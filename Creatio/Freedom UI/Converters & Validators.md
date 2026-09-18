---
tags: [creatio, freedom-ui, converters]
generated: 2026-09-16
---
# Конвертери та валідатори Freedom UI

Сигнатура конвертера: `convert(value, $context, ...args)` — перший аргумент = значення атрибута ліворуч від `|`, другий = view-модель контексту (для рядка `crt.TemplateList`/`crt.DataGrid` — view-модель елемента колекції, інакше сторінка), далі — аргументи після `:`. Синтаксис у конфігу: `"$Attr | crt.Conv : 'arg1' : $OtherAttr | crt.Conv2"`. Кастомні конвертери оголошуються у схемі в секції `converters: { "usr.Name": (value, ctx, ...args) => ... }`.

Валідатор: у `viewModelConfig.attributes.X.validators: { "crt.Required": { type: "crt.Required", params: {...} } }`; метод `validate(control)` повертає `null` або об'єкт помилки.

| Тип | Метод | Тіло (початок, мінімізовано) |
|---|---|---|
| `crt.ActivityResultsFilters` | `convert(Kt)` | `{const $t=this._getActivityCategory(Kt);if(!$t)return null;const _e=new nt.X;return this._addActivityCategoryFilter(_e,$t),this._addAllowedResultFilterIfNeed(_e,$t,Kt),this._addBusinessProcessOnlyFilterIfNeed(_e,$t,Kt),_` |
| `crt.AdPlatformLogin` | `— (дія/сервіс, не конвертер)` |  |
| `crt.AddBulkEmailAudience` | `— (дія/сервіс, не конвертер)` |  |
| `crt.AddEventAudience` | `— (дія/сервіс, не конвертер)` |  |
| `crt.AdfsTenantValidator` | `validate(e,t)` | `{const a=super.validate(e);return a\|\|(e.value.trim().startsWith("http")?{required:this.defaultValidationError(t)}:null)}` |
| `crt.AppendConditionalParts` | `convert(h,y,...L)` | `{let k=h[0];for(let mt=0,Vt=L.length;mt<Vt;mt++)k+=h[mt+1]?L[mt]:"";return k}` |
| `crt.BaseLlmViewElementConfigToSchema` | `convert(_,i,s)` | `{var c=this;return(0,e.A)(function*(){const d=yield c.generateViewConfigDiff(_,s),p=yield c.generateViewModelConfigDiff(_,s),r=yield c.generateModelConfigDiff(_,s);return{viewConfigDiff:d,viewModelConfigDiff:p,modelConfi` |
| `crt.BooleanToStringValue` | `convert(h,y,L,k=null)` | `{return h?L:k}` |
| `crt.ChartWidgetToSchema` | `— (дія/сервіс, не конвертер)` |  |
| `crt.CommunicationMenuItems` | `convert(t,e,n=[])` | `{const[o,i]=t,r=[...new Set(o.map(u=>u.typeOrGroupId))],c=[];for(const u of r){const d=o.filter(v=>v.typeOrGroupId===u),g=d[0],y=g?.groupIcon?.value;if(d.length>1){const v=this._getMenuItem(y,g.groupName);v.items=d.map(b` |
| `crt.CommunicationOptionsValidation` | `convert(t)` | `{var e=this;return(0,f.A)(function*(){const n=e._getValidationResult(!0);if(!t.masterRecordColumnName\|\|!t.masterRecordColumnValue)return e._getValidationResult(!1,e._translate("Validations.IncorrectSetupComponentMessag` |
| `crt.CommunicationTypeProvider` | `convert(t)` | `{var e=this;return(0,f.A)(function*(){const n=yield e._getCache();if(yield n.has(t))return n.get(t);const o=e._createQuery(t);try{const r=(yield(0,p.firstValueFrom)(e._queryExecutor.executeSelectQuery(o).pipe((0,p.catchE` |
| `crt.Compact` | `convert(h)` | `{return(0,ae.compact)(h)}` |
| `crt.ConditionalEmailId` | `convert(M)` | `{const u=M[1],s=M[0];return u?null:s}` |
| `crt.CopilotChatMode` | `convert(e,t,n)` | `{const[s,i]=e;return s\|\|(n?!i:i)}` |
| `crt.CreateFilterByDependency` | `convert(h,y,L,k)` | `{var mt=this;return(0,z.A)(function*(){const Vt=y,ee=new ta.s("TEMP");return yield mt._addDataSourceFilters(ee.filters,Vt,L,k),ee.getMetadata().filters})()}` |
| `crt.CreatioAiHeaderCaption` | `convert(Y)` | `{const[nt,ut]=Y;return!nt&&!ut}` |
| `crt.DataGridHasNoFilteredItems` | `convert(h)` | `{const y=h.shift();return this.isEmptyCollection(y)&&this.hasFilterValues(h)}` |
| `crt.DataGridHasNoItems` | `convert(h)` | `{const y=h.shift();return this.isEmptyCollection(y)&&!this.hasFilterValues(h)}` |
| `crt.DataGridStage` | `convert(Pt,Mt)` | `{var Ht=this;return(0,ct.A)(function*(){const[zt,Te]=yield Promise.all([(0,lt.firstValueFrom)(Ht._dcmSchemaManagerService.getDcmSchemaDataCollection()),(0,lt.firstValueFrom)(Ht._dcmSchemaManagerService.getDcmSchemaDataIt` |
| `crt.DeleteBackgroundImage` | `— (дія/сервіс, не конвертер)` |  |
| `crt.EmptyOrWhiteSpace` | `validate(_,i)` | `{const s=_.value;return(typeof s=="string"?!!(_&&_.value?.trim()):this.validateLczValue(s))?null:{required:this.defaultValidationError(i)}}` |
| `crt.FindInCollection` | `convert(ot,gt,jt,be)` | `{return(0,dt.A)(function*(){const Ve=yield gt[jt];if(!Ve\|\|!Array.isArray(Ve))return null;for(const un of Ve)if(typeof un=="object"&&un!==null&&be){if((yield un[be])===ot)return un}else if(un===ot)return un;return null}` |
| `crt.FollowFeedButtonCaption` | `convert(b)` | `{return b?this._translateService.instant("Feed.Following.ButtonCaption.Unfollow"):this._translateService.instant("Feed.Following.ButtonCaption.Follow")}` |
| `crt.FormatValue` | `convert(ot,gt,jt)` | `{return this._formatValuePipe.transform(ot,jt)}` |
| `crt.FullPipelineWidgetToSchema` | `— (дія/сервіс, не конвертер)` |  |
| `crt.FunnelWidgetToSchema` | `— (дія/сервіс, не конвертер)` |  |
| `crt.GenerateCopilotActionCode` | `convert(e,t,n)` | `{var s=this;return(0,a.A)(function*(){const i=e.map(function(){var p=(0,a.A)(function*(h){return yield h[n]});return function(h){return p.apply(this,arguments)}}()),o=yield Promise.all(i);return(0,r.lastValueFrom)(s._int` |
| `crt.GenerateCopilotSkillCode` | `convert(e,t,n)` | `{var s=this;return(0,a.A)(function*(){const i=e.map(function(){var p=(0,a.A)(function*(h){return yield h[n]});return function(h){return p.apply(this,arguments)}}()),o=yield Promise.all(i);return(0,r.lastValueFrom)(s._int` |
| `crt.GetFeatureState` | `convert(h,y)` | `{if(!this._validateParameters(h))return!1;const L=this._normalizedFeature(h);return!!this._featureValues[L]}` |
| `crt.GoogleAnalyticsLogin` | `— (дія/сервіс, не конвертер)` |  |
| `crt.HasUnsavedDataOr7XDetails` | `convert([h,y])` | `{return h\|\|y?.length>0}` |
| `crt.HideComponentWithNoItems` | `convert(ot,gt,jt)` | `{return(0,dt.A)(function*(){return(ot?.shift()\|\|gt.attributes[jt])?.length?{}:{display:"none"}})()}` |
| `crt.IfElse` | `convert(ot,gt,jt,be)` | `{return ot?jt:be}` |
| `crt.IndicatorWidgetToSchema` | `— (дія/сервіс, не конвертер)` |  |
| `crt.InterpolateString` | `convert(ot,gt,jt,...be)` | `{return _e.String.format(jt,ot,...be)}` |
| `crt.InvertBooleanValue` | `convert(ot)` | `{return!ot}` |
| `crt.IsAnySelected` | `convert(h,y)` | `{return h?.type==="specific"?h.selected?.length>0:h?.type==="all"}` |
| `crt.IsCallActive` | `convert(t)` | `{const n=t?.state===w.CONNECTED\|\|t?.state===w.HOLDED\|\|t?.state===w.CONFERENCED,a=t?.isWrapUp\|\|!1;return n\|\|a}` |
| `crt.IsCallDetailsChanged` | `convert(t)` | `{const n=t[0],a=t[1],l=t[2],s=t[3],d=t[4],h=(a??"")!==(s??""),p=(l??"")!==(d?.value??""),v=h\|\|p;return v&&this._wrapUpService?.typing(n?.callId),v}` |
| `crt.IsCallDetailsChangedAndWrapUp` | `convert(t)` | `{const n=t[0],a=t[1];return n&&(a?.isWrapUp??!1)}` |
| `crt.IsCallDetailsUnchanged` | `convert(t)` | `{const n=t[0],a=t[1];return!n&&(a?.isWrapUp??!1)}` |
| `crt.IsEqual` | `convert(ot,gt,jt)` | `{return(0,H.isEqual)(ot,jt)}` |
| `crt.IsEveryEqualTo` | `convert(ot,gt,jt)` | `{const be=Array.isArray(ot)?ot:[ot];return be.length?be.every(Ve=>super.convert(Ve,gt,jt)):!0}` |
| `crt.IsJsonValidator` | `validate(e,t)` | `{const a=e.value;if((0,y.isEmpty)(a)&&t?.skipEmptyValues)return null;try{JSON.parse(a===null?"":a)}catch{return{IsJson:{message:this._translateService?.instant(this.i18nMessageKey)\|\|""}}}return null}` |
| `crt.IsModelLoaded` | `convert(ot,gt,jt)` | `{return gt.getModelByName(jt).isLoaded}` |
| `crt.IsRightPanelVisible` | `convert(Et)` | `{return!!Et}` |
| `crt.IsTargetSummaryItem` | `convert(t,e,a)` | `{return!t\|\|!a?!1:this._isEqualByViewElement(t,a)\|\|this._isEqualByModel(t,a)}` |
| `crt.LaunchCampaign` | `— (дія/сервіс, не конвертер)` |  |
| `crt.LinkPrefix` | `convert(ot)` | `{return(0,H.isEmpty)(ot)?"":(ot=ot.trim(),this._getEncodedUri(ot.startsWith("http://")\|\|ot.startsWith("https://")?ot:`//${ot}`))}` |
| `crt.ListWidgetToSchema` | `— (дія/сервіс, не конвертер)` |  |
| `crt.LoadFeedMessages` | `convert(d,g,P,i,c,M)` | `{var h=this;return(0,n.A)(function*(){const v=yield g[c];h._feedSortColumn=v\|\|h._feedSortColumn;const f=d.find(y=>!!y&&!(0,e.n7)(y));if(P===x.Q.User)return h._getUserMessages(f,M);if(P===x.Q.Record){const y=d.find(L=>(` |
| `crt.LoadInProgressChats` | `convert()` | `{return this.getChats(!0)}` |
| `crt.LoadNextSteps` | `convert(t,n,i)` | `{const o=t.find(c=>(0,G.n7)(c));return(0,l.isEmpty)(o)\|\|(0,l.isEmpty)(i)\|\|i==="#DataSourceEntityName()#"?(0,A.lastValueFrom)((0,A.of)([])):(0,A.lastValueFrom)(this._nextStepsService.getNextSteps(o,i))}` |
| `crt.LoadNotAcceptedChats` | `convert()` | `{return this.getChats(!1)}` |
| `crt.Max` | `validate(Tt,Ut)` | `{const pe=a.Validators.max(Ut.max)(Tt);return pe?{max:this.defaultValidationError({...Ut,...pe.max})}:null}` |
| `crt.MaxLength` | `validate(Tt,Ut)` | `{const re=Gn.T.getControlValueAndTrimIfNeeded(Tt,Ut);return this._maxLengthValidator(re,Ut)}` |
| `crt.MergeIncomingItems` | `convert(t)` | `{return t.flat().filter(n=>!!n)}` |
| `crt.Min` | `validate(Tt,Ut)` | `{const pe=a.Validators.min(Ut.min)(Tt);return pe?{min:this.defaultValidationError({...Ut,...pe.min})}:null}` |
| `crt.MinLength` | `validate(Tt,Ut)` | `{const re=Gn.T.getControlValueAndTrimIfNeeded(Tt,Ut);return this._minLengthValidator(re,Ut)}` |
| `crt.NorCondition` | `convert(h,y,L)` | `{return!h&&!L}` |
| `crt.OpenCampaignDesigner` | `— (дія/сервіс, не конвертер)` |  |
| `crt.OpenEmailDesigner` | `— (дія/сервіс, не конвертер)` |  |
| `crt.OrBooleanValue` | `convert(ot,gt,jt)` | `{Array.isArray(ot)\|\|(ot=[ot,jt]);const be=ot[0],Ve=ot[1];return be\|\|Ve}` |
| `crt.PhoneNumber` | `validate(Tt,Ut)` | `{return!Tt.value\|\|this._phoneValidationService.isValidPhoneNumber(Tt.value)?null:{invalidPhoneNumber:this.defaultValidationError(Ut)}}` |
| `crt.PickDataGridFeatureValue` | `convert(Pt,Mt,Ht)` | `{const zt=J(Pt,this._defaultFeatures);return Ht?(0,j.get)(zt,Ht):zt}` |
| `crt.RegExp` | `validate(Tt,Ut)` | `{typeof Ut.regex=="string"&&(Ut.regex=new RegExp(Ut.regex));const re=Ut.regex.test(Tt.value);return this.i18nMessageKey=Ut.message\|\|this.i18nMessageKey,re?null:{[Ut.errorCode]:this.defaultValidationError({...Ut})}}` |
| `crt.RemoveBulkEmailAudience` | `— (дія/сервіс, не конвертер)` |  |
| `crt.RemoveEventAudience` | `— (дія/сервіс, не конвертер)` |  |
| `crt.Required` | `validate(i,s)` | `{const c=u.T.getControlValueAndTrimIfNeeded(i,s);return this._requiredValidator(c,s)}` |
| `crt.RightPanelContainerSelectedTab` | `convert(Et)` | `{return Et&&Et.value!==g.hO?Ot:Et}` |
| `crt.SchemaNameAllowedSymbols` | `validate(Tt)` | `{return super.validate(Tt,this._params)}` |
| `crt.SchemaNamePrefix` | `validate(Tt,Ut)` | `{var re=this;return(0,M.A)(function*(){if((0,Wa.isObject)(Tt.value))return null;const pe=Gn.T.getControlValueAndTrimIfNeeded(Tt,{trimValue:!0}),xe=yield re._getSchemaNamePrefix();if(xe){const Ge=!pe?.startsWith(xe);if(Ge` |
| `crt.ShouldEnableSenderDomainShareAction` | `convert(Pt,Mt,Ht)` | `{return!Pt\|\|!Ht?!1:Pt.value===this._validatedStatusId}` |
| `crt.SkipIfSelectionEmpty` | `convert(h,y,L)` | `{return this._isSelectionStateEmpty(L)?null:h}` |
| `crt.StopCampaign` | `— (дія/сервіс, не конвертер)` |  |
| `crt.StringUrlValidator` | `validate(e,t)` | `{if(t&&t.SkipEmptyValues&&(0,y.isEmpty)(e.value))return null;const r=super.validate(e);if(r)return r;const i=e.value;try{new URL(i)}catch{return{required:this.defaultValidationError(t)}}return null}` |
| `crt.SummaryItemToExpressionMetadata` | `convert(t,e,a,s)` | `{var m=this;return(0,v.A)(function*(){if(!a\|\|!s)return null;let u=yield m._getModelFilters(a,e);if(!u)return null;const{hierarchyConfig:_,excludedFilters:f}=yield m._getHierarchyWithFiltersConfig(a,e);return f&&(u=f),m` |
| `crt.ToAggregatedValue` | `convert(ot,gt,jt)` | `{return ot&&jt===Ct.Sum?this._summarize(ot):0}` |
| `crt.ToBoolean` | `convert(ot)` | `{return!!ot}` |
| `crt.ToChartWidgetSeriesDataAsync` | `convert(h,y,L)` | `{var k=this;return(0,z.A)(function*(){const mt=L?.length??0,Vt=new Array(mt).fill([]);if(mt===0\|\|h.filter(Boolean).length<mt)return Vt;const fe=L.map(cn=>k._getSeriesData(y,cn)),$e=yield Promise.all(fe);return $e.every` |
| `crt.ToCollectionFilters` | `convert(h,y,L,k)` | `{var mt=this;return(0,z.A)(function*(){const Vt=y,ee=Vt.getBoundDataSchemaByAttributePath(L).primaryAttributeName,fe=k?.type==="specific"&&k?.selected?.length,$e=k?.type==="all"&&k?.unselected?.length,cn=new ta.s("tempTa` |
| `crt.ToCollectionItemsCount` | `convert(h,y,L,k)` | `{const[mt,Vt]=h;return Vt?!mt\|\|mt.length===0?(this._resetItemsCountLoadParameters(L,y),Promise.resolve(0)):super.convert(h,y,L,k):y.attributes[k]}` |
| `crt.ToCollectionSelectedItemsCount` | `convert(h,y,L,k)` | `{var mt=()=>super.convert,Vt=this;return(0,z.A)(function*(){const[ee,fe,$e]=h??[];if((0,ae.isNil)($e)\|\|!fe?.type)return 0;if(fe.type==="specific")return fe.selected?.length??0;const cn=fe.unselected??[];if(cn.length===` |
| `crt.ToDataGridDesignSettingsByFolderAsync` | `convert(yt,Ct,Ot)` | `{return this._dataGridDesignSettingsByFolderRepository.get({dataGridName:Ot,schema:this._schemaService.schema,folderId:yt})}` |
| `crt.ToDataGridHeaderToolbarItemsAsync` | `convert(Pt,Mt,Ht)` | `{var zt=this;return(0,ct.A)(function*(){const Te={type:"crt.MenuLabel",caption:zt._translateService.instant("DataGrid.ActionsToolbar.DataGridSettingsLabel")},je={type:"crt.MenuItem",caption:zt._translateService.instant("` |
| `crt.ToDataGridHeaderToolbarItemsByFolderAsync` | `convert(yt,Ct,Ot)` | `{var Zt=this;return(0,s.A)(function*([A,Kt],$t,_e){if(Kt??=[],!A\|\|Zt._dataGridDesignSettingsByFolderDisabled)return Kt;const Oe=Zt._getRelatedFolderTreeViewConfig(_e);if(!Oe?.name)return Kt;const{activeFolderNameAttrNa` |
| `crt.ToDataTableSortingConfig` | `convert(Pt,Mt,Ht)` | `{if(!Pt?.length\|\|!Mt\|\|!Ht)return[];const zt=Mt._attributeConfigs?.[Ht];return zt?(0,z.Zt)(Pt,zt):[]}` |
| `crt.ToDataValueTypeDisplayValue` | `convert(ot)` | `{if(!ot)return this._getEmptyDisplayValue();const gt=Object.values(Ce.Q).find(jt=>jt.id===ot)?.translateKey;return gt?this._translateService.instant(gt):this._getEmptyDisplayValue()}` |
| `crt.ToDataValueTypeLookupValue` | `convert(ot)` | `{if(!ot)return null;const gt=Object.values(Ce.Q).find(jt=>jt.id===ot);return gt?{value:gt.id,displayValue:this._translateService.instant(gt.translateKey)}:null}` |
| `crt.ToDcmStageValue` | `convert(ot)` | `{return ot?(0,Kt.lastValueFrom)(this._getDcmStagesList(ot.value)):Promise.resolve([])}` |
| `crt.ToDisplayValue` | `convert(ot)` | `{return ot?.displayValue\|\|ot?.value\|\|ot}` |
| `crt.ToEmailLink` | `convert(ot)` | `{return ot?`mailTo: ${ot}`:""}` |
| `crt.ToEmptyPlaceholder` | `convert(ot,gt,jt)` | `{return this._toEmptyPlaceholder.transform(ot,jt)}` |
| `crt.ToEntityStageDataTableSliderConverterAsync` | `convert(h,y,L)` | `{var k=this;return(0,z.A)(function*(){if(!L)return null;const mt=yield k._getTargetDCMSchemaData(L.schemas,L.filterColumnAttributePath,y),Vt=L.schemasData.find(ee=>ee.name===mt?.name);return k._getSliderCellModel(h,Vt)})` |
| `crt.ToEqualFilter` | `convert(h,y,L)` | `{if(!this._validateParameters(h,L))return{};const k=this._normalizedValue(h),mt=new Fi.x(ua.H.Equal,new Bn.g({columnPath:L}),new Pi.J({value:k}));return(0,As.classToPlain)(mt)}` |
| `crt.ToExpressionResult` | `convert(Tt,Ut)` | `{const re={type:"crt.ExecuteExpressionRequest",$context:Ut,metadata:Tt};return Ot.t.instance.process(re).then(pe=>pe).catch(pe=>({success:!1,result:null,errorInfo:pe}))}` |
| `crt.ToFileContentUrl` | `convert(h,y,L)` | `{return this._fileContentUrlBuilder.getUrl(L,h)}` |
| `crt.ToFileLink` | `convert(s,c,d)` | `{return d?a.Location.joinWithSlash(this._getFilePath(d),s):""}` |
| `crt.ToFilterGroup` | `convert(h,y,L=Yi.H.Or,k)` | `{const mt=new $o.X(L,k);return h??=[],h.filter(Vt=>typeof Vt!="object"\|\|Object.entries(Vt).length>0).forEach(Vt=>{mt.add(typeof Vt=="string"?JSON.parse(Vt):Vt)}),(0,As.instanceToPlain)(mt)}` |
| `crt.ToImageLink` | `convert(ot,gt)` | `{return ot?typeof ot=="string"?ot:(0,$.Mc)(ot.value):""}` |
| `crt.ToInFilter` | `convert(h,y,L)` | `{if(!L)return{};if(Array.isArray(h)&&h.length===0)return{};const k=new bl.f(ua.H.Equal,new Bn.g({columnPath:L}),this._getParametersExpression(h));return(0,As.classToPlain)(k)}` |
| `crt.ToIndicatorValueAsync` | `convert(h,y,L)` | `{return(0,z.A)(function*(){return h?.length?(yield h[0][L])?.toString():""})()}` |
| `crt.ToKeyValuePair` | `convert(h,y,L)` | `{return[L,h]}` |
| `crt.ToLocalTimeValue` | `convert(ot)` | `{const gt=this._userInfo?.cultureInfo,jt=(0,H.isEmpty)(gt?.dateTimeFormat?.code)?(0,H.isEmpty)(gt?.sysCultureName)?"en-US":gt.sysCultureName:gt.dateTimeFormat.code,be=!(0,H.isEmpty)(gt?.dateTimeFormat?.amDesignator);retu` |
| `crt.ToLookup` | `convert(v,C,P)` | `{var I=this;return(0,e.A)(function*(){const D=Array.isArray(v),b=D?v:[v],R=b.filter(d.n7),O=I.getLookupValuesFromContext(R,C,P),{lookupValues:S,notFound:M}=O,T=yield I._getLookupValuesFromDataSource(M,P),x=b.map(V=>S.fin` |
| `crt.ToLookupDisplayValue` | `convert(ot)` | `{return this._lookupFormatPipe.transform(ot)}` |
| `crt.ToMeetingInvitationInfo` | `convert(e)` | `{const t=e?.value\|\|e;return(0,u.lastValueFrom)(this._changeMeetingService.getMeetingInvitationInfo(t))}` |
| `crt.ToObjectCollectionWithMapping` | `convert(h,y,L)` | `{const k=new Array;return h.forEach((mt,Vt)=>{typeof L[Vt]>"u"\|\|k.push({name:L[Vt],value:mt})}),k}` |
| `crt.ToObjectFromEntries` | `convert(h,y)` | `{return Object.fromEntries(h)}` |
| `crt.ToObjectProp` | `convert(ot,gt,jt,be=null)` | `{const Ve=ot&&ot[jt];return Ve==null\|\|Ve===""?be:Ve}` |
| `crt.ToOpenPageLink` | `convert(h,y,L)` | `{return this._getRecordUrl(h,L)}` |
| `crt.ToPhoneLink` | `convert(ot)` | `{return ot?`tel: ${ot}`:""}` |
| `crt.ToRecipientsMailboxes` | `convert(h)` | `{return(0,p.lastValueFrom)(this._recipientsService.getRecipients(h.event.query,h.event.recipientsLength).pipe((0,p.map)(y=>({recipients:y,loadStamp:(0,t.qv)()}))))}` |
| `crt.ToRecordLinkAsync` | `convert(h,y,L)` | `{return(0,z.A)(function*(){if(!h)return null;const{referenceSchemaName:k}=yield(0,h_.N)(y,L);return(0,as.TX)(k,h)})()}` |
| `crt.ToSendInviteDisabled` | `convert(e)` | `{return!e\|\|!e.HasCalendarIntegration}` |
| `crt.ToSendInviteIsOutdated` | `convert(e)` | `{return!e\|\|e.IsOutdatedMeeting}` |
| `crt.ToSendInviteIsStartDateUpdated` | `convert(e)` | `{return!!e}` |
| `crt.ToSendInviteVisible` | `convert(e)` | `{return!e\|\|!e.IsParticipantsExist\|\|e.organizer?.value!==this._userInfo.contactId?!1:!e.HasCalendarIntegration\|\|e.IsSynchronized}` |
| `crt.ToSendersMailboxes` | `convert()` | `{return(0,p.lastValueFrom)(this._userInfoService.loadCurrentUserInfo().pipe((0,p.concatMap)(h=>this._mailboxesService.getMailboxesForSend(h?.userInfo.id))))}` |
| `crt.ToSummariesActionsAsync` | `convert(t,e,a,s)` | `{var m=this;return(0,v.A)(function*(){const u=yield m._getProfileActions(a),_=yield m._createQuickSummaryItemMenuItemsSection(a,s,e),f=m._createAdvancedSetupActions(a);return[..._,...f,...u]})()}` |
| `crt.ToTileFilter` | `convert(t,n,i)` | `{return Promise.resolve({filter:t,type:i})}` |
| `crt.ToTileFilterGroup` | `convert(t,n)` | `{return Promise.resolve(t)}` |
| `crt.ToValuesFromCollection` | `convert(ot,gt,jt,be,Ve)` | `{var un=this;return(0,dt.A)(function*(){const[Ta,ci]=ot??[];if(!Ta\|\|!jt\|\|!be\|\|!gt)return[];const Wr=un._normalizePrimaryAttributeValues(ci),_r=Ve?.filterByPrimaryAttributeValues!==!1;if(!Wr?.length&&_r)return[];con` |
| `crt.UniqueCodeColumnValue` | `validate(Tt,Ut)` | `{const re=Tt.value;if(!re)return null;const pe=window[this._windowCodeList];return pe&&pe.filter(Ge=>Ge===re).length>1?{uniqueColumnValue:this.defaultValidationError({...Ut,controlValue:re})}:null}` |
| `crt.UserPasswordComplexity` | `— (дія/сервіс, не конвертер)` |  |
| `crt.UserPasswordHistory` | `validate(W,tt)` | `{var _t=this;return(0,_.A)(function*(){const Rt=Ie.T.getControlValueAndTrimIfNeeded(W,{trimValue:!1});return Ie.T.isEmptyInputValue(Rt)\|\|!Ie.T.hasValidLength(Rt)\|\|(yield _t._getSysSettingByCode("PasswordHistoryRecord` |
| `crt.UserPasswordLoginEquality` | `validate(W,tt)` | `{var _t=this;return(0,_.A)(function*(){const Rt=Ie.T.getControlValueAndTrimIfNeeded(W,{trimValue:!1});return Ie.T.isEmptyInputValue(Rt)\|\|!Ie.T.hasValidLength(Rt)\|\|!(yield _t._getSysSettingByCode("PasswordNotEqualToUs` |
| `crt.ValidateCampaign` | `— (дія/сервіс, не конвертер)` |  |
| `crt.ViewModelCollectionToIncomingItemsArray` | `convert(t,n,a)` | `{return(0,m.A)(function*(){return!t\|\|t.length===0\|\|!a?[]:yield Promise.all(t.map(function(){var s=(0,m.A)(function*(d){return{schemaName:(yield d.getPrimaryDataSchema()).name,id:yield d[a.id],itemTitle:yield d[a.item` |