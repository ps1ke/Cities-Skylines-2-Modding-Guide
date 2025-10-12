# Game.UI.Editor.InspectorPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.ObjectToolSystem m_ObjectTool`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.UI.Editor.EditorAssetUploadPanel m_AssetUploadPanel`  
- `private Game.Input.ProxyAction m_MoveAction`  
- `private Game.Input.ProxyAction m_CloneAction`  
- `private Game.Input.ProxyAction m_AutoAlignAction`  
- `private Game.Input.ProxyAction m_AutoConnectAction`  
- `private Game.Input.ProxyAction m_AlignXAction`  
- `private Game.Input.ProxyAction m_AlignYAction`  
- `private Game.Input.ProxyAction m_AlignZAction`  
- `private Game.UI.Widgets.EditorGenerator m_EditorGenerator`  
- `private Game.UI.Widgets.Button[] m_MeshFooter`  
- `private Game.UI.Widgets.Button[] m_InstanceFooter`  
- `private Game.UI.Widgets.Button[] m_PrefabFooter`  
- `private Game.UI.Widgets.Button[] m_CustomAssetFooter`  
- `private Unity.Entities.Entity m_CurrentSelectedEntity`  
- `private System.Object m_SelectedObject`  
- `private System.Object m_ParentObject`  
- `private Game.Prefabs.ObjectSubObjectInfo m_LastSubObject`  
- `private Game.Prefabs.ObjectSubObjectInfo m_CurrentSubObject`  
- `private Game.UI.Localization.LocalizedString m_SelectedName`  
- `private Game.UI.Localization.LocalizedString m_ParentName`  
- `private System.Collections.Generic.List<System.Object> m_SectionObjects`  
- `private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Game.UI.Editor.InspectorPanelSystem+LocalizationFields> m_WipLocalization`  
- `private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Platform`  

## Properties

- `private Game.UI.Editor.InspectorPanelSystem+Mode mode { private get }`  
- `private System.Boolean canMoveSelected { private get }`  
- `private System.Boolean canCloneSelected { private get }`  
- `private System.Boolean canAlignSelected { private get }`  

## Constructors

- `public InspectorPanelSystem()`  

## Methods

- `private <OnCreate>b__32_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  
- `private <OnCreate>b__32_1() : System.Boolean`  
- `private <OnCreate>b__32_2() : System.Boolean`  
- `private <OnCreate>b__32_3() : System.Boolean`  
- `private <ShowSaveAssetPanel>b__75_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  
- `private <ShowShareAssetPanel>b__80_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  
- `private AlignX() : System.Void`  
- `private AlignY() : System.Void`  
- `private AlignZ() : System.Void`  
- `private AutoAlign() : System.Void`  
- `private AutoConnect() : System.Void`  
- `private BuildLocalizationFields(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.UI.Widgets.IWidget> widgets) : System.Void`  
- `private CloneSelected() : System.Void`  
- `public static DisableAllFields(Game.UI.Widgets.IWidget widget) : System.Void`  
- `private DisableSection(System.Object obj, System.Object parent) : System.Boolean`  
- `private DuplicatePrefab(Game.Prefabs.PrefabBase oldPrefab) : Game.Prefabs.PrefabBase`  
- `private FindObjectMeshInfo(Game.Prefabs.ObjectGeometryPrefab prefab, Game.Prefabs.PrefabBase meshPrefab, Game.Prefabs.ObjectMeshInfo& info) : System.Boolean`  
- `private static GetActiveAccessor(Game.Prefabs.ComponentBase component) : Game.Reflection.ITypedValueAccessor<System.Boolean>`  
- `private GetComponentTypeItems() : System.Collections.Generic.IEnumerable<Game.UI.Editor.Item>`  
- `private GetCustomAssets() : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  
- `private GetObjectName(System.Object obj) : Game.UI.Localization.LocalizedString`  
- `private GetSectionObjects() : System.Collections.Generic.IEnumerable<System.Object>`  
- `private HandleInput() : System.Void`  
- `private InitializeLocalization(Game.Prefabs.PrefabBase prefab, System.String key) : System.Collections.Generic.List<Game.UI.Editor.LocalizationField+LocalizationFieldEntry>`  
- `private static IsBuiltinAsset(Colossal.IO.AssetDatabase.AssetData asset) : System.Boolean`  
- `private IsColorVariationField(Game.UI.Widgets.IWidget widget, System.Int32& variationSetIndex, System.Int32& colorIndex, Game.Prefabs.RenderPrefabBase& mesh) : System.Boolean`  
- `private IsEmissiveField(Game.UI.Widgets.IWidget widget, System.Int32& singleLightIndex, System.Int32& multiLightIndex, Game.Prefabs.RenderPrefabBase& mesh) : System.Boolean`  
- `private MoveSelected() : System.Void`  
- `private MoveSubObjects(Game.Prefabs.PrefabBase prefab) : System.Void`  
- `private OnAddComponent(System.Type type) : System.Void`  
- `private OnColorVariationChanged(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase mesh, System.Int32 variationSetIndex, System.Int32 colorIndex) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `private OnDuplicate() : System.Void`  
- `private OnEmissiveChanged(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase mesh, System.Int32 singleLightIndex, System.Int32 multiLightIndex) : System.Void`  
- `private OnLocate() : System.Void`  
- `private OnSaveAsset(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid, System.Action<Colossal.IO.AssetDatabase.PrefabAsset> callback = null) : System.Void`  
- `private OnShareAsset(Colossal.IO.AssetDatabase.PrefabAsset asset) : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `protected virtual OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  
- `private RefreshContent() : System.Void`  
- `private RefreshFooter(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> panelChildren) : System.Void`  
- `private RefreshSections() : System.Void`  
- `private RefreshTitle() : System.Void`  
- `private SaveAsset(System.String name, Colossal.IO.AssetDatabase.PrefabAsset existing = null, System.Action<Colossal.IO.AssetDatabase.PrefabAsset> callback = null) : System.Void`  
- `private SaveIcons(Game.Prefabs.PrefabBase prefab, System.String name) : System.Void`  
- `private SaveLocalization(Game.Prefabs.PrefabBase prefab, System.String name) : System.Void`  
- `public SelectEntity(Unity.Entities.Entity entity) : System.Boolean`  
- `private SelectInUnityEditor(UnityEngine.Object obj) : System.Void`  
- `public SelectMesh(Unity.Entities.Entity entity, System.Int32 meshIndex) : System.Boolean`  
- `private SelectObjectForEntity(Unity.Entities.Entity entity) : System.Boolean`  
- `public SelectPrefab(Game.Prefabs.PrefabBase prefab) : System.Void`  
- `private ShowAddComponentPicker() : System.Void`  
- `private ShowSaveAssetPanel() : System.Void`  
- `private ShowShareAssetPanel() : System.Void`  
- `public ShowThumbnailPicker(Game.UI.Editor.LoadAssetPanel+LoadCallback callback) : System.Void`  
- `private TryGetAssetItem(Colossal.IO.AssetDatabase.PrefabAsset asset, Game.UI.Editor.AssetItem& item) : System.Boolean`  
- `private UpdateParent(System.Boolean moveSubObjects) : System.Void`  

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

