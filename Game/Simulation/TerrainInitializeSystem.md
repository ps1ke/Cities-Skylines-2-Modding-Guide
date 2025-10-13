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
[Preserve]
	public TerrainInitializeSystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_TerrainMaterialSystem = base.World.GetOrCreateSystemManaged<TerrainMaterialSystem>();
		m_TerrainRenderSystem = base.World.GetOrCreateSystemManaged<TerrainRenderSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_WaterRenderSystem = base.World.GetOrCreateSystemManaged<WaterRenderSystem>();
		m_SnowSystem = base.World.GetOrCreateSystemManaged<SnowSystem>();
		m_TerrainPropertiesQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<TerrainPropertiesData>());
		m_TerrainMaterialPropertiesQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<TerrainMaterialPropertiesData>());
		RequireForUpdate(m_TerrainPropertiesQuery);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		Entity singletonEntity = m_TerrainPropertiesQuery.GetSingletonEntity();
		TerrainPropertiesPrefab prefab = m_PrefabSystem.GetPrefab<TerrainPropertiesPrefab>(singletonEntity);
		m_WaterSystem.MaxSpeed = prefab.m_WaterMaxSpeed;
	}
```


