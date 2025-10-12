# Game.UI.Menu.AssetUploadPanelUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Fields

- `private Game.UI.Menu.NotificationUISystem m_NotificationUISystem`  
- `private Game.UI.Editor.AssetPickerAdapter m_PreviewPickerAdapter`  
- `private Game.UI.Menu.PdxAssetUploadHandle m_UploadHandle`  
- `private System.Boolean m_AllowManualFileCopy`  
- `private Game.UI.Menu.AssetUploadPanelUISystem+State m_State`  
- `private Game.UI.Widgets.IWidget[] m_MainPanel`  
- `private Game.UI.Editor.LargeIconButton m_PreviewPickerButton`  
- `private Game.UI.Editor.ExternalLinkField m_ExternalLinkField`  
- `private Game.UI.Widgets.IconButtonGroup m_Screenshots`  
- `private Game.UI.Widgets.LayoutContainer m_PlatformResult`  
- `private Game.UI.Editor.Widgets.ItemPickerPopup<System.Int32> m_ExistingModPopup`  
- `private Game.UI.Widgets.PopupValueField<System.Int32> m_ExistingModField`  
- `private Game.UI.Widgets.Button m_SubmitButton`  
- `private Game.UI.Editor.ListField m_AssetList`  
- `private Game.UI.Widgets.PopupValueField<Game.Prefabs.PrefabBase> m_AssetListPopup`  
- `private Game.UI.Editor.ListField m_TagsList`  
- `private Game.UI.Widgets.PopupValueField<System.String> m_TagsListPopup`  
- `private Game.UI.Widgets.LayoutContainer m_DLCInfo`  
- `private System.Boolean m_DLCInfoVisible`  
- `private Game.UI.Widgets.IWidget[] m_PreviewPickerPanel`  
- `private Game.UI.Widgets.Button m_SelectPreviewButton`  
- `public System.Action<System.Collections.Generic.IList<Game.UI.Widgets.IWidget>> onChildrenChange`  
- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children`  
- `private static readonly System.String kNotificationID`  
- `private static readonly Game.UI.Localization.LocalizedString kNone`  
- `private static readonly System.String kFailureLabel`  
- `private static readonly System.String kSubmittingLabel`  
- `private static readonly System.String kCompleteLabel`  
- `private static readonly System.String kSubmitLabel`  
- `private static readonly System.String kNoInternetConnectionLabel`  
- `private static readonly System.String kNotLoggedInLabel`  
- `private static readonly System.String kNoSocialProfile`  
- `private static readonly System.String kOpenProfilePage`  
- `private static readonly System.String kDLCListLabel`  
- `private static readonly System.Single kNotificationDelay`  

## Properties

- `private System.Boolean nameError { private get }`  
- `private System.Boolean shortDescirptionError { private get }`  
- `private System.Boolean longDescipriontError { private get }`  
- `private System.Boolean forumLinkError { private get }`  
- `private System.Boolean externalLinkError { private get }`  
- `private System.Boolean changelogError { private get }`  
- `private System.Boolean versionError { private get }`  
- `private System.Boolean noInternetConnection { private get }`  
- `private System.Boolean notLoggedIn { private get }`  
- `private System.Boolean anyError { private get }`  
- `private System.Boolean disableSubmit { private get }`  
- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get }`  

## Constructors

- `public AssetUploadPanelUISystem()`  

## Methods

- `private <OnCreate>b__60_0() : System.Void`  
- `private <OnCreate>b__60_1() : System.Boolean`  
- `private <OnCreate>b__60_10() : System.Boolean`  
- `private <OnCreate>b__60_11() : System.Int32`  
- `private <OnCreate>b__60_12(System.Int32 value) : System.Void`  
- `private <OnCreate>b__60_13() : System.Boolean`  
- `private <OnCreate>b__60_14() : System.Boolean`  
- `private <OnCreate>b__60_15() : System.String`  
- `private <OnCreate>b__60_16(System.String value) : System.Void`  
- `private <OnCreate>b__60_18() : System.Boolean`  
- `private <OnCreate>b__60_19() : System.Boolean`  
- `private <OnCreate>b__60_2() : System.String`  
- `private <OnCreate>b__60_20() : System.String`  
- `private <OnCreate>b__60_21(System.String value) : System.Void`  
- `private <OnCreate>b__60_22() : System.String`  
- `private <OnCreate>b__60_23(System.String value) : System.Void`  
- `private <OnCreate>b__60_24() : System.Boolean`  
- `private <OnCreate>b__60_25() : System.String`  
- `private <OnCreate>b__60_26(System.String value) : System.Void`  
- `private <OnCreate>b__60_27() : System.Boolean`  
- `private <OnCreate>b__60_28() : System.String`  
- `private <OnCreate>b__60_29(System.String value) : System.Void`  
- `private <OnCreate>b__60_3(System.String value) : System.Void`  
- `private <OnCreate>b__60_30() : System.Boolean`  
- `private <OnCreate>b__60_32() : System.Boolean`  
- `private <OnCreate>b__60_33() : Game.UI.Editor.ProgressIndicator+State`  
- `private <OnCreate>b__60_34() : System.Boolean`  
- `private <OnCreate>b__60_35() : System.Boolean`  
- `private <OnCreate>b__60_36() : System.Void`  
- `private <OnCreate>b__60_4() : System.Boolean`  
- `private <OnCreate>b__60_5() : System.Boolean`  
- `private <OnCreate>b__60_6(System.Boolean value) : System.Void`  
- `private <OnCreate>b__60_7() : System.Int32`  
- `private <OnCreate>b__60_8(System.Int32 value) : System.Void`  
- `private <OnCreate>b__60_9() : System.Boolean`  
- `private <RefreshScreenshots>b__81_1() : System.Void`  
- `private <ReportNoSocial>b__69_0() : System.Void`  
- `private <SyncPlatformData>b__73_0() : System.Void`  
- `private AddScreenshot(Colossal.Hash128 guid) : System.Void`  
- `private BeginSubmit() : System.Void`  
- `private Cancel() : System.Void`  
- `private ClearState() : System.Void`  
- `public Close() : System.Boolean`  
- `private ClosePreviewPickerPanel(System.Action<Colossal.Hash128> callback) : System.Void`  
- `private FinalizeSubmit() : System.Void`  
- `private GetExistingMods() : System.Collections.Generic.IEnumerable<Game.UI.Editor.Widgets.ItemPickerPopup<System.Int32>>`  
- `private static GetItem(Colossal.IO.AssetDatabase.AssetData asset, System.Boolean removable, System.Boolean mainAsset) : Game.UI.Editor.ListField+Item`  
- `private static GetLabel(Colossal.IO.AssetDatabase.AssetData asset) : System.String`  
- `private GetPreviews(System.Boolean excludeScreenshots = False) : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  
- `private GetSubmitButtonLabel() : System.String`  
- `private OnAddPrefab(Game.Prefabs.PrefabBase prefab) : System.Void`  
- `private OnAddTag(System.String tag) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `private OnRemoveAdditionalAsset(System.Int32 index) : System.Void`  
- `private OnRemoveTag(System.Int32 index) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private OpenPreviewPickerPanel(System.Action<Colossal.Hash128> callback, Colossal.Hash128 defaultSelection = null, System.Boolean excludeScreenshots = False) : System.Void`  
- `private RefreshAssetList() : System.Void`  
- `private RefreshAuthorMods() : System.Void`  
- `private RefreshDLCList() : System.Void`  
- `private RefreshExternalLinks() : System.Void`  
- `private RefreshPreview() : System.Void`  
- `private RefreshScreenshots() : System.Void`  
- `private RefreshSocialProfileStatus() : System.Void`  
- `private RefreshSubmitButtonLabel() : System.Void`  
- `private RefreshTags() : System.Void`  
- `private RemoveScreenshot(System.Int32 index) : System.Void`  
- `private ReportError(Colossal.PSI.Common.IModsUploadSupport+ModOperationResult result) : System.Void`  
- `private ReportLocalDataNotFound() : System.Void`  
- `private ReportNoSocial() : System.Void`  
- `private ReportSubmitting() : System.Void`  
- `private ReportSuccess() : System.Void`  
- `private ReportSyncing() : System.Void`  
- `private SetChildren(Game.UI.Widgets.IWidget[] newChildren) : System.Void`  
- `private SetInfoFromExisting() : System.Void`  
- `private SetPreview(Colossal.Hash128 guid) : System.Void`  
- `private ShouldShowInPrefabPicker(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `public Show(Colossal.IO.AssetDatabase.AssetData mainAsset, System.Boolean allowManualFileCopy = False) : System.Void`  
- `private Submit() : System.Void`  
- `private SyncPlatformData() : System.Void`  
- `private TryMatchDLC(System.String internalName, Colossal.PSI.Common.IModsUploadSupport+DLCTag& dlc) : System.Boolean`  

## Nested types

- `Game.UI.Menu.AssetUploadPanelUISystem+State`  
- `Game.UI.Menu.AssetUploadPanelUISystem+<>c`  
- `Game.UI.Menu.AssetUploadPanelUISystem+<>c__DisplayClass102_0`  
- `Game.UI.Menu.AssetUploadPanelUISystem+<>c__DisplayClass64_0`  
- `Game.UI.Menu.AssetUploadPanelUISystem+<>c__DisplayClass77_0`  
- `Game.UI.Menu.AssetUploadPanelUISystem+<>c__DisplayClass78_0`  
- `Game.UI.Menu.AssetUploadPanelUISystem+<>c__DisplayClass81_0`  
- `Game.UI.Menu.AssetUploadPanelUISystem+<>c__DisplayClass86_0`  
- `Game.UI.Menu.AssetUploadPanelUISystem+<>c__DisplayClass94_0`  
- `Game.UI.Menu.AssetUploadPanelUISystem+<BeginSubmit>d__77`  
- `Game.UI.Menu.AssetUploadPanelUISystem+<Cancel>d__79`  
- `Game.UI.Menu.AssetUploadPanelUISystem+<FinalizeSubmit>d__78`  
- `Game.UI.Menu.AssetUploadPanelUISystem+<GetExistingMods>d__101`  
- `Game.UI.Menu.AssetUploadPanelUISystem+<GetPreviews>d__99`  
- `Game.UI.Menu.AssetUploadPanelUISystem+<SetInfoFromExisting>d__102`  
- `Game.UI.Menu.AssetUploadPanelUISystem+<SyncPlatformData>d__73`  

