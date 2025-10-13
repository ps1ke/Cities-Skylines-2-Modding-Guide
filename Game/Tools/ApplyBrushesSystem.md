# Game.Tools.ApplyBrushesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ApplyBrushesSystem : Game.GameSystemBase
{
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.ComponentTypeSet m_AppliedDeletedTypes;
    private Game.Tools.ApplyBrushesSystem+TypeHandle __TypeHandle;

    public ApplyBrushesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle ApplyCellMapBrush<TCell, TModifier>(Game.Simulation.CellMapSystem<TCell> cellMapSystem, TModifier modifier, Game.Tools.Brush brush, Unity.Entities.Entity prefab, Game.Prefabs.TerraformingType terraformingType, Game.Tools.ApplyBrushesSystem+ApplyCellMapBrushJob<TCell, TModifier> applyCellMapBrushJob);
    private System.Void ApplyHeight(Game.Tools.Brush brush, Unity.Entities.Entity prefab, Game.Prefabs.TerraformingType terraformingType);
    private System.Void ApplyMaterial(Game.Tools.Brush brush, Unity.Entities.Entity prefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem`  

```csharp
private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedDeletedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedDeletedTypes;
```

- `private Game.Tools.ApplyBrushesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ApplyBrushesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ApplyBrushesSystem()`  

```csharp
public ApplyBrushesSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private ApplyCellMapBrush<TCell, TModifier>(Game.Simulation.CellMapSystem<TCell> cellMapSystem, TModifier modifier, Game.Tools.Brush brush, Unity.Entities.Entity prefab, Game.Prefabs.TerraformingType terraformingType, Game.Tools.ApplyBrushesSystem+ApplyCellMapBrushJob<TCell, TModifier> applyCellMapBrushJob) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle ApplyCellMapBrush<TCell, TModifier>(Game.Simulation.CellMapSystem<TCell> cellMapSystem, TModifier modifier, Game.Tools.Brush brush, Unity.Entities.Entity prefab, Game.Prefabs.TerraformingType terraformingType, Game.Tools.ApplyBrushesSystem+ApplyCellMapBrushJob<TCell, TModifier> applyCellMapBrushJob);
```

- `private ApplyHeight(Game.Tools.Brush brush, Unity.Entities.Entity prefab, Game.Prefabs.TerraformingType terraformingType) : System.Void`  

```csharp
private System.Void ApplyHeight(Game.Tools.Brush brush, Unity.Entities.Entity prefab, Game.Prefabs.TerraformingType terraformingType);
```

- `private ApplyMaterial(Game.Tools.Brush brush, Unity.Entities.Entity prefab) : System.Void`  

```csharp
private System.Void ApplyMaterial(Game.Tools.Brush brush, Unity.Entities.Entity prefab);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Tools.ApplyBrushesSystem+ICellModifier<TCell>`  
- `Game.Tools.ApplyBrushesSystem+NaturalResourcesModifier`  
- `Game.Tools.ApplyBrushesSystem+GroundWaterModifier`  
- `Game.Tools.ApplyBrushesSystem+ApplyCellMapBrushJob<TCell, TModifier>`  
- `Game.Tools.ApplyBrushesSystem+TypeHandle`  

