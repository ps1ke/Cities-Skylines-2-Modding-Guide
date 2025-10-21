# Game.UI.Menu.AssetUploadPanelUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class AssetUploadPanelUISystem : Game.UI.UISystemBase
{
    private Game.UI.Menu.NotificationUISystem m_NotificationUISystem;
    private Game.UI.Editor.AssetPickerAdapter m_PreviewPickerAdapter;
    private Game.UI.Menu.PdxAssetUploadHandle m_UploadHandle;
    private System.Boolean m_AllowManualFileCopy;
    private Game.UI.Menu.AssetUploadPanelUISystem+State m_State;
    private Game.UI.Widgets.IWidget[] m_MainPanel;
    private Game.UI.Editor.LargeIconButton m_PreviewPickerButton;
    private Game.UI.Editor.ExternalLinkField m_ExternalLinkField;
    private Game.UI.Widgets.IconButtonGroup m_Screenshots;
    private Game.UI.Widgets.LayoutContainer m_PlatformResult;
    private Game.UI.Editor.Widgets.ItemPickerPopup<System.Int32> m_ExistingModPopup;
    private Game.UI.Widgets.PopupValueField<System.Int32> m_ExistingModField;
    private Game.UI.Widgets.Button m_SubmitButton;
    private Game.UI.Editor.ListField m_AssetList;
    private Game.UI.Widgets.PopupValueField<Game.Prefabs.PrefabBase> m_AssetListPopup;
    private Game.UI.Editor.ListField m_TagsList;
    private Game.UI.Widgets.PopupValueField<System.String> m_TagsListPopup;
    private Game.UI.Widgets.LayoutContainer m_DLCInfo;
    private System.Boolean m_DLCInfoVisible;
    private Game.UI.Widgets.IWidget[] m_PreviewPickerPanel;
    private Game.UI.Widgets.Button m_SelectPreviewButton;
    public System.Action<System.Collections.Generic.IList<Game.UI.Widgets.IWidget>> onChildrenChange;
    private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children;
    private static readonly System.String kNotificationID;
    private static readonly Game.UI.Localization.LocalizedString kNone;
    private static readonly System.String kFailureLabel;
    private static readonly System.String kSubmittingLabel;
    private static readonly System.String kCompleteLabel;
    private static readonly System.String kSubmitLabel;
    private static readonly System.String kNoInternetConnectionLabel;
    private static readonly System.String kNotLoggedInLabel;
    private static readonly System.String kNoSocialProfile;
    private static readonly System.String kOpenProfilePage;
    private static readonly System.String kDLCListLabel;
    private static readonly System.Single kNotificationDelay;

    private System.Boolean nameError { private get; }
    private System.Boolean shortDescirptionError { private get; }
    private System.Boolean longDescipriontError { private get; }
    private System.Boolean forumLinkError { private get; }
    private System.Boolean externalLinkError { private get; }
    private System.Boolean changelogError { private get; }
    private System.Boolean versionError { private get; }
    private System.Boolean noInternetConnection { private get; }
    private System.Boolean notLoggedIn { private get; }
    private System.Boolean anyError { private get; }
    private System.Boolean disableSubmit { private get; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; }

    public AssetUploadPanelUISystem();

    private System.Void <OnCreate>b__60_0();
    private System.Boolean <OnCreate>b__60_1();
    private System.Boolean <OnCreate>b__60_10();
    private System.Int32 <OnCreate>b__60_11();
    private System.Void <OnCreate>b__60_12(System.Int32 value);
    private System.Boolean <OnCreate>b__60_13();
    private System.Boolean <OnCreate>b__60_14();
    private System.String <OnCreate>b__60_15();
    private System.Void <OnCreate>b__60_16(System.String value);
    private System.Boolean <OnCreate>b__60_18();
    private System.Boolean <OnCreate>b__60_19();
    private System.String <OnCreate>b__60_2();
    private System.String <OnCreate>b__60_20();
    private System.Void <OnCreate>b__60_21(System.String value);
    private System.String <OnCreate>b__60_22();
    private System.Void <OnCreate>b__60_23(System.String value);
    private System.Boolean <OnCreate>b__60_24();
    private System.String <OnCreate>b__60_25();
    private System.Void <OnCreate>b__60_26(System.String value);
    private System.Boolean <OnCreate>b__60_27();
    private System.String <OnCreate>b__60_28();
    private System.Void <OnCreate>b__60_29(System.String value);
    private System.Void <OnCreate>b__60_3(System.String value);
    private System.Boolean <OnCreate>b__60_30();
    private System.Boolean <OnCreate>b__60_32();
    private Game.UI.Editor.ProgressIndicator+State <OnCreate>b__60_33();
    private System.Boolean <OnCreate>b__60_34();
    private System.Boolean <OnCreate>b__60_35();
    private System.Void <OnCreate>b__60_36();
    private System.Boolean <OnCreate>b__60_4();
    private System.Boolean <OnCreate>b__60_5();
    private System.Void <OnCreate>b__60_6(System.Boolean value);
    private System.Int32 <OnCreate>b__60_7();
    private System.Void <OnCreate>b__60_8(System.Int32 value);
    private System.Boolean <OnCreate>b__60_9();
    private System.Void <RefreshScreenshots>b__81_1();
    private System.Void <ReportNoSocial>b__69_0();
    private System.Void <SyncPlatformData>b__73_0();
    private System.Void AddScreenshot(Colossal.Hash128 guid);
    private System.Void BeginSubmit();
    private System.Void Cancel();
    private System.Void ClearState();
    public System.Boolean Close();
    private System.Void ClosePreviewPickerPanel(System.Action<Colossal.Hash128> callback);
    private System.Void FinalizeSubmit();
    private System.Collections.Generic.IEnumerable<Game.UI.Editor.Widgets.ItemPickerPopup<System.Int32>> GetExistingMods();
    private static Game.UI.Editor.ListField+Item GetItem(Colossal.IO.AssetDatabase.AssetData asset, System.Boolean removable, System.Boolean mainAsset);
    private static System.String GetLabel(Colossal.IO.AssetDatabase.AssetData asset);
    private System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> GetPreviews(System.Boolean excludeScreenshots);
    private System.String GetSubmitButtonLabel();
    private System.Void OnAddPrefab(Game.Prefabs.PrefabBase prefab);
    private System.Void OnAddTag(System.String tag);
    protected virtual System.Void OnCreate();
    private System.Void OnRemoveAdditionalAsset(System.Int32 index);
    private System.Void OnRemoveTag(System.Int32 index);
    protected virtual System.Void OnUpdate();
    private System.Void OpenPreviewPickerPanel(System.Action<Colossal.Hash128> callback, Colossal.Hash128 defaultSelection, System.Boolean excludeScreenshots);
    private System.Void RefreshAssetList();
    private System.Void RefreshAuthorMods();
    private System.Void RefreshDLCList();
    private System.Void RefreshExternalLinks();
    private System.Void RefreshPreview();
    private System.Void RefreshScreenshots();
    private System.Void RefreshSocialProfileStatus();
    private System.Void RefreshSubmitButtonLabel();
    private System.Void RefreshTags();
    private System.Void RemoveScreenshot(System.Int32 index);
    private System.Void ReportError(Colossal.PSI.Common.IModsUploadSupport+ModOperationResult result);
    private System.Void ReportLocalDataNotFound();
    private System.Void ReportNoSocial();
    private System.Void ReportSubmitting();
    private System.Void ReportSuccess();
    private System.Void ReportSyncing();
    private System.Void SetChildren(Game.UI.Widgets.IWidget[] newChildren);
    private System.Void SetInfoFromExisting();
    private System.Void SetPreview(Colossal.Hash128 guid);
    private System.Boolean ShouldShowInPrefabPicker(Game.Prefabs.PrefabBase prefab);
    public System.Void Show(Colossal.IO.AssetDatabase.AssetData mainAsset, System.Boolean allowManualFileCopy);
    private System.Void Submit();
    private System.Void SyncPlatformData();
    private System.Boolean TryMatchDLC(System.String internalName, Colossal.PSI.Common.IModsUploadSupport+DLCTag& dlc);
}
```


## Fields

- `private Game.UI.Menu.NotificationUISystem m_NotificationUISystem`  

```csharp
private Game.UI.Menu.NotificationUISystem m_NotificationUISystem;
```

- `private Game.UI.Editor.AssetPickerAdapter m_PreviewPickerAdapter`  

```csharp
private Game.UI.Editor.AssetPickerAdapter m_PreviewPickerAdapter;
```

- `private Game.UI.Menu.PdxAssetUploadHandle m_UploadHandle`  

```csharp
private Game.UI.Menu.PdxAssetUploadHandle m_UploadHandle;
```

- `private System.Boolean m_AllowManualFileCopy`  

```csharp
private System.Boolean m_AllowManualFileCopy;
```

- `private Game.UI.Menu.AssetUploadPanelUISystem+State m_State`  

```csharp
private Game.UI.Menu.AssetUploadPanelUISystem+State m_State;
```

- `private Game.UI.Widgets.IWidget[] m_MainPanel`  

```csharp
private Game.UI.Widgets.IWidget[] m_MainPanel;
```

- `private Game.UI.Editor.LargeIconButton m_PreviewPickerButton`  

```csharp
private Game.UI.Editor.LargeIconButton m_PreviewPickerButton;
```

- `private Game.UI.Editor.ExternalLinkField m_ExternalLinkField`  

```csharp
private Game.UI.Editor.ExternalLinkField m_ExternalLinkField;
```

- `private Game.UI.Widgets.IconButtonGroup m_Screenshots`  

```csharp
private Game.UI.Widgets.IconButtonGroup m_Screenshots;
```

- `private Game.UI.Widgets.LayoutContainer m_PlatformResult`  

```csharp
private Game.UI.Widgets.LayoutContainer m_PlatformResult;
```

- `private Game.UI.Editor.Widgets.ItemPickerPopup<System.Int32> m_ExistingModPopup`  

```csharp
private Game.UI.Editor.Widgets.ItemPickerPopup<System.Int32> m_ExistingModPopup;
```

- `private Game.UI.Widgets.PopupValueField<System.Int32> m_ExistingModField`  

```csharp
private Game.UI.Widgets.PopupValueField<System.Int32> m_ExistingModField;
```

- `private Game.UI.Widgets.Button m_SubmitButton`  

```csharp
private Game.UI.Widgets.Button m_SubmitButton;
```

- `private Game.UI.Editor.ListField m_AssetList`  

```csharp
private Game.UI.Editor.ListField m_AssetList;
```

- `private Game.UI.Widgets.PopupValueField<Game.Prefabs.PrefabBase> m_AssetListPopup`  

```csharp
private Game.UI.Widgets.PopupValueField<Game.Prefabs.PrefabBase> m_AssetListPopup;
```

- `private Game.UI.Editor.ListField m_TagsList`  

```csharp
private Game.UI.Editor.ListField m_TagsList;
```

- `private Game.UI.Widgets.PopupValueField<System.String> m_TagsListPopup`  

```csharp
private Game.UI.Widgets.PopupValueField<System.String> m_TagsListPopup;
```

- `private Game.UI.Widgets.LayoutContainer m_DLCInfo`  

```csharp
private Game.UI.Widgets.LayoutContainer m_DLCInfo;
```

- `private System.Boolean m_DLCInfoVisible`  

```csharp
private System.Boolean m_DLCInfoVisible;
```

- `private Game.UI.Widgets.IWidget[] m_PreviewPickerPanel`  

```csharp
private Game.UI.Widgets.IWidget[] m_PreviewPickerPanel;
```

- `private Game.UI.Widgets.Button m_SelectPreviewButton`  

```csharp
private Game.UI.Widgets.Button m_SelectPreviewButton;
```

- `public System.Action<System.Collections.Generic.IList<Game.UI.Widgets.IWidget>> onChildrenChange`  

```csharp
public System.Action<System.Collections.Generic.IList<Game.UI.Widgets.IWidget>> onChildrenChange;
```

- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children`  

```csharp
private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children;
```

- `private static readonly System.String kNotificationID`  

```csharp
private static readonly System.String kNotificationID;
```

- `private static readonly Game.UI.Localization.LocalizedString kNone`  

```csharp
private static readonly Game.UI.Localization.LocalizedString kNone;
```

- `private static readonly System.String kFailureLabel`  

```csharp
private static readonly System.String kFailureLabel;
```

- `private static readonly System.String kSubmittingLabel`  

```csharp
private static readonly System.String kSubmittingLabel;
```

- `private static readonly System.String kCompleteLabel`  

```csharp
private static readonly System.String kCompleteLabel;
```

- `private static readonly System.String kSubmitLabel`  

```csharp
private static readonly System.String kSubmitLabel;
```

- `private static readonly System.String kNoInternetConnectionLabel`  

```csharp
private static readonly System.String kNoInternetConnectionLabel;
```

- `private static readonly System.String kNotLoggedInLabel`  

```csharp
private static readonly System.String kNotLoggedInLabel;
```

- `private static readonly System.String kNoSocialProfile`  

```csharp
private static readonly System.String kNoSocialProfile;
```

- `private static readonly System.String kOpenProfilePage`  

```csharp
private static readonly System.String kOpenProfilePage;
```

- `private static readonly System.String kDLCListLabel`  

```csharp
private static readonly System.String kDLCListLabel;
```

- `private static readonly System.Single kNotificationDelay`  

```csharp
private static readonly System.Single kNotificationDelay;
```


## Properties

- `private System.Boolean nameError { private get }`  

```csharp
private System.Boolean nameError { private get; }
```

- `private System.Boolean shortDescirptionError { private get }`  

```csharp
private System.Boolean shortDescirptionError { private get; }
```

- `private System.Boolean longDescipriontError { private get }`  

```csharp
private System.Boolean longDescipriontError { private get; }
```

- `private System.Boolean forumLinkError { private get }`  

```csharp
private System.Boolean forumLinkError { private get; }
```

- `private System.Boolean externalLinkError { private get }`  

```csharp
private System.Boolean externalLinkError { private get; }
```

- `private System.Boolean changelogError { private get }`  

```csharp
private System.Boolean changelogError { private get; }
```

- `private System.Boolean versionError { private get }`  

```csharp
private System.Boolean versionError { private get; }
```

- `private System.Boolean noInternetConnection { private get }`  

```csharp
private System.Boolean noInternetConnection { private get; }
```

- `private System.Boolean notLoggedIn { private get }`  

```csharp
private System.Boolean notLoggedIn { private get; }
```

- `private System.Boolean anyError { private get }`  

```csharp
private System.Boolean anyError { private get; }
```

- `private System.Boolean disableSubmit { private get }`  

```csharp
private System.Boolean disableSubmit { private get; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; }
```


## Constructors

- `public AssetUploadPanelUISystem()`  

```csharp
public AssetUploadPanelUISystem();
```


## Methods

- `private <OnCreate>b__60_0() : System.Void`  

```csharp
private System.Void <OnCreate>b__60_0();
```

- `private <OnCreate>b__60_1() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__60_1();
```

- `private <OnCreate>b__60_10() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__60_10();
```

- `private <OnCreate>b__60_11() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__60_11();
```

- `private <OnCreate>b__60_12(System.Int32 value) : System.Void`  

```csharp
private System.Void <OnCreate>b__60_12(System.Int32 value);
```

- `private <OnCreate>b__60_13() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__60_13();
```

- `private <OnCreate>b__60_14() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__60_14();
```

- `private <OnCreate>b__60_15() : System.String`  

```csharp
private System.String <OnCreate>b__60_15();
```

- `private <OnCreate>b__60_16(System.String value) : System.Void`  

```csharp
private System.Void <OnCreate>b__60_16(System.String value);
```

- `private <OnCreate>b__60_18() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__60_18();
```

- `private <OnCreate>b__60_19() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__60_19();
```

- `private <OnCreate>b__60_2() : System.String`  

```csharp
private System.String <OnCreate>b__60_2();
```

- `private <OnCreate>b__60_20() : System.String`  

```csharp
private System.String <OnCreate>b__60_20();
```

- `private <OnCreate>b__60_21(System.String value) : System.Void`  

```csharp
private System.Void <OnCreate>b__60_21(System.String value);
```

- `private <OnCreate>b__60_22() : System.String`  

```csharp
private System.String <OnCreate>b__60_22();
```

- `private <OnCreate>b__60_23(System.String value) : System.Void`  

```csharp
private System.Void <OnCreate>b__60_23(System.String value);
```

- `private <OnCreate>b__60_24() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__60_24();
```

- `private <OnCreate>b__60_25() : System.String`  

```csharp
private System.String <OnCreate>b__60_25();
```

- `private <OnCreate>b__60_26(System.String value) : System.Void`  

```csharp
private System.Void <OnCreate>b__60_26(System.String value);
```

- `private <OnCreate>b__60_27() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__60_27();
```

- `private <OnCreate>b__60_28() : System.String`  

```csharp
private System.String <OnCreate>b__60_28();
```

- `private <OnCreate>b__60_29(System.String value) : System.Void`  

```csharp
private System.Void <OnCreate>b__60_29(System.String value);
```

- `private <OnCreate>b__60_3(System.String value) : System.Void`  

```csharp
private System.Void <OnCreate>b__60_3(System.String value);
```

- `private <OnCreate>b__60_30() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__60_30();
```

- `private <OnCreate>b__60_32() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__60_32();
```

- `private <OnCreate>b__60_33() : Game.UI.Editor.ProgressIndicator+State`  

```csharp
private Game.UI.Editor.ProgressIndicator+State <OnCreate>b__60_33();
```

- `private <OnCreate>b__60_34() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__60_34();
```

- `private <OnCreate>b__60_35() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__60_35();
```

- `private <OnCreate>b__60_36() : System.Void`  

```csharp
private System.Void <OnCreate>b__60_36();
```

- `private <OnCreate>b__60_4() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__60_4();
```

- `private <OnCreate>b__60_5() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__60_5();
```

- `private <OnCreate>b__60_6(System.Boolean value) : System.Void`  

```csharp
private System.Void <OnCreate>b__60_6(System.Boolean value);
```

- `private <OnCreate>b__60_7() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__60_7();
```

- `private <OnCreate>b__60_8(System.Int32 value) : System.Void`  

```csharp
private System.Void <OnCreate>b__60_8(System.Int32 value);
```

- `private <OnCreate>b__60_9() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__60_9();
```

- `private <RefreshScreenshots>b__81_1() : System.Void`  

```csharp
private System.Void <RefreshScreenshots>b__81_1();
```

- `private <ReportNoSocial>b__69_0() : System.Void`  

```csharp
private System.Void <ReportNoSocial>b__69_0();
```

- `private <SyncPlatformData>b__73_0() : System.Void`  

```csharp
private System.Void <SyncPlatformData>b__73_0();
```

- `private AddScreenshot(Colossal.Hash128 guid) : System.Void`  

```csharp
private System.Void AddScreenshot(Colossal.Hash128 guid);
```

- `private BeginSubmit() : System.Void`  

```csharp
private System.Void BeginSubmit();
```

- `private Cancel() : System.Void`  

```csharp
private System.Void Cancel();
```

- `private ClearState() : System.Void`  

```csharp
private System.Void ClearState();
```

- `public Close() : System.Boolean`  

```csharp
public System.Boolean Close();
```

- `private ClosePreviewPickerPanel(System.Action<Colossal.Hash128> callback) : System.Void`  

```csharp
private System.Void ClosePreviewPickerPanel(System.Action<Colossal.Hash128> callback);
```

- `private FinalizeSubmit() : System.Void`  

```csharp
private System.Void FinalizeSubmit();
```

- `private GetExistingMods() : System.Collections.Generic.IEnumerable<Game.UI.Editor.Widgets.ItemPickerPopup<System.Int32>>`  

```csharp
private System.Collections.Generic.IEnumerable<Game.UI.Editor.Widgets.ItemPickerPopup<System.Int32>> GetExistingMods();
```

- `private static GetItem(Colossal.IO.AssetDatabase.AssetData asset, System.Boolean removable, System.Boolean mainAsset) : Game.UI.Editor.ListField+Item`  

```csharp
private static Game.UI.Editor.ListField+Item GetItem(Colossal.IO.AssetDatabase.AssetData asset, System.Boolean removable, System.Boolean mainAsset);
```

- `private static GetLabel(Colossal.IO.AssetDatabase.AssetData asset) : System.String`  

```csharp
private static System.String GetLabel(Colossal.IO.AssetDatabase.AssetData asset);
```

- `private GetPreviews(System.Boolean excludeScreenshots = False) : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  

```csharp
private System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> GetPreviews(System.Boolean excludeScreenshots);
```

- `private GetSubmitButtonLabel() : System.String`  

```csharp
private System.String GetSubmitButtonLabel();
```

- `private OnAddPrefab(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private System.Void OnAddPrefab(Game.Prefabs.PrefabBase prefab);
```

- `private OnAddTag(System.String tag) : System.Void`  

```csharp
private System.Void OnAddTag(System.String tag);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `private OnRemoveAdditionalAsset(System.Int32 index) : System.Void`  

```csharp
private System.Void OnRemoveAdditionalAsset(System.Int32 index);
```

- `private OnRemoveTag(System.Int32 index) : System.Void`  

```csharp
private System.Void OnRemoveTag(System.Int32 index);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private OpenPreviewPickerPanel(System.Action<Colossal.Hash128> callback, Colossal.Hash128 defaultSelection = null, System.Boolean excludeScreenshots = False) : System.Void`  

```csharp
private System.Void OpenPreviewPickerPanel(System.Action<Colossal.Hash128> callback, Colossal.Hash128 defaultSelection, System.Boolean excludeScreenshots);
```

- `private RefreshAssetList() : System.Void`  

```csharp
private System.Void RefreshAssetList();
```

- `private RefreshAuthorMods() : System.Void`  

```csharp
private System.Void RefreshAuthorMods();
```

- `private RefreshDLCList() : System.Void`  

```csharp
private System.Void RefreshDLCList();
```

- `private RefreshExternalLinks() : System.Void`  

```csharp
private System.Void RefreshExternalLinks();
```

- `private RefreshPreview() : System.Void`  

```csharp
private System.Void RefreshPreview();
```

- `private RefreshScreenshots() : System.Void`  

```csharp
private System.Void RefreshScreenshots();
```

- `private RefreshSocialProfileStatus() : System.Void`  

```csharp
private System.Void RefreshSocialProfileStatus();
```

- `private RefreshSubmitButtonLabel() : System.Void`  

```csharp
private System.Void RefreshSubmitButtonLabel();
```

- `private RefreshTags() : System.Void`  

```csharp
private System.Void RefreshTags();
```

- `private RemoveScreenshot(System.Int32 index) : System.Void`  

```csharp
private System.Void RemoveScreenshot(System.Int32 index);
```

- `private ReportError(Colossal.PSI.Common.IModsUploadSupport+ModOperationResult result) : System.Void`  

```csharp
private System.Void ReportError(Colossal.PSI.Common.IModsUploadSupport+ModOperationResult result);
```

- `private ReportLocalDataNotFound() : System.Void`  

```csharp
private System.Void ReportLocalDataNotFound();
```

- `private ReportNoSocial() : System.Void`  

```csharp
private System.Void ReportNoSocial();
```

- `private ReportSubmitting() : System.Void`  

```csharp
private System.Void ReportSubmitting();
```

- `private ReportSuccess() : System.Void`  

```csharp
private System.Void ReportSuccess();
```

- `private ReportSyncing() : System.Void`  

```csharp
private System.Void ReportSyncing();
```

- `private SetChildren(Game.UI.Widgets.IWidget[] newChildren) : System.Void`  

```csharp
private System.Void SetChildren(Game.UI.Widgets.IWidget[] newChildren);
```

- `private SetInfoFromExisting() : System.Void`  

```csharp
private System.Void SetInfoFromExisting();
```

- `private SetPreview(Colossal.Hash128 guid) : System.Void`  

```csharp
private System.Void SetPreview(Colossal.Hash128 guid);
```

- `private ShouldShowInPrefabPicker(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
private System.Boolean ShouldShowInPrefabPicker(Game.Prefabs.PrefabBase prefab);
```

- `public Show(Colossal.IO.AssetDatabase.AssetData mainAsset, System.Boolean allowManualFileCopy = False) : System.Void`  

```csharp
public System.Void Show(Colossal.IO.AssetDatabase.AssetData mainAsset, System.Boolean allowManualFileCopy);
```

- `private Submit() : System.Void`  

```csharp
private System.Void Submit();
```

- `private SyncPlatformData() : System.Void`  

```csharp
private System.Void SyncPlatformData();
```

- `private TryMatchDLC(System.String internalName, Colossal.PSI.Common.IModsUploadSupport+DLCTag& dlc) : System.Boolean`  

```csharp
private System.Boolean TryMatchDLC(System.String internalName, Colossal.PSI.Common.IModsUploadSupport+DLCTag& dlc);
```


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

