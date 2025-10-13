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
[Preserve]
	public AssetUploadPanelUISystem()
	{
	}
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
private void AddScreenshot(Colossal.Hash128 guid)
	{
		if (AssetDatabase.global.TryGetAsset(guid, out AssetData asset))
		{
			m_UploadHandle.AddScreenshot(asset);
		}
		RefreshScreenshots();
	}
```

- `private BeginSubmit() : System.Void`  

```csharp
private async void BeginSubmit()
	{
		IModsUploadSupport.ModOperationResult result = await m_UploadHandle.BeginSubmit();
		if (result.m_Success)
		{
			if (m_AllowManualFileCopy)
			{
				GameManager.instance.RunOnMainThread(delegate
				{
					GUIUtility.systemCopyBuffer = m_UploadHandle.GetAbsoluteContentPath();
					GameManager.instance.userInterface.paradoxBindings.PushDialog(new ParadoxBindings.MultiOptionDialog("Ready to upload", "A work-in-progress folder has been created in " + m_UploadHandle.GetAbsoluteContentPath() + " where you may now copy any additional files you wish to share. Press Submit once you're ready to finalize the upload.", new ParadoxBindings.MultiOptionDialog.Option
					{
						m_Id = "Submit",
						m_OnSelect = FinalizeSubmit
					}, new ParadoxBindings.MultiOptionDialog.Option
					{
						m_Id = "Cancel",
						m_OnSelect = Cancel
					}));
				});
			}
			else
			{
				FinalizeSubmit();
			}
		}
		else
		{
			GameManager.instance.RunOnMainThread(delegate
			{
				ReportError(result);
			});
		}
	}
```

- `private Cancel() : System.Void`  

```csharp
private async void Cancel()
	{
		m_NotificationUISystem.RemoveNotification(kNotificationID);
		await m_UploadHandle.Cleanup();
		ClearState();
	}
```

- `private ClearState() : System.Void`  

```csharp
private void ClearState()
	{
		m_State = State.Ready;
		m_PlatformResult.children = Array.Empty<IWidget>();
		RefreshSubmitButtonLabel();
	}
```

- `public Close() : System.Boolean`  

```csharp
public bool Close()
	{
		if (children == m_PreviewPickerPanel)
		{
			SetChildren(m_MainPanel);
			return false;
		}
		if (m_ExistingModField.expanded)
		{
			m_ExistingModField.expanded = false;
			return false;
		}
		if (m_AssetListPopup != null && m_AssetListPopup.expanded)
		{
			m_AssetListPopup.expanded = false;
			return false;
		}
		return true;
	}
```

- `private ClosePreviewPickerPanel(System.Action<Colossal.Hash128> callback) : System.Void`  

```csharp
private void ClosePreviewPickerPanel(Action<Colossal.Hash128> callback)
	{
		SetChildren(m_MainPanel);
		callback?.Invoke(m_PreviewPickerAdapter.selectedItem.guid);
	}
```

- `private FinalizeSubmit() : System.Void`  

```csharp
private async void FinalizeSubmit()
	{
		IModsUploadSupport.ModOperationResult result = await m_UploadHandle.FinalizeSubmit();
		GameManager.instance.RunOnMainThread(delegate
		{
			if (!result.m_Success)
			{
				ReportError(result);
			}
			else
			{
				ReportSuccess();
			}
		});
	}
```

- `private GetExistingMods() : System.Collections.Generic.IEnumerable<Game.UI.Editor.Widgets.ItemPickerPopup<System.Int32>>`  

```csharp
private IEnumerable<ItemPickerPopup<int>.Item> GetExistingMods()
	{
		yield return new ItemPickerPopup<int>.Item
		{
			m_Value = -1,
			displayName = kNone
		};
		foreach (IModsUploadSupport.ModInfo authorMod in m_UploadHandle.authorMods)
		{
			ItemPickerPopup<int>.Item item = new ItemPickerPopup<int>.Item
			{
				m_Value = authorMod.m_PublishedID,
				displayName = LocalizedString.Value(authorMod.m_DisplayName)
			};
			string[] array = new string[2];
			int publishedID = authorMod.m_PublishedID;
			array[0] = publishedID.ToString();
			array[1] = authorMod.m_DisplayName;
			item.m_SearchTerms = array;
			yield return item;
		}
	}
```

- `private static GetItem(Colossal.IO.AssetDatabase.AssetData asset, System.Boolean removable, System.Boolean mainAsset) : Game.UI.Editor.ListField+Item`  

```csharp
private static ListField.Item GetItem(AssetData asset, bool removable, bool mainAsset)
	{
		ListField.Item result = new ListField.Item
		{
			m_Label = GetLabel(asset),
			m_Removable = removable,
			m_Data = asset
		};
		if (asset is PrefabAsset prefabAsset)
		{
			HashSet<AssetData> hashSet = new HashSet<AssetData>();
			AssetUploadUtils.CollectPrefabAssetDependencies(prefabAsset, hashSet, mainAsset);
			result.m_SubItems = hashSet.Where((AssetData dep) => dep != asset && dep is PrefabAsset).Select(GetLabel).ToArray();
		}
		return result;
	}
```

- `private static GetLabel(Colossal.IO.AssetDatabase.AssetData asset) : System.String`  

```csharp
private static string GetLabel(AssetData asset)
	{
		SourceMeta meta = asset.GetMeta();
		if (meta.platformID > 0)
		{
			return $"{asset.name} ({meta.platformID})";
		}
		if (meta.packaged)
		{
			return asset.name + " (" + meta.packageName + ")";
		}
		return asset.name;
	}
```

- `private GetPreviews(System.Boolean excludeScreenshots = False) : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  

```csharp
private IEnumerable<AssetItem> GetPreviews(bool excludeScreenshots = false)
	{
		HashSet<IAssetData> screenshots = (excludeScreenshots ? new HashSet<IAssetData>(m_UploadHandle.screenshots) : null);
		foreach (AssetData originalPreview in m_UploadHandle.originalPreviews)
		{
			if (!excludeScreenshots || !screenshots.Contains(originalPreview))
			{
				yield return new AssetItem
				{
					guid = originalPreview.id,
					image = AssetUploadUtils.GetImageURI(originalPreview)
				};
			}
		}
		foreach (ImageAsset asset in AssetDatabase.global.GetAssets(SearchFilter<ImageAsset>.ByCondition((ImageAsset a) => a.GetMeta().subPath?.StartsWith(ScreenUtility.kScreenshotDirectory) ?? false)))
		{
			if (!excludeScreenshots || !screenshots.Contains(asset))
			{
				yield return new AssetItem
				{
					guid = asset.id,
					fileName = asset.name,
					displayName = asset.name,
					image = asset.ToUri()
				};
			}
		}
	}
```

- `private GetSubmitButtonLabel() : System.String`  

```csharp
private string GetSubmitButtonLabel()
	{
		if (m_State == State.Success)
		{
			return kCompleteLabel;
		}
		if (noInternetConnection)
		{
			return kNoInternetConnectionLabel;
		}
		if (notLoggedIn)
		{
			return kNotLoggedInLabel;
		}
		return kSubmitLabel;
	}
```

- `private OnAddPrefab(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private void OnAddPrefab(PrefabBase prefab)
	{
		m_AssetListPopup.expanded = false;
		if (!(prefab == null))
		{
			m_UploadHandle.AddAdditionalAsset(prefab.asset);
			RefreshAssetList();
			RefreshDLCList();
		}
	}
```

- `private OnAddTag(System.String tag) : System.Void`  

```csharp
private void OnAddTag(string tag)
	{
		m_TagsListPopup.expanded = false;
		if (tag != null)
		{
			m_UploadHandle.AddAdditionalTag(tag);
		}
		RefreshTags();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_NotificationUISystem = base.World.GetOrCreateSystemManaged<NotificationUISystem>();
		m_ExistingModPopup = new ItemPickerPopup<int>(hasFooter: false);
		IWidget[] array = new IWidget[1];
		Scrollable scrollable = new Scrollable();
		IWidget[] array2 = new IWidget[16];
		LargeIconButton obj = new LargeIconButton
		{
			action = delegate
			{
				OpenPreviewPickerPanel(SetPreview, m_UploadHandle.preview?.id ?? default(Identifier));
			}
		};
		LargeIconButton largeIconButton = obj;
		m_PreviewPickerButton = obj;
		array2[0] = largeIconButton;
		Group obj2 = new Group
		{
			displayName = kDLCListLabel
		};
		Group obj3 = obj2;
		IWidget[] array3 = new IWidget[1];
		Column obj4 = new Column
		{
			flex = new FlexLayout(1f, 0f, -1),
			children = new List<IWidget>()
		};
		LayoutContainer layoutContainer = obj4;
		m_DLCInfo = obj4;
		array3[0] = layoutContainer;
		obj3.children = array3;
		obj2.hidden = () => !m_DLCInfoVisible;
		array2[1] = obj2;
		array2[2] = new StringInputFieldWithError
		{
			displayName = "Menu.ASSET_NAME",
			errorMessage = "Menu.ASSET_ERROR_NAME",
			accessor = new DelegateAccessor<string>(() => m_UploadHandle.modInfo.m_DisplayName, delegate(string value)
			{
				IModsUploadSupport.ModInfo modInfo = m_UploadHandle.modInfo;
				modInfo.m_DisplayName = value;
				m_UploadHandle.modInfo = modInfo;
			}),
			error = () => nameError,
			maxLength = 60
		};
		array2[3] = new ToggleField
		{
			displayName = "Menu.ASSET_UPDATE_EXISTING",
			accessor = new DelegateAccessor<bool>(() => m_UploadHandle.updateExisting, delegate(bool value)
			{
				m_UploadHandle.updateExisting = value;
			})
		};
		PopupValueField<int> obj5 = new PopupValueField<int>
		{
			displayName = "Menu.ASSET_EXISTING",
			accessor = new DelegateAccessor<int>(() => m_UploadHandle.modInfo.m_PublishedID, delegate(int value)
			{
				IModsUploadSupport.ModInfo modInfo = m_UploadHandle.modInfo;
				modInfo.m_PublishedID = value;
				m_UploadHandle.modInfo = modInfo;
				SetInfoFromExisting();
			}),
			hidden = () => !m_UploadHandle.updateExisting || m_UploadHandle.authorMods.Count == 0,
			popup = m_ExistingModPopup
		};
		PopupValueField<int> popupValueField = obj5;
		m_ExistingModField = obj5;
		array2[4] = popupValueField;
		array2[5] = new IntInputField
		{
			displayName = "Menu.ASSET_EXISTING_ID",
			hidden = () => !m_UploadHandle.updateExisting || m_UploadHandle.authorMods.Count > 0,
			min = 0,
			accessor = new DelegateAccessor<int>(() => m_UploadHandle.modInfo.m_PublishedID, delegate(int value)
			{
				IModsUploadSupport.ModInfo modInfo = m_UploadHandle.modInfo;
				modInfo.m_PublishedID = value;
				m_UploadHandle.modInfo = modInfo;
			})
		};
		array2[6] = new StringInputFieldWithError
		{
			displayName = "Menu.ASSET_VERSION",
			errorMessage = "Menu.ASSET_ERROR_VERSION",
			error = () => versionError,
			hidden = () => !m_UploadHandle.updateExisting,
			accessor = new DelegateAccessor<string>(() => m_UploadHandle.modInfo.m_UserModVersion, delegate(string value)
			{
				if (value.All((char c) => char.IsLetterOrDigit(c) || c == '.' || c == '-' || c == '_'))
				{
					IModsUploadSupport.ModInfo modInfo = m_UploadHandle.modInfo;
					modInfo.m_UserModVersion = value;
					m_UploadHandle.modInfo = modInfo;
				}
			}),
			maxLength = 20
		};
		array2[7] = new StringInputFieldWithError
		{
			displayName = "Menu.ASSET_CHANGELOG",
			errorMessage = "Menu.ASSET_ERROR_EMPTY_CHANGELOG",
			error = () => changelogError,
			multiline = StringInputField.kDefaultMultilines,
			hidden = () => !m_UploadHandle.updateExisting,
			accessor = new DelegateAccessor<string>(() => m_UploadHandle.modInfo.m_Changelog, delegate(string value)
			{
				IModsUploadSupport.ModInfo modInfo = m_UploadHandle.modInfo;
				modInfo.m_Changelog = value;
				m_UploadHandle.modInfo = modInfo;
			}),
			maxLength = 20000
		};
		array2[8] = new StringInputFieldWithError
		{
			displayName = "Menu.ASSET_SHORT_DESCRIPTION",
			errorMessage = "Menu.ASSET_ERROR_DESCRIPTION",
			accessor = new DelegateAccessor<string>(() => m_UploadHandle.modInfo.m_ShortDescription, delegate(string value)
			{
				IModsUploadSupport.ModInfo modInfo = m_UploadHandle.modInfo;
				modInfo.m_ShortDescription = value;
				m_UploadHandle.modInfo = modInfo;
			}),
			error = () => shortDescirptionError,
			maxLength = 200
		};
		array2[9] = new StringInputFieldWithError
		{
			displayName = "Menu.ASSET_LONG_DESCRIPTION",
			errorMessage = "Menu.ASSET_ERROR_DESCRIPTION",
			multiline = StringInputField.kDefaultMultilines,
			accessor = new DelegateAccessor<string>(() => m_UploadHandle.modInfo.m_LongDescription, delegate(string value)
			{
				IModsUploadSupport.ModInfo modInfo = m_UploadHandle.modInfo;
				modInfo.m_LongDescription = value;
				m_UploadHandle.modInfo = modInfo;
			}),
			error = () => longDescipriontError,
			maxLength = 20000
		};
		array2[10] = new StringInputFieldWithError
		{
			displayName = "Menu.ASSET_FORUM_LINK_LABEL",
			errorMessage = "Menu.ASSET_ERROR_LINK",
			accessor = new DelegateAccessor<string>(() => m_UploadHandle.modInfo.m_ForumLink, delegate(string value)
			{
				IModsUploadSupport.ModInfo modInfo = m_UploadHandle.modInfo;
				modInfo.m_ForumLink = value;
				m_UploadHandle.modInfo = modInfo;
			}),
			error = () => forumLinkError
		};
		array2[11] = new Group
		{
			displayName = "Menu.ASSET_EXTERNAL_LINKS",
			children = new IWidget[1] { m_ExternalLinkField = new ExternalLinkField() }
		};
		array2[12] = new Group
		{
			displayName = "Menu.ASSET_PREVIEW_SCREENSHOTS",
			children = new IWidget[1] { m_Screenshots = new IconButtonGroup() }
		};
		EditorSection editorSection = new EditorSection
		{
			displayName = "Paradox.ADDITIONAL_TAGS"
		};
		IWidget[] obj6 = new IWidget[2]
		{
			m_TagsList = new ListField(),
			null
		};
		PopupValueField<string> obj7 = new PopupValueField<string>
		{
			displayName = "Paradox.ADD_TAG",
			popup = new ItemPickerPopup<string>(hasFooter: false, hasImages: false),
			accessor = new DelegateAccessor<string>(() => string.Empty, OnAddTag),
			disabled = () => m_UploadHandle.tagCount >= ModTags.kMaxTags
		};
		PopupValueField<string> popupValueField2 = obj7;
		m_TagsListPopup = obj7;
		obj6[1] = popupValueField2;
		editorSection.children = obj6;
		array2[13] = editorSection;
		Row row = new Row
		{
			flex = new FlexLayout(1f, 0f, -1)
		};
		row.children = new IWidget[2]
		{
			m_PlatformResult = new Column
			{
				flex = new FlexLayout(1f, 1f, -1)
			},
			new ProgressIndicator
			{
				state = delegate
				{
					if (m_State == State.Processing)
					{
						return ProgressIndicator.State.Loading;
					}
					return (m_State != State.Failure && m_State != State.Disabled) ? ProgressIndicator.State.Success : ProgressIndicator.State.Failure;
				},
				hidden = () => m_State == State.Ready
			}
		};
		array2[14] = row;
		array2[15] = (m_SubmitButton = new Button
		{
			displayName = kSubmitLabel,
			action = Submit,
			disabled = () => disableSubmit
		});
		scrollable.children = array2;
		array[0] = scrollable;
		m_MainPanel = array;
		if (m_AssetList != null)
		{
			ListField assetList = m_AssetList;
			assetList.onItemRemoved = (Action<int>)Delegate.Combine(assetList.onItemRemoved, new Action<int>(OnRemoveAdditionalAsset));
		}
		ListField tagsList = m_TagsList;
		tagsList.onItemRemoved = (Action<int>)Delegate.Combine(tagsList.onItemRemoved, new Action<int>(OnRemoveTag));
		m_PreviewPickerAdapter = new AssetPickerAdapter(GetPreviews(), 4);
		IWidget[] array4 = new IWidget[1];
		Column column = new Column
		{
			flex = FlexLayout.Fill
		};
		IWidget[] obj8 = new IWidget[2]
		{
			new ItemPicker<AssetItem>
			{
				adapter = m_PreviewPickerAdapter
			},
			null
		};
		obj8[1] = new ButtonRow
		{
			children = new Button[2]
			{
				m_SelectPreviewButton = new Button
				{
					displayName = "Common.SELECT"
				},
				new Button
				{
					displayName = "Common.CANCEL",
					action = delegate
					{
						SetChildren(m_MainPanel);
					}
				}
			}
		};
		column.children = obj8;
		array4[0] = column;
		m_PreviewPickerPanel = array4;
		SetChildren(m_MainPanel);
	}
```

- `private OnRemoveAdditionalAsset(System.Int32 index) : System.Void`  

```csharp
private void OnRemoveAdditionalAsset(int index)
	{
		if (m_AssetList.m_Items[index].m_Data is AssetData asset)
		{
			m_UploadHandle.RemoveAdditionalAsset(asset);
			RefreshAssetList();
			RefreshDLCList();
		}
	}
```

- `private OnRemoveTag(System.Int32 index) : System.Void`  

```csharp
private void OnRemoveTag(int index)
	{
		if (m_TagsList.m_Items[index].m_Data is string tag)
		{
			m_UploadHandle.RemoveAdditionalTag(tag);
		}
		RefreshTags();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		RefreshSubmitButtonLabel();
	}
```

- `private OpenPreviewPickerPanel(System.Action<Colossal.Hash128> callback, Colossal.Hash128 defaultSelection = null, System.Boolean excludeScreenshots = False) : System.Void`  

```csharp
private System.Void OpenPreviewPickerPanel(System.Action<Colossal.Hash128> callback, Colossal.Hash128 defaultSelection, System.Boolean excludeScreenshots);
```

- `private RefreshAssetList() : System.Void`  

```csharp
private void RefreshAssetList()
	{
		if (m_AssetList == null)
		{
			return;
		}
		List<ListField.Item> list = new List<ListField.Item>();
		foreach (AssetData asset in m_UploadHandle.assets)
		{
			list.Add(GetItem(asset, removable: false, asset == m_UploadHandle.mainAsset));
		}
		foreach (AssetData additionalAsset in m_UploadHandle.additionalAssets)
		{
			list.Add(GetItem(additionalAsset, removable: true, additionalAsset == m_UploadHandle.mainAsset));
		}
		m_AssetList.m_Items = list;
		m_AssetList.SetPropertiesChanged();
	}
```

- `private RefreshAuthorMods() : System.Void`  

```csharp
private void RefreshAuthorMods()
	{
		m_ExistingModPopup.SetItems(GetExistingMods());
	}
```

- `private RefreshDLCList() : System.Void`  

```csharp
private void RefreshDLCList()
	{
		m_DLCInfoVisible = false;
		m_DLCInfo.children.Clear();
		string[] dLCDependencies = m_UploadHandle.modInfo.m_DLCDependencies;
		foreach (string internalName in dLCDependencies)
		{
			if (TryMatchDLC(internalName, out var dlc))
			{
				m_DLCInfo.children.Add(new DLCInfoField
				{
					displayName = dlc.m_DisplayName,
					type = dlc.m_Type,
					image = dlc.m_ImageURI
				});
				m_DLCInfoVisible = true;
			}
		}
		m_DLCInfo.SetChildrenChanged();
	}
```

- `private RefreshExternalLinks() : System.Void`  

```csharp
private void RefreshExternalLinks()
	{
		m_ExternalLinkField.links = m_UploadHandle.modInfo.m_ExternalLinks;
		m_ExternalLinkField.SetPropertiesChanged();
	}
```

- `private RefreshPreview() : System.Void`  

```csharp
private void RefreshPreview()
	{
		m_PreviewPickerButton.icon = AssetUploadUtils.GetImageURI(m_UploadHandle.preview);
		m_PreviewPickerButton.SetPropertiesChanged();
	}
```

- `private RefreshScreenshots() : System.Void`  

```csharp
private void RefreshScreenshots()
	{
		List<IconButton> list = new List<IconButton>(m_UploadHandle.screenshots.Count + 1);
		for (int i = 0; i < m_UploadHandle.screenshots.Count; i++)
		{
			int index = i;
			list.Add(new IconButton
			{
				icon = AssetUploadUtils.GetImageURI(m_UploadHandle.screenshots[index]),
				action = delegate
				{
					RemoveScreenshot(index);
				}
			});
		}
		list.Add(new IconButton
		{
			icon = "Media/Glyphs/Plus.svg",
			action = delegate
			{
				OpenPreviewPickerPanel(AddScreenshot, default(Colossal.Hash128), excludeScreenshots: true);
			}
		});
		m_Screenshots.children = list.ToArray();
	}
```

- `private RefreshSocialProfileStatus() : System.Void`  

```csharp
private void RefreshSocialProfileStatus()
	{
		if (string.IsNullOrEmpty(m_UploadHandle.socialProfile.m_Name))
		{
			ReportNoSocial();
		}
		else if (m_State == State.Disabled)
		{
			ClearState();
		}
	}
```

- `private RefreshSubmitButtonLabel() : System.Void`  

```csharp
private void RefreshSubmitButtonLabel()
	{
		string submitButtonLabel = GetSubmitButtonLabel();
		if (m_SubmitButton.displayName.id != submitButtonLabel)
		{
			m_SubmitButton.displayName = submitButtonLabel;
			m_SubmitButton.SetPropertiesChanged();
		}
	}
```

- `private RefreshTags() : System.Void`  

```csharp
private void RefreshTags()
	{
		List<ListField.Item> list = new List<ListField.Item>();
		foreach (string tag in m_UploadHandle.tags)
		{
			list.Add(new ListField.Item
			{
				m_Label = tag,
				m_Removable = false,
				m_Data = tag
			});
		}
		foreach (string additionalTag in m_UploadHandle.additionalTags)
		{
			list.Add(new ListField.Item
			{
				m_Label = additionalTag,
				m_Removable = true,
				m_Data = additionalTag
			});
		}
		m_TagsList.m_Items = list;
		m_TagsList.SetPropertiesChanged();
		List<ItemPickerPopup<string>.Item> list2 = new List<ItemPickerPopup<string>.Item>();
		IModsUploadSupport.ModTag[] availableTags = m_UploadHandle.availableTags;
		for (int i = 0; i < availableTags.Length; i++)
		{
			IModsUploadSupport.ModTag modTag = availableTags[i];
			if (!m_UploadHandle.tags.Contains(modTag.m_Id) && !m_UploadHandle.additionalTags.Contains(modTag.m_Id))
			{
				list2.Add(new ItemPickerPopup<string>.Item
				{
					m_Value = modTag.m_Id,
					displayName = modTag.m_DisplayName
				});
			}
		}
		((ItemPickerPopup<string>)m_TagsListPopup.popup).SetItems(list2);
	}
```

- `private RemoveScreenshot(System.Int32 index) : System.Void`  

```csharp
private void RemoveScreenshot(int index)
	{
		AssetData asset = m_UploadHandle.screenshots[index];
		m_UploadHandle.RemoveScreenshot(asset);
		RefreshScreenshots();
	}
```

- `private ReportError(Colossal.PSI.Common.IModsUploadSupport+ModOperationResult result) : System.Void`  

```csharp
private void ReportError(IModsUploadSupport.ModOperationResult result)
	{
		m_State = State.Failure;
		List<IWidget> list = new List<IWidget>
		{
			new ErrorLabel
			{
				visible = true,
				displayName = kFailureLabel
			}
		};
		foreach (string line in result.m_Error.GetLines())
		{
			list.Add(new ErrorLabel
			{
				visible = true,
				displayName = line
			});
		}
		m_PlatformResult.children = list;
		m_NotificationUISystem.RemoveNotification(kNotificationID);
		m_NotificationUISystem.RemoveNotification(kNotificationID, kNotificationDelay, kFailureLabel, result.m_Error.m_Raw, null, ProgressState.Failed);
	}
```

- `private ReportLocalDataNotFound() : System.Void`  

```csharp
private void ReportLocalDataNotFound()
	{
		m_PlatformResult.children = new IWidget[1]
		{
			new Label
			{
				displayName = "Paradox.EXISTING_PREVIEWS_ERROR"
			}
		};
	}
```

- `private ReportNoSocial() : System.Void`  

```csharp
private void ReportNoSocial()
	{
		m_State = State.Disabled;
		m_PlatformResult.children = new IWidget[2]
		{
			new Label
			{
				displayName = kNoSocialProfile
			},
			new Button
			{
				displayName = kOpenProfilePage,
				action = delegate
				{
					PdxAssetUploadHandle uploadHandle = m_UploadHandle;
					uploadHandle.onSocialProfileSynced = (Action)Delegate.Combine(uploadHandle.onSocialProfileSynced, new Action(RefreshSocialProfileStatus));
					m_UploadHandle.ShowModsUIProfilePage();
				}
			}
		};
	}
```

- `private ReportSubmitting() : System.Void`  

```csharp
private void ReportSubmitting()
	{
		m_State = State.Processing;
		m_PlatformResult.children = new IWidget[1]
		{
			new Label
			{
				displayName = kSubmittingLabel
			}
		};
		m_NotificationUISystem.AddOrUpdateNotification(kNotificationID, kSubmittingLabel, m_UploadHandle.modInfo.m_DisplayName, null, ProgressState.Indeterminate);
	}
```

- `private ReportSuccess() : System.Void`  

```csharp
private void ReportSuccess()
	{
		m_State = State.Success;
		List<IWidget> list = new List<IWidget>();
		list.Add(new Label
		{
			displayName = kCompleteLabel
		});
		string id = m_UploadHandle.modInfo.m_PublishedID.ToString();
		LocalizedString localizedString = new LocalizedString("Menu.ASSET_UPLOAD_ID", id, new Dictionary<string, ILocElement> { 
		{
			"ID",
			LocalizedString.Value(id)
		} });
		list.Add(new Label
		{
			displayName = localizedString
		});
		list.Add(new Button
		{
			displayName = "Menu.ASSET_COPY_ID",
			action = delegate
			{
				GUIUtility.systemCopyBuffer = id;
			}
		});
		m_PlatformResult.children = list;
		RefreshSubmitButtonLabel();
		m_NotificationUISystem.RemoveNotification(kNotificationID);
		m_NotificationUISystem.RemoveNotification(kNotificationID, kNotificationDelay, kCompleteLabel, localizedString, null, ProgressState.Complete, null, delegate
		{
			GUIUtility.systemCopyBuffer = id;
		});
	}
```

- `private ReportSyncing() : System.Void`  

```csharp
private void ReportSyncing()
	{
		m_State = State.Processing;
		m_PlatformResult.children = new IWidget[1]
		{
			new Label
			{
				displayName = "Paradox.RETRIEVING_DATA"
			}
		};
	}
```

- `private SetChildren(Game.UI.Widgets.IWidget[] newChildren) : System.Void`  

```csharp
private void SetChildren(IWidget[] newChildren)
	{
		if (newChildren != m_Children)
		{
			m_Children = newChildren;
			onChildrenChange?.Invoke(m_Children);
		}
	}
```

- `private SetInfoFromExisting() : System.Void`  

```csharp
private async void SetInfoFromExisting()
	{
		m_State = State.Processing;
		IModsUploadSupport.ModInfo info = await m_UploadHandle.GetExistingInfo();
		var (localDataFound, localData) = await m_UploadHandle.GetLocalData(info.m_PublishedID);
		GameManager.instance.RunOnMainThread(delegate
		{
			m_State = State.Ready;
			m_UploadHandle.modInfo = info;
			RefreshExternalLinks();
			if (localDataFound)
			{
				ClearState();
				m_UploadHandle.SetPreviewsFromExisting(localData);
				RefreshPreview();
				RefreshScreenshots();
			}
			else
			{
				ReportLocalDataNotFound();
			}
		});
	}
```

- `private SetPreview(Colossal.Hash128 guid) : System.Void`  

```csharp
private void SetPreview(Colossal.Hash128 guid)
	{
		if (AssetDatabase.global.TryGetAsset(guid, out AssetData asset))
		{
			m_UploadHandle.SetPreview(asset);
		}
		RefreshPreview();
	}
```

- `private ShouldShowInPrefabPicker(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
private bool ShouldShowInPrefabPicker(PrefabBase prefab)
	{
		if (prefab.asset != null && prefab.asset.database == AssetDatabase.user)
		{
			return !m_UploadHandle.cachedDependencies.Contains(prefab.asset);
		}
		return false;
	}
```

- `public Show(Colossal.IO.AssetDatabase.AssetData mainAsset, System.Boolean allowManualFileCopy = False) : System.Void`  

```csharp
public void Show(AssetData mainAsset, bool allowManualFileCopy = false)
	{
		m_AllowManualFileCopy = false;
		m_UploadHandle = new PdxAssetUploadHandle(mainAsset);
		SetChildren(m_MainPanel);
		RefreshExternalLinks();
		RefreshScreenshots();
		RefreshPreview();
		RefreshAssetList();
		RefreshDLCList();
		ClearState();
		SyncPlatformData();
	}
```

- `private Submit() : System.Void`  

```csharp
private void Submit()
	{
		ReportSubmitting();
		BeginSubmit();
	}
```

- `private SyncPlatformData() : System.Void`  

```csharp
private async void SyncPlatformData()
	{
		ReportSyncing();
		await m_UploadHandle.SyncPlatformData();
		GameManager.instance.RunOnMainThread(delegate
		{
			ClearState();
			RefreshSocialProfileStatus();
			RefreshAuthorMods();
			RefreshTags();
			RefreshDLCList();
		});
	}
```

- `private TryMatchDLC(System.String internalName, Colossal.PSI.Common.IModsUploadSupport+DLCTag& dlc) : System.Boolean`  

```csharp
private bool TryMatchDLC(string internalName, out IModsUploadSupport.DLCTag dlc)
	{
		IModsUploadSupport.DLCTag[] availableDLCs = m_UploadHandle.availableDLCs;
		for (int i = 0; i < availableDLCs.Length; i++)
		{
			IModsUploadSupport.DLCTag dLCTag = availableDLCs[i];
			if (dLCTag.m_InternalName == internalName)
			{
				dlc = dLCTag;
				return true;
			}
		}
		dlc = default(IModsUploadSupport.DLCTag);
		return false;
	}
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

