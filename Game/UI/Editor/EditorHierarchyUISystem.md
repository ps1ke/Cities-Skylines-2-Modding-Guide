# Game.UI.Editor.EditorHierarchyUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EditorHierarchyUISystem : Game.UI.UISystemBase
{
    public System.Action<Unity.Entities.Entity> onSave;
    public System.Action<Unity.Entities.Entity> onBulldoze;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.UI.Editor.EditorToolUISystem m_EditorToolUISystem;
    private Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Unity.Entities.EntityQuery m_ModifiedQuery;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.Editor.EditorHierarchyUISystem+Viewport> m_ViewportBinding;
    private System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+PanelItem> <panelItems>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> m_Hierarchy;
    private Unity.Collections.NativeParallelHashSet<Game.UI.Editor.EditorHierarchyUISystem+ItemId> m_ExpandedIds;
    private System.Int32 m_TotalCount;
    private Game.UI.Editor.EditorHierarchyUISystem+ItemId m_SelectedId;
    private Game.UI.Editor.EditorHierarchyUISystem+Viewport m_Viewport;
    private System.Int32 m_NextViewportStartIndex;
    private System.Int32 m_NextViewportEndIndex;
    private System.Boolean m_Dirty;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CameraMode;
    private Game.UI.Editor.EditorHierarchyUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }
    public System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+PanelItem> panelItems { get; private set; }

    public EditorHierarchyUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Int32 <OnCreate>b__27_0();
    private Game.UI.Editor.EditorHierarchyUISystem+ItemId <OnCreate>b__27_1();
    private Game.UI.Editor.EditorHierarchyUISystem+Viewport <OnCreate>b__27_2();
    private System.Void <OnCreate>b__27_3(System.Int32 mode);
    private System.Boolean <UpdateSelection>b__32_0(Game.UI.Editor.EditorHierarchyUISystem+PanelItem p);
    private System.Boolean <UpdateSelection>b__32_1(Game.UI.Editor.EditorHierarchyUISystem+PanelItem p);
    private Game.UI.Editor.EditorHierarchyUISystem+ViewportItem BuildViewportItem(Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem item);
    private Unity.Jobs.JobHandle EditorHierarchyUISystem_4E004959_LambdaJob_0_Execute(Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> hierarchy, Unity.Jobs.JobHandle __inputDependency);
    private Game.UI.Localization.LocalizedString GetName(Game.UI.Editor.EditorHierarchyUISystem+ItemId id);
    private Game.UI.Localization.LocalizedString GetTooltip(Game.UI.Editor.EditorHierarchyUISystem+ItemId id);
    private System.Int32 GetWidth();
    private System.Void OnBulldoze(Unity.Entities.Entity entity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnSave(Unity.Entities.Entity entity);
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnUpdate();
    private System.Void RefreshCameraController(Game.UI.Editor.EditorHierarchyUISystem+CameraMode mode);
    private System.Void SetExpanded(Game.UI.Editor.EditorHierarchyUISystem+ItemId id, System.Boolean expanded);
    public System.Void SetSelectedId(Game.UI.Editor.EditorHierarchyUISystem+ItemId id);
    private System.Void SetViewportRange(System.Int32 startIndex, System.Int32 endIndex);
    private System.Void SetWidth(System.Int32 width);
    private System.Void ToggleCameraMode(Game.UI.Editor.EditorHierarchyUISystem+CameraMode cameraMode);
    private System.Void UpdateHierarchy(Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> hierarchy);
    private System.Void UpdateSelection();
    private System.Void UpdateViewport(System.Boolean force);
    private System.Boolean ViewportChanged();
}
```


## Fields

- `public System.Action<Unity.Entities.Entity> onSave`  

```csharp
public System.Action<Unity.Entities.Entity> onSave;
```

- `public System.Action<Unity.Entities.Entity> onBulldoze`  

```csharp
public System.Action<Unity.Entities.Entity> onBulldoze;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.UI.Editor.EditorToolUISystem m_EditorToolUISystem`  

```csharp
private Game.UI.Editor.EditorToolUISystem m_EditorToolUISystem;
```

- `private Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem`  

```csharp
private Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Unity.Entities.EntityQuery m_ObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedQuery;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.Editor.EditorHierarchyUISystem+Viewport> m_ViewportBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.Editor.EditorHierarchyUISystem+Viewport> m_ViewportBinding;
```

- `private System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+PanelItem> <panelItems>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+PanelItem> <panelItems>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> m_Hierarchy`  

```csharp
private Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> m_Hierarchy;
```

- `private Unity.Collections.NativeParallelHashSet<Game.UI.Editor.EditorHierarchyUISystem+ItemId> m_ExpandedIds`  

```csharp
private Unity.Collections.NativeParallelHashSet<Game.UI.Editor.EditorHierarchyUISystem+ItemId> m_ExpandedIds;
```

- `private System.Int32 m_TotalCount`  

```csharp
private System.Int32 m_TotalCount;
```

- `private Game.UI.Editor.EditorHierarchyUISystem+ItemId m_SelectedId`  

```csharp
private Game.UI.Editor.EditorHierarchyUISystem+ItemId m_SelectedId;
```

- `private Game.UI.Editor.EditorHierarchyUISystem+Viewport m_Viewport`  

```csharp
private Game.UI.Editor.EditorHierarchyUISystem+Viewport m_Viewport;
```

- `private System.Int32 m_NextViewportStartIndex`  

```csharp
private System.Int32 m_NextViewportStartIndex;
```

- `private System.Int32 m_NextViewportEndIndex`  

```csharp
private System.Int32 m_NextViewportEndIndex;
```

- `private System.Boolean m_Dirty`  

```csharp
private System.Boolean m_Dirty;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CameraMode`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CameraMode;
```

- `private Game.UI.Editor.EditorHierarchyUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Editor.EditorHierarchyUISystem+TypeHandle __TypeHandle;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```

- `public System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+PanelItem> panelItems { get; private set }`  

```csharp
public System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+PanelItem> panelItems { get; private set; }
```


## Constructors

- `public EditorHierarchyUISystem()`  

```csharp
public EditorHierarchyUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private <OnCreate>b__27_0() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__27_0();
```

- `private <OnCreate>b__27_1() : Game.UI.Editor.EditorHierarchyUISystem+ItemId`  

```csharp
private Game.UI.Editor.EditorHierarchyUISystem+ItemId <OnCreate>b__27_1();
```

- `private <OnCreate>b__27_2() : Game.UI.Editor.EditorHierarchyUISystem+Viewport`  

```csharp
private Game.UI.Editor.EditorHierarchyUISystem+Viewport <OnCreate>b__27_2();
```

- `private <OnCreate>b__27_3(System.Int32 mode) : System.Void`  

```csharp
private System.Void <OnCreate>b__27_3(System.Int32 mode);
```

- `private <UpdateSelection>b__32_0(Game.UI.Editor.EditorHierarchyUISystem+PanelItem p) : System.Boolean`  

```csharp
private System.Boolean <UpdateSelection>b__32_0(Game.UI.Editor.EditorHierarchyUISystem+PanelItem p);
```

- `private <UpdateSelection>b__32_1(Game.UI.Editor.EditorHierarchyUISystem+PanelItem p) : System.Boolean`  

```csharp
private System.Boolean <UpdateSelection>b__32_1(Game.UI.Editor.EditorHierarchyUISystem+PanelItem p);
```

- `private BuildViewportItem(Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem item) : Game.UI.Editor.EditorHierarchyUISystem+ViewportItem`  

```csharp
private Game.UI.Editor.EditorHierarchyUISystem+ViewportItem BuildViewportItem(Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem item);
```

- `private EditorHierarchyUISystem_4E004959_LambdaJob_0_Execute(Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> hierarchy, Unity.Jobs.JobHandle __inputDependency) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle EditorHierarchyUISystem_4E004959_LambdaJob_0_Execute(Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> hierarchy, Unity.Jobs.JobHandle __inputDependency);
```

- `private GetName(Game.UI.Editor.EditorHierarchyUISystem+ItemId id) : Game.UI.Localization.LocalizedString`  

```csharp
private Game.UI.Localization.LocalizedString GetName(Game.UI.Editor.EditorHierarchyUISystem+ItemId id);
```

- `private GetTooltip(Game.UI.Editor.EditorHierarchyUISystem+ItemId id) : Game.UI.Localization.LocalizedString`  

```csharp
private Game.UI.Localization.LocalizedString GetTooltip(Game.UI.Editor.EditorHierarchyUISystem+ItemId id);
```

- `private GetWidth() : System.Int32`  

```csharp
private System.Int32 GetWidth();
```

- `private OnBulldoze(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void OnBulldoze(Unity.Entities.Entity entity);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `private OnSave(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void OnSave(Unity.Entities.Entity entity);
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private RefreshCameraController(Game.UI.Editor.EditorHierarchyUISystem+CameraMode mode) : System.Void`  

```csharp
private System.Void RefreshCameraController(Game.UI.Editor.EditorHierarchyUISystem+CameraMode mode);
```

- `private SetExpanded(Game.UI.Editor.EditorHierarchyUISystem+ItemId id, System.Boolean expanded) : System.Void`  

```csharp
private System.Void SetExpanded(Game.UI.Editor.EditorHierarchyUISystem+ItemId id, System.Boolean expanded);
```

- `public SetSelectedId(Game.UI.Editor.EditorHierarchyUISystem+ItemId id) : System.Void`  

```csharp
public System.Void SetSelectedId(Game.UI.Editor.EditorHierarchyUISystem+ItemId id);
```

- `private SetViewportRange(System.Int32 startIndex, System.Int32 endIndex) : System.Void`  

```csharp
private System.Void SetViewportRange(System.Int32 startIndex, System.Int32 endIndex);
```

- `private SetWidth(System.Int32 width) : System.Void`  

```csharp
private System.Void SetWidth(System.Int32 width);
```

- `private ToggleCameraMode(Game.UI.Editor.EditorHierarchyUISystem+CameraMode cameraMode) : System.Void`  

```csharp
private System.Void ToggleCameraMode(Game.UI.Editor.EditorHierarchyUISystem+CameraMode cameraMode);
```

- `private UpdateHierarchy(Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> hierarchy) : System.Void`  

```csharp
private System.Void UpdateHierarchy(Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> hierarchy);
```

- `private UpdateSelection() : System.Void`  

```csharp
private System.Void UpdateSelection();
```

- `private UpdateViewport(System.Boolean force) : System.Void`  

```csharp
private System.Void UpdateViewport(System.Boolean force);
```

- `private ViewportChanged() : System.Boolean`  

```csharp
private System.Boolean ViewportChanged();
```


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

