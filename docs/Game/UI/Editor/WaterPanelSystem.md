# Game.UI.Editor.WaterPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPanelSystem : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.WaterToolSystem m_WaterToolSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_WaterSourceQuery;
    private Unity.Entities.EntityQuery m_UpdatedSourceQuery;
    private Unity.Entities.EntityArchetype m_WaterSourceArchetype;
    private Game.UI.Editor.WaterPanelSystem+WaterConfig m_Config;
    private static readonly System.Int32[] kWaterSpeedValues;

    public WaterPanelSystem();

    private System.Void AddBorderSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Entities.Entity entity, Game.UI.Editor.WaterPanelSystem+WaterConfig+BorderWaterSource source, System.Int32 constantDepth, Game.Simulation.TerrainHeightData& terrainHeightData);
    private System.Void AddSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Entities.Entity entity, Game.UI.Editor.WaterPanelSystem+WaterConfig+WaterSource source, System.Int32 constantDepth, System.Single& amount, Game.Simulation.TerrainHeightData& terrainHeightData);
    private System.Void ApplyWaterSources();
    private Game.UI.Widgets.IWidget[] BuildWaterSpeedToggles();
    public System.Void FetchWaterSources();
    private Unity.Entities.Entity GetSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> sources, System.Int32& sourceCount);
    protected virtual System.Boolean OnCancel();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
    protected virtual System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.WaterToolSystem m_WaterToolSystem`  

```csharp
private Game.Tools.WaterToolSystem m_WaterToolSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_WaterSourceQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaterSourceQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedSourceQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedSourceQuery;
```

- `private Unity.Entities.EntityArchetype m_WaterSourceArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_WaterSourceArchetype;
```

- `private Game.UI.Editor.WaterPanelSystem+WaterConfig m_Config`  

```csharp
private Game.UI.Editor.WaterPanelSystem+WaterConfig m_Config;
```

- `private static readonly System.Int32[] kWaterSpeedValues`  

```csharp
private static readonly System.Int32[] kWaterSpeedValues;
```


## Constructors

- `public WaterPanelSystem()`  

```csharp
public WaterPanelSystem();
```


## Methods

- `private AddBorderSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Entities.Entity entity, Game.UI.Editor.WaterPanelSystem+WaterConfig+BorderWaterSource source, System.Int32 constantDepth, Game.Simulation.TerrainHeightData& terrainHeightData) : System.Void`  

```csharp
private System.Void AddBorderSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Entities.Entity entity, Game.UI.Editor.WaterPanelSystem+WaterConfig+BorderWaterSource source, System.Int32 constantDepth, Game.Simulation.TerrainHeightData& terrainHeightData);
```

- `private AddSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Entities.Entity entity, Game.UI.Editor.WaterPanelSystem+WaterConfig+WaterSource source, System.Int32 constantDepth, System.Single& amount, Game.Simulation.TerrainHeightData& terrainHeightData) : System.Void`  

```csharp
private System.Void AddSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Entities.Entity entity, Game.UI.Editor.WaterPanelSystem+WaterConfig+WaterSource source, System.Int32 constantDepth, System.Single& amount, Game.Simulation.TerrainHeightData& terrainHeightData);
```

- `private ApplyWaterSources() : System.Void`  

```csharp
private System.Void ApplyWaterSources();
```

- `private BuildWaterSpeedToggles() : Game.UI.Widgets.IWidget[]`  

```csharp
private Game.UI.Widgets.IWidget[] BuildWaterSpeedToggles();
```

- `public FetchWaterSources() : System.Void`  

```csharp
public System.Void FetchWaterSources();
```

- `private GetSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> sources, System.Int32& sourceCount) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> sources, System.Int32& sourceCount);
```

- `protected virtual OnCancel() : System.Boolean`  

```csharp
protected virtual System.Boolean OnCancel();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
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


## Nested types

- `Game.UI.Editor.WaterPanelSystem+WaterConfig`  
- `Game.UI.Editor.WaterPanelSystem+<>c__DisplayClass11_0`  

