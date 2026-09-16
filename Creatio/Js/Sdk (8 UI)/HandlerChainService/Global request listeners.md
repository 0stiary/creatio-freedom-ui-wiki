**HandlerChainService** позволяет регистрировать обработчики вне схем freedom или обрабатывать запросы, выполняемые вне контекста страницы.  

1. **Первый способ: регистрация конкретного обработчика** 
   - Создаем класс обработчик и регистрируем для конкретного запроса в **HandlerChainService**.  

		```js Template
		// класс обработчик
		const handlerType = class extends sdk.BaseRequestHandler {
		    handle(request) {
		        // бизнес-логика
		    }
		};
		
		// регистрация обработчика
		sdk.HandlerChainService.instance.register({
		    // тип обрабатываемого запроса
		    requestType: "bnz.ExampleRequest",
		    // ранее созданный обработчик
		    createHandler: () => new handlerType(),
		    // указать ключи при которых будет запускаться обработчик
		    scopes: [],
		    source: { type: sdk.HandlerSourceType.Host }
		});
		```

  
2. **Второй способ: обработка всех типов запросов** 
   - В данном случае подписываемся на все запросы которые будут генерироваться в системе (неважно что будет указано в `scopes` запроса).  

		```js
		sdk.HandlerChainService.instance.subscribe(function (request) {
		    // бизнес-логика
		});
		```

  
При любом из подходов `register` или `subscribe` необходимо сделать отписку от реквестов в момент уничтожения вью модели.
Функции `register` и `subscribe` возвращают функцию которая сделает отписку, нам необходимо просто сохранить данную функцию и вызвать в нужный момент, например при `crt.HandleViewModelDestroyRequest`.  
Пример подписки и сохранения функции для отписки  

```js title="Subscribe"
{
    request: "crt.HandleViewModelInitRequest",
    handler: async function (request, next) {
      next?.handle(request);
      // создадим массив в context где будем хранить все отписки от событий
      request.$context.unsubscribesHandlers = request.$context.unsubscribesHandlers || [];
      let unsubscribeHandler = sdk.HandlerChainService.instance.subscribe(function (request) {
          // бизнес-логика
      });
      request.$context.unsubscribesHandlers.push(unsubscribeHandler);
    }
}
```

  
Отписка при дестрое схемы  

```js title="Unsubscribe"
{
        request: "crt.HandleViewModelDestroyRequest",
        handler: async function(request, next) {
          request.$context.unsubscribesHandlers && request.$context.unsubscribesHandlers.forEach(x => x());
          return next?.handle(request);
        }
}
```