# Game.UI.Editor.InspectorPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InspectorPanelSystem : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.ObjectToolSystem m_ObjectTool;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.UI.Editor.EditorAssetUploadPanel m_AssetUploadPanel;
    private Game.Input.ProxyAction m_MoveAction;
    private Game.Input.ProxyAction m_CloneAction;
    private Game.Input.ProxyAction m_AutoAlignAction;
    private Game.Input.ProxyAction m_AutoConnectAction;
    private Game.Input.ProxyAction m_AlignXAction;
    private Game.Input.ProxyAction m_AlignYAction;
    private Game.Input.ProxyAction m_AlignZAction;
    private Game.UI.Widgets.EditorGenerator m_EditorGenerator;
    private Game.UI.Widgets.Button[] m_MeshFooter;
    private Game.UI.Widgets.Button[] m_InstanceFooter;
    private Game.UI.Widgets.Button[] m_PrefabFooter;
    private Game.UI.Widgets.Button[] m_CustomAssetFooter;
    private Unity.Entities.Entity m_CurrentSelectedEntity;
    private System.Object m_SelectedObject;
    private System.Object m_ParentObject;
    private Game.Prefabs.ObjectSubObjectInfo m_LastSubObject;
    private Game.Prefabs.ObjectSubObjectInfo m_CurrentSubObject;
    private Game.UI.Localization.LocalizedString m_SelectedName;
    private Game.UI.Localization.LocalizedString m_ParentName;
    private System.Collections.Generic.List<System.Object> m_SectionObjects;
    private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Game.UI.Editor.InspectorPanelSystem+LocalizationFields> m_WipLocalization;
    private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Platform;

    private Game.UI.Editor.InspectorPanelSystem+Mode mode { private get; }
    private System.Boolean canMoveSelected { private get; }
    private System.Boolean canCloneSelected { private get; }
    private System.Boolean canAlignSelected { private get; }

    public InspectorPanelSystem();

    private System.Void <OnCreate>b__32_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
    private System.Boolean <OnCreate>b__32_1();
    private System.Boolean <OnCreate>b__32_2();
    private System.Boolean <OnCreate>b__32_3();
    private System.Void <ShowSaveAssetPanel>b__75_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid);
    private System.Void <ShowShareAssetPanel>b__80_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid);
    private System.Void AlignX();
    private System.Void AlignY();
    private System.Void AlignZ();
    private System.Void AutoAlign();
    private System.Void AutoConnect();
    private System.Void BuildLocalizationFields(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.UI.Widgets.IWidget> widgets);
    private System.Void CloneSelected();
    public static System.Void DisableAllFields(Game.UI.Widgets.IWidget widget);
    private System.Boolean DisableSection(System.Object obj, System.Object parent);
    private Game.Prefabs.PrefabBase DuplicatePrefab(Game.Prefabs.PrefabBase oldPrefab);
    private System.Boolean FindObjectMeshInfo(Game.Prefabs.ObjectGeometryPrefab prefab, Game.Prefabs.PrefabBase meshPrefab, Game.Prefabs.ObjectMeshInfo& info);
    private static Game.Reflection.ITypedValueAccessor<System.Boolean> GetActiveAccessor(Game.Prefabs.ComponentBase component);
    private System.Collections.Generic.IEnumerable<Game.UI.Editor.Item> GetComponentTypeItems();
    private System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> GetCustomAssets();
    private Game.UI.Localization.LocalizedString GetObjectName(System.Object obj);
    private System.Collections.Generic.IEnumerable<System.Object> GetSectionObjects();
    private System.Void HandleInput();
    private System.Collections.Generic.List<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> InitializeLocalization(Game.Prefabs.PrefabBase prefab, System.String key);
    private static System.Boolean IsBuiltinAsset(Colossal.IO.AssetDatabase.AssetData asset);
    private System.Boolean IsColorVariationField(Game.UI.Widgets.IWidget widget, System.Int32& variationSetIndex, System.Int32& colorIndex, Game.Prefabs.RenderPrefabBase& mesh);
    private System.Boolean IsEmissiveField(Game.UI.Widgets.IWidget widget, System.Int32& singleLightIndex, System.Int32& multiLightIndex, Game.Prefabs.RenderPrefabBase& mesh);
    private System.Void MoveSelected();
    private System.Void MoveSubObjects(Game.Prefabs.PrefabBase prefab);
    private System.Void OnAddComponent(System.Type type);
    private System.Void OnColorVariationChanged(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase mesh, System.Int32 variationSetIndex, System.Int32 colorIndex);
    protected virtual System.Void OnCreate();
    private System.Void OnDuplicate();
    private System.Void OnEmissiveChanged(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase mesh, System.Int32 singleLightIndex, System.Int32 multiLightIndex);
    private System.Void OnLocate();
    private System.Void OnSaveAsset(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid, System.Action<Colossal.IO.AssetDatabase.PrefabAsset> callback);
    private System.Void OnShareAsset(Colossal.IO.AssetDatabase.PrefabAsset asset);
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
    protected virtual System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
    private System.Void RefreshContent();
    private System.Void RefreshFooter(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> panelChildren);
    private System.Void RefreshSections();
    private System.Void RefreshTitle();
    private System.Void SaveAsset(System.String name, Colossal.IO.AssetDatabase.PrefabAsset existing, System.Action<Colossal.IO.AssetDatabase.PrefabAsset> callback);
    private System.Void SaveIcons(Game.Prefabs.PrefabBase prefab, System.String name);
    private System.Void SaveLocalization(Game.Prefabs.PrefabBase prefab, System.String name);
    public System.Boolean SelectEntity(Unity.Entities.Entity entity);
    private System.Void SelectInUnityEditor(UnityEngine.Object obj);
    public System.Boolean SelectMesh(Unity.Entities.Entity entity, System.Int32 meshIndex);
    private System.Boolean SelectObjectForEntity(Unity.Entities.Entity entity);
    public System.Void SelectPrefab(Game.Prefabs.PrefabBase prefab);
    private System.Void ShowAddComponentPicker();
    private System.Void ShowSaveAssetPanel();
    private System.Void ShowShareAssetPanel();
    public System.Void ShowThumbnailPicker(Game.UI.Editor.LoadAssetPanel+LoadCallback callback);
    private System.Boolean TryGetAssetItem(Colossal.IO.AssetDatabase.PrefabAsset asset, Game.UI.Editor.AssetItem& item);
    private System.Void UpdateParent(System.Boolean moveSubObjects);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.ObjectToolSystem m_ObjectTool`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectTool;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.UI.Editor.EditorAssetUploadPanel m_AssetUploadPanel`  

```csharp
private Game.UI.Editor.EditorAssetUploadPanel m_AssetUploadPanel;
```

- `private Game.Input.ProxyAction m_MoveAction`  

```csharp
private Game.Input.ProxyAction m_MoveAction;
```

- `private Game.Input.ProxyAction m_CloneAction`  

```csharp
private Game.Input.ProxyAction m_CloneAction;
```

- `private Game.Input.ProxyAction m_AutoAlignAction`  

```csharp
private Game.Input.ProxyAction m_AutoAlignAction;
```

- `private Game.Input.ProxyAction m_AutoConnectAction`  

```csharp
private Game.Input.ProxyAction m_AutoConnectAction;
```

- `private Game.Input.ProxyAction m_AlignXAction`  

```csharp
private Game.Input.ProxyAction m_AlignXAction;
```

- `private Game.Input.ProxyAction m_AlignYAction`  

```csharp
private Game.Input.ProxyAction m_AlignYAction;
```

- `private Game.Input.ProxyAction m_AlignZAction`  

```csharp
private Game.Input.ProxyAction m_AlignZAction;
```

- `private Game.UI.Widgets.EditorGenerator m_EditorGenerator`  

```csharp
private Game.UI.Widgets.EditorGenerator m_EditorGenerator;
```

- `private Game.UI.Widgets.Button[] m_MeshFooter`  

```csharp
private Game.UI.Widgets.Button[] m_MeshFooter;
```

- `private Game.UI.Widgets.Button[] m_InstanceFooter`  

```csharp
private Game.UI.Widgets.Button[] m_InstanceFooter;
```

- `private Game.UI.Widgets.Button[] m_PrefabFooter`  

```csharp
private Game.UI.Widgets.Button[] m_PrefabFooter;
```

- `private Game.UI.Widgets.Button[] m_CustomAssetFooter`  

```csharp
private Game.UI.Widgets.Button[] m_CustomAssetFooter;
```

- `private Unity.Entities.Entity m_CurrentSelectedEntity`  

```csharp
private Unity.Entities.Entity m_CurrentSelectedEntity;
```

- `private System.Object m_SelectedObject`  

```csharp
private System.Object m_SelectedObject;
```

- `private System.Object m_ParentObject`  

```csharp
private System.Object m_ParentObject;
```

- `private Game.Prefabs.ObjectSubObjectInfo m_LastSubObject`  

```csharp
private Game.Prefabs.ObjectSubObjectInfo m_LastSubObject;
```

- `private Game.Prefabs.ObjectSubObjectInfo m_CurrentSubObject`  

```csharp
private Game.Prefabs.ObjectSubObjectInfo m_CurrentSubObject;
```

- `private Game.UI.Localization.LocalizedString m_SelectedName`  

```csharp
private Game.UI.Localization.LocalizedString m_SelectedName;
```

- `private Game.UI.Localization.LocalizedString m_ParentName`  

```csharp
private Game.UI.Localization.LocalizedString m_ParentName;
```

- `private System.Collections.Generic.List<System.Object> m_SectionObjects`  

```csharp
private System.Collections.Generic.List<System.Object> m_SectionObjects;
```

- `private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Game.UI.Editor.InspectorPanelSystem+LocalizationFields> m_WipLocalization`  

```csharp
private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Game.UI.Editor.InspectorPanelSystem+LocalizationFields> m_WipLocalization;
```

- `private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Platform`  

```csharp
private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Platform;
```


## Properties

- `private Game.UI.Editor.InspectorPanelSystem+Mode mode { private get }`  

```csharp
private Game.UI.Editor.InspectorPanelSystem+Mode mode { private get; }
```

- `private System.Boolean canMoveSelected { private get }`  

```csharp
private System.Boolean canMoveSelected { private get; }
```

- `private System.Boolean canCloneSelected { private get }`  

```csharp
private System.Boolean canCloneSelected { private get; }
```

- `private System.Boolean canAlignSelected { private get }`  

```csharp
private System.Boolean canAlignSelected { private get; }
```


## Constructors

- `public InspectorPanelSystem()`  

```csharp
public InspectorPanelSystem();
```


## Methods

- `private <OnCreate>b__32_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  

```csharp
private System.Void <OnCreate>b__32_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
```

- `private <OnCreate>b__32_1() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__32_1();
```

- `private <OnCreate>b__32_2() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__32_2();
```

- `private <OnCreate>b__32_3() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__32_3();
```

- `private <ShowSaveAssetPanel>b__75_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  

```csharp
private System.Void <ShowSaveAssetPanel>b__75_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid);
```

- `private <ShowShareAssetPanel>b__80_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  

```csharp
private System.Void <ShowShareAssetPanel>b__80_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid);
```

- `private AlignX() : System.Void`  

```csharp
private System.Void AlignX();
```

- `private AlignY() : System.Void`  

```csharp
private System.Void AlignY();
```

- `private AlignZ() : System.Void`  

```csharp
private System.Void AlignZ();
```

- `private AutoAlign() : System.Void`  

```csharp
private System.Void AutoAlign();
```

- `private AutoConnect() : System.Void`  

```csharp
private System.Void AutoConnect();
```

- `private BuildLocalizationFields(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.UI.Widgets.IWidget> widgets) : System.Void`  

```csharp
private System.Void BuildLocalizationFields(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.UI.Widgets.IWidget> widgets);
```

- `private CloneSelected() : System.Void`  

```csharp
private System.Void CloneSelected();
```

- `public static DisableAllFields(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
public static System.Void DisableAllFields(Game.UI.Widgets.IWidget widget);
```

- `private DisableSection(System.Object obj, System.Object parent) : System.Boolean`  

```csharp
private System.Boolean DisableSection(System.Object obj, System.Object parent);
```

- `private DuplicatePrefab(Game.Prefabs.PrefabBase oldPrefab) : Game.Prefabs.PrefabBase`  

```csharp
private Game.Prefabs.PrefabBase DuplicatePrefab(Game.Prefabs.PrefabBase oldPrefab);
```

- `private FindObjectMeshInfo(Game.Prefabs.ObjectGeometryPrefab prefab, Game.Prefabs.PrefabBase meshPrefab, Game.Prefabs.ObjectMeshInfo& info) : System.Boolean`  

```csharp
private System.Boolean FindObjectMeshInfo(Game.Prefabs.ObjectGeometryPrefab prefab, Game.Prefabs.PrefabBase meshPrefab, Game.Prefabs.ObjectMeshInfo& info);
```

- `private static GetActiveAccessor(Game.Prefabs.ComponentBase component) : Game.Reflection.ITypedValueAccessor<System.Boolean>`  

```csharp
private static Game.Reflection.ITypedValueAccessor<System.Boolean> GetActiveAccessor(Game.Prefabs.ComponentBase component);
```

- `private GetComponentTypeItems() : System.Collections.Generic.IEnumerable<Game.UI.Editor.Item>`  

```csharp
private System.Collections.Generic.IEnumerable<Game.UI.Editor.Item> GetComponentTypeItems();
```

- `private GetCustomAssets() : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  

```csharp
private System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> GetCustomAssets();
```

- `private GetObjectName(System.Object obj) : Game.UI.Localization.LocalizedString`  

```csharp
private Game.UI.Localization.LocalizedString GetObjectName(System.Object obj);
```

- `private GetSectionObjects() : System.Collections.Generic.IEnumerable<System.Object>`  

```csharp
private System.Collections.Generic.IEnumerable<System.Object> GetSectionObjects();
```

- `private HandleInput() : System.Void`  

```csharp
private System.Void HandleInput();
```

- `private InitializeLocalization(Game.Prefabs.PrefabBase prefab, System.String key) : System.Collections.Generic.List<Game.UI.Editor.LocalizationField+LocalizationFieldEntry>`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> InitializeLocalization(Game.Prefabs.PrefabBase prefab, System.String key);
```

- `private static IsBuiltinAsset(Colossal.IO.AssetDatabase.AssetData asset) : System.Boolean`  

```csharp
private static System.Boolean IsBuiltinAsset(Colossal.IO.AssetDatabase.AssetData asset);
```

- `private IsColorVariationField(Game.UI.Widgets.IWidget widget, System.Int32& variationSetIndex, System.Int32& colorIndex, Game.Prefabs.RenderPrefabBase& mesh) : System.Boolean`  

```csharp
private System.Boolean IsColorVariationField(Game.UI.Widgets.IWidget widget, System.Int32& variationSetIndex, System.Int32& colorIndex, Game.Prefabs.RenderPrefabBase& mesh);
```

- `private IsEmissiveField(Game.UI.Widgets.IWidget widget, System.Int32& singleLightIndex, System.Int32& multiLightIndex, Game.Prefabs.RenderPrefabBase& mesh) : System.Boolean`  

```csharp
private System.Boolean IsEmissiveField(Game.UI.Widgets.IWidget widget, System.Int32& singleLightIndex, System.Int32& multiLightIndex, Game.Prefabs.RenderPrefabBase& mesh);
```

- `private MoveSelected() : System.Void`  

```csharp
private System.Void MoveSelected();
```

- `private MoveSubObjects(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private System.Void MoveSubObjects(Game.Prefabs.PrefabBase prefab);
```

- `private OnAddComponent(System.Type type) : System.Void`  

```csharp
private System.Void OnAddComponent(System.Type type);
```

- `private OnColorVariationChanged(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase mesh, System.Int32 variationSetIndex, System.Int32 colorIndex) : System.Void`  

```csharp
private System.Void OnColorVariationChanged(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase mesh, System.Int32 variationSetIndex, System.Int32 colorIndex);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `private OnDuplicate() : System.Void`  

```csharp
private System.Void OnDuplicate();
```

- `private OnEmissiveChanged(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase mesh, System.Int32 singleLightIndex, System.Int32 multiLightIndex) : System.Void`  

```csharp
private System.Void OnEmissiveChanged(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase mesh, System.Int32 singleLightIndex, System.Int32 multiLightIndex);
```

- `private OnLocate() : System.Void`  

```csharp
private System.Void OnLocate();
```

- `private OnSaveAsset(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid, System.Action<Colossal.IO.AssetDatabase.PrefabAsset> callback = null) : System.Void`  

```csharp
private System.Void OnSaveAsset(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid, System.Action<Colossal.IO.AssetDatabase.PrefabAsset> callback);
```

- `private OnShareAsset(Colossal.IO.AssetDatabase.PrefabAsset asset) : System.Void`  

```csharp
private System.Void OnShareAsset(Colossal.IO.AssetDatabase.PrefabAsset asset);
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `protected virtual OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
protected virtual System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
```

- `private RefreshContent() : System.Void`  

```csharp
private System.Void RefreshContent();
```

- `private RefreshFooter(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> panelChildren) : System.Void`  

```csharp
private System.Void RefreshFooter(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> panelChildren);
```

- `private RefreshSections() : System.Void`  

```csharp
private System.Void RefreshSections();
```

- `private RefreshTitle() : System.Void`  

```csharp
private System.Void RefreshTitle();
```

- `private SaveAsset(System.String name, Colossal.IO.AssetDatabase.PrefabAsset existing = null, System.Action<Colossal.IO.AssetDatabase.PrefabAsset> callback = null) : System.Void`  

```csharp
private System.Void SaveAsset(System.String name, Colossal.IO.AssetDatabase.PrefabAsset existing, System.Action<Colossal.IO.AssetDatabase.PrefabAsset> callback);
```

- `private SaveIcons(Game.Prefabs.PrefabBase prefab, System.String name) : System.Void`  

```csharp
private System.Void SaveIcons(Game.Prefabs.PrefabBase prefab, System.String name);
```

- `private SaveLocalization(Game.Prefabs.PrefabBase prefab, System.String name) : System.Void`  

```csharp
private System.Void SaveLocalization(Game.Prefabs.PrefabBase prefab, System.String name);
```

- `public SelectEntity(Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public System.Boolean SelectEntity(Unity.Entities.Entity entity);
```

- `private SelectInUnityEditor(UnityEngine.Object obj) : System.Void`  

```csharp
private System.Void SelectInUnityEditor(UnityEngine.Object obj);
```

- `public SelectMesh(Unity.Entities.Entity entity, System.Int32 meshIndex) : System.Boolean`  

```csharp
public System.Boolean SelectMesh(Unity.Entities.Entity entity, System.Int32 meshIndex);
```

- `private SelectObjectForEntity(Unity.Entities.Entity entity) : System.Boolean`  

```csharp
private System.Boolean SelectObjectForEntity(Unity.Entities.Entity entity);
```

- `public SelectPrefab(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
public System.Void SelectPrefab(Game.Prefabs.PrefabBase prefab);
```

- `private ShowAddComponentPicker() : System.Void`  

```csharp
private System.Void ShowAddComponentPicker();
```

- `private ShowSaveAssetPanel() : System.Void`  

```csharp
private System.Void ShowSaveAssetPanel();
```

- `private ShowShareAssetPanel() : System.Void`  

```csharp
private System.Void ShowShareAssetPanel();
```

- `public ShowThumbnailPicker(Game.UI.Editor.LoadAssetPanel+LoadCallback callback) : System.Void`  

```csharp
public System.Void ShowThumbnailPicker(Game.UI.Editor.LoadAssetPanel+LoadCallback callback);
```

- `private TryGetAssetItem(Colossal.IO.AssetDatabase.PrefabAsset asset, Game.UI.Editor.AssetItem& item) : System.Boolean`  

```csharp
private System.Boolean TryGetAssetItem(Colossal.IO.AssetDatabase.PrefabAsset asset, Game.UI.Editor.AssetItem& item);
```

- `private UpdateParent(System.Boolean moveSubObjects) : System.Void`  

```csharp
private System.Void UpdateParent(System.Boolean moveSubObjects);
```


## Nested types

- `Game.UI.Editor.InspectorPanelSystem+Mode`  
- `Game.UI.Editor.InspectorPanelSystem+LocalizationFields`  
- `Game.UI.Editor.InspectorPanelSystem+<>c`  
- `Game.UI.Editor.InspectorPanelSystem+<>c__DisplayClass45_0`  
- `Game.UI.Editor.InspectorPanelSystem+<>c__DisplayClass49_0`  
- `Game.UI.Editor.InspectorPanelSystem+<>c__DisplayClass53_0`  
- `Game.UI.Editor.InspectorPanelSystem+<>c__DisplayClass78_0`  
- `Game.UI.Editor.InspectorPanelSystem+<>c__DisplayClass83_0`  
- `Game.UI.Editor.InspectorPanelSystem+<GetComponentTypeItems>d__53`  
- `Game.UI.Editor.InspectorPanelSystem+<GetCustomAssets>d__76`  
- `Game.UI.Editor.InspectorPanelSystem+<GetSectionObjects>d__48`  

