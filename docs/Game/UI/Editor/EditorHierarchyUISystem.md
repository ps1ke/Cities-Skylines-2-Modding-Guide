# Game.UI.Editor.EditorHierarchyUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `public System.Action<Unity.Entities.Entity> onSave`  
- `public System.Action<Unity.Entities.Entity> onBulldoze`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.UI.Editor.EditorToolUISystem m_EditorToolUISystem`  
- `private Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Unity.Entities.EntityQuery m_ObjectQuery`  
- `private Unity.Entities.EntityQuery m_ModifiedQuery`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.Editor.EditorHierarchyUISystem+Viewport> m_ViewportBinding`  
- `private System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+PanelItem> <panelItems>k__BackingField`  
- `private Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> m_Hierarchy`  
- `private Unity.Collections.NativeParallelHashSet<Game.UI.Editor.EditorHierarchyUISystem+ItemId> m_ExpandedIds`  
- `private System.Int32 m_TotalCount`  
- `private Game.UI.Editor.EditorHierarchyUISystem+ItemId m_SelectedId`  
- `private Game.UI.Editor.EditorHierarchyUISystem+Viewport m_Viewport`  
- `private System.Int32 m_NextViewportStartIndex`  
- `private System.Int32 m_NextViewportEndIndex`  
- `private System.Boolean m_Dirty`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CameraMode`  
- `private Game.UI.Editor.EditorHierarchyUISystem+TypeHandle __TypeHandle`  
- `private static const System.String kGroup`  

## Properties

- `public Game.GameMode gameMode { get }`  
- `public System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+PanelItem> panelItems { get; private set }`  

## Constructors

- `public EditorHierarchyUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private <OnCreate>b__27_0() : System.Int32`  
- `private <OnCreate>b__27_1() : Game.UI.Editor.EditorHierarchyUISystem+ItemId`  
- `private <OnCreate>b__27_2() : Game.UI.Editor.EditorHierarchyUISystem+Viewport`  
- `private <OnCreate>b__27_3(System.Int32 mode) : System.Void`  
- `private <UpdateSelection>b__32_0(Game.UI.Editor.EditorHierarchyUISystem+PanelItem p) : System.Boolean`  
- `private <UpdateSelection>b__32_1(Game.UI.Editor.EditorHierarchyUISystem+PanelItem p) : System.Boolean`  
- `private BuildViewportItem(Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem item) : Game.UI.Editor.EditorHierarchyUISystem+ViewportItem`  
- `private EditorHierarchyUISystem_4E004959_LambdaJob_0_Execute(Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> hierarchy, Unity.Jobs.JobHandle __inputDependency) : Unity.Jobs.JobHandle`  
- `private GetName(Game.UI.Editor.EditorHierarchyUISystem+ItemId id) : Game.UI.Localization.LocalizedString`  
- `private GetTooltip(Game.UI.Editor.EditorHierarchyUISystem+ItemId id) : Game.UI.Localization.LocalizedString`  
- `private GetWidth() : System.Int32`  
- `private OnBulldoze(Unity.Entities.Entity entity) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private OnSave(Unity.Entities.Entity entity) : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private RefreshCameraController(Game.UI.Editor.EditorHierarchyUISystem+CameraMode mode) : System.Void`  
- `private SetExpanded(Game.UI.Editor.EditorHierarchyUISystem+ItemId id, System.Boolean expanded) : System.Void`  
- `public SetSelectedId(Game.UI.Editor.EditorHierarchyUISystem+ItemId id) : System.Void`  
- `private SetViewportRange(System.Int32 startIndex, System.Int32 endIndex) : System.Void`  
- `private SetWidth(System.Int32 width) : System.Void`  
- `private ToggleCameraMode(Game.UI.Editor.EditorHierarchyUISystem+CameraMode cameraMode) : System.Void`  
- `private UpdateHierarchy(Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> hierarchy) : System.Void`  
- `private UpdateSelection() : System.Void`  
- `private UpdateViewport(System.Boolean force) : System.Void`  
- `private ViewportChanged() : System.Boolean`  

## Nested types

- `Game.UI.Editor.EditorHierarchyUISystem+CameraMode`  
- `Game.UI.Editor.EditorHierarchyUISystem+ObjectHierarchyJob`  
- `Game.UI.Editor.EditorHierarchyUISystem+PanelItem`  
- `Game.UI.Editor.EditorHierarchyUISystem+Viewport`  
- `Game.UI.Editor.EditorHierarchyUISystem+ViewportItem`  
- `Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem`  
- `Game.UI.Editor.EditorHierarchyUISystem+ItemId`  
- `Game.UI.Editor.EditorHierarchyUISystem+ItemType`  
- `Game.UI.Editor.EditorHierarchyUISystem+EditorHierarchyUISystem_4E004959_LambdaJob_0_Job`  
- `Game.UI.Editor.EditorHierarchyUISystem+TypeHandle`  
- `Game.UI.Editor.EditorHierarchyUISystem+<>c__DisplayClass40_0`  

