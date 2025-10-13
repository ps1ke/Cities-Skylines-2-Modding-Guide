# Game.Simulation.TerrainInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `FormerlySerializedAs`, `CompilerGenerated`  

## Code

```csharp
public class TerrainInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_TerrainPropertiesQuery;
    private Unity.Entities.EntityQuery m_TerrainMaterialPropertiesQuery;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem;
    private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Rendering.WaterRenderSystem m_WaterRenderSystem;
    private Game.Simulation.SnowSystem m_SnowSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;

    public TerrainInitializeSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_TerrainPropertiesQuery`  

```csharp
private Unity.Entities.EntityQuery m_TerrainPropertiesQuery;
```

- `private Unity.Entities.EntityQuery m_TerrainMaterialPropertiesQuery`  

```csharp
private Unity.Entities.EntityQuery m_TerrainMaterialPropertiesQuery;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem`  

```csharp
private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem;
```

- `private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem`  

```csharp
private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Rendering.WaterRenderSystem m_WaterRenderSystem`  

```csharp
private Game.Rendering.WaterRenderSystem m_WaterRenderSystem;
```

- `private Game.Simulation.SnowSystem m_SnowSystem`  

```csharp
private Game.Simulation.SnowSystem m_SnowSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```


## Constructors

- `public TerrainInitializeSystem()`  

```csharp
public TerrainInitializeSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


