# Game.UI.MapMetadataSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MapMetadataSystem : Game.GameSystemBase
{
    private Game.Simulation.PlanetarySystem m_PlanetarySystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private System.Single m_Area;
    private System.Single m_BuildableLand;
    private System.Single m_SurfaceWaterAvailability;
    private System.Single m_GroundWaterAvailability;
    private Game.UI.MapMetadataSystem+Resources m_Resources;
    private Game.UI.MapMetadataSystem+Connections m_Connections;
    private Unity.Entities.EntityQuery m_MapTileQuery;
    private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
    private System.String <mapName>k__BackingField;
    private Game.UI.MapMetadataSystem+TypeHandle __TypeHandle;

    public System.String mapName { get; set; }
    public System.String theme { get; }
    public Colossal.Mathematics.Bounds1 temperatureRange { get; }
    public System.Single cloudiness { get; }
    public System.Single precipitation { get; }
    public System.Single latitude { get; }
    public System.Single longitude { get; }
    public System.Single area { get; }
    public System.Single buildableLand { get; }
    public System.Single surfaceWaterAvailability { get; }
    public System.Single groundWaterAvailability { get; }
    public Game.UI.MapMetadataSystem+Resources resources { get; }
    public Game.UI.MapMetadataSystem+Connections connections { get; }

    public MapMetadataSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void UpdateConnections();
    private System.Void UpdateResources();
}
```


## Fields

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  

```csharp
private Game.Simulation.PlanetarySystem m_PlanetarySystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private System.Single m_Area`  

```csharp
private System.Single m_Area;
```

- `private System.Single m_BuildableLand`  

```csharp
private System.Single m_BuildableLand;
```

- `private System.Single m_SurfaceWaterAvailability`  

```csharp
private System.Single m_SurfaceWaterAvailability;
```

- `private System.Single m_GroundWaterAvailability`  

```csharp
private System.Single m_GroundWaterAvailability;
```

- `private Game.UI.MapMetadataSystem+Resources m_Resources`  

```csharp
private Game.UI.MapMetadataSystem+Resources m_Resources;
```

- `private Game.UI.MapMetadataSystem+Connections m_Connections`  

```csharp
private Game.UI.MapMetadataSystem+Connections m_Connections;
```

- `private Unity.Entities.EntityQuery m_MapTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_MapTileQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
```

- `private System.String <mapName>k__BackingField`  

```csharp
private System.String <mapName>k__BackingField;
```

- `private Game.UI.MapMetadataSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.MapMetadataSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.String mapName { get; set }`  

```csharp
public System.String mapName { get; set; }
```

- `public System.String theme { get }`  

```csharp
public System.String theme { get; }
```

- `public Colossal.Mathematics.Bounds1 temperatureRange { get }`  

```csharp
public Colossal.Mathematics.Bounds1 temperatureRange { get; }
```

- `public System.Single cloudiness { get }`  

```csharp
public System.Single cloudiness { get; }
```

- `public System.Single precipitation { get }`  

```csharp
public System.Single precipitation { get; }
```

- `public System.Single latitude { get }`  

```csharp
public System.Single latitude { get; }
```

- `public System.Single longitude { get }`  

```csharp
public System.Single longitude { get; }
```

- `public System.Single area { get }`  

```csharp
public System.Single area { get; }
```

- `public System.Single buildableLand { get }`  

```csharp
public System.Single buildableLand { get; }
```

- `public System.Single surfaceWaterAvailability { get }`  

```csharp
public System.Single surfaceWaterAvailability { get; }
```

- `public System.Single groundWaterAvailability { get }`  

```csharp
public System.Single groundWaterAvailability { get; }
```

- `public Game.UI.MapMetadataSystem+Resources resources { get }`  

```csharp
public Game.UI.MapMetadataSystem+Resources resources { get; }
```

- `public Game.UI.MapMetadataSystem+Connections connections { get }`  

```csharp
public Game.UI.MapMetadataSystem+Connections connections { get; }
```


## Constructors

- `public MapMetadataSystem()`  

```csharp
[Preserve]
	public MapMetadataSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PlanetarySystem = base.World.GetOrCreateSystemManaged<PlanetarySystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_MapTileQuery = GetEntityQuery(ComponentType.ReadOnly<MapTile>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_OutsideConnectionQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Objects.OutsideConnection>(),
				ComponentType.ReadOnly<Game.Objects.ElectricityOutsideConnection>(),
				ComponentType.ReadOnly<Game.Objects.WaterPipeOutsideConnection>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		CompleteDependency();
		UpdateResources();
		UpdateConnections();
	}
```

- `private UpdateConnections() : System.Void`  

```csharp
private void UpdateConnections()
	{
		m_Connections = default(Connections);
		ComponentTypeHandle<Game.Objects.ElectricityOutsideConnection> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_ElectricityOutsideConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<Game.Objects.WaterPipeOutsideConnection> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_WaterPipeOutsideConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<PrefabRef> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		NativeArray<ArchetypeChunk> nativeArray = m_OutsideConnectionQuery.ToArchetypeChunkArray(Allocator.Temp);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<PrefabRef> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle3);
				m_Connections.electricity |= archetypeChunk.Has(ref typeHandle);
				m_Connections.water |= archetypeChunk.Has(ref typeHandle2);
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					if (base.EntityManager.TryGetComponent<OutsideConnectionData>(nativeArray2[j].m_Prefab, out var component))
					{
						m_Connections.road |= (component.m_Type & OutsideConnectionTransferType.Road) != 0;
						m_Connections.train |= (component.m_Type & OutsideConnectionTransferType.Train) != 0;
						m_Connections.air |= (component.m_Type & OutsideConnectionTransferType.Air) != 0;
						m_Connections.ship |= (component.m_Type & OutsideConnectionTransferType.Ship) != 0;
					}
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `private UpdateResources() : System.Void`  

```csharp
private void UpdateResources()
	{
		m_Area = 0f;
		m_BuildableLand = 0f;
		m_SurfaceWaterAvailability = 0f;
		m_GroundWaterAvailability = 0f;
		m_Resources = default(Resources);
		BufferTypeHandle<MapFeatureElement> bufferTypeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_MapFeatureElement_RO_BufferTypeHandle, ref base.CheckedStateRef);
		NativeArray<ArchetypeChunk> nativeArray = m_MapTileQuery.ToArchetypeChunkArray(Allocator.Temp);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				BufferAccessor<MapFeatureElement> bufferAccessor = nativeArray[i].GetBufferAccessor(ref bufferTypeHandle);
				for (int j = 0; j < bufferAccessor.Length; j++)
				{
					DynamicBuffer<MapFeatureElement> dynamicBuffer = bufferAccessor[j];
					m_Area += dynamicBuffer[0].m_Amount;
					m_BuildableLand += dynamicBuffer[1].m_Amount;
					m_SurfaceWaterAvailability += dynamicBuffer[6].m_Amount;
					m_GroundWaterAvailability += dynamicBuffer[7].m_Amount;
					m_Resources.fertile += dynamicBuffer[2].m_Amount;
					m_Resources.forest += dynamicBuffer[3].m_Amount;
					m_Resources.oil += dynamicBuffer[4].m_Amount;
					m_Resources.ore += dynamicBuffer[5].m_Amount;
					m_Resources.fish += dynamicBuffer[8].m_Amount;
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```


## Nested types

- `Game.UI.MapMetadataSystem+Resources`  
- `Game.UI.MapMetadataSystem+Connections`  
- `Game.UI.MapMetadataSystem+TypeHandle`  

