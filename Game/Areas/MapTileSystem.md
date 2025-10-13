# Game.Areas.MapTileSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MapTileSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_MapTileQuery;
    private Unity.Entities.EntityQuery m_DeletedMapTileQuery;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_StartTiles;
    private Game.Areas.MapTileSystem+TypeHandle __TypeHandle;
    private static const System.Int32 LEGACY_GRID_WIDTH;
    private static const System.Int32 LEGACY_GRID_LENGTH;
    private static const System.Single LEGACY_CELL_SIZE;

    public MapTileSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddOwner(Unity.Mathematics.int2 tile, Unity.Collections.NativeArray<Unity.Entities.Entity> entities);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeList<Unity.Entities.Entity> GetStartTiles();
    private System.Void LegacyGenerateMapTiles(System.Boolean editorMode);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Entities.EntityQuery m_MapTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_MapTileQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedMapTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedMapTileQuery;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_StartTiles`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_StartTiles;
```

- `private Game.Areas.MapTileSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.MapTileSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 LEGACY_GRID_WIDTH`  

```csharp
private static const System.Int32 LEGACY_GRID_WIDTH;
```

- `private static const System.Int32 LEGACY_GRID_LENGTH`  

```csharp
private static const System.Int32 LEGACY_GRID_LENGTH;
```

- `private static const System.Single LEGACY_CELL_SIZE`  

```csharp
private static const System.Single LEGACY_CELL_SIZE;
```


## Constructors

- `public MapTileSystem()`  

```csharp
[Preserve]
	public MapTileSystem()
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

- `private AddOwner(Unity.Mathematics.int2 tile, Unity.Collections.NativeArray<Unity.Entities.Entity> entities) : System.Void`  

```csharp
private void AddOwner(int2 tile, NativeArray<Entity> entities)
	{
		int index = tile.y * 23 + tile.x;
		base.EntityManager.RemoveComponent<Native>(entities[index]);
		m_StartTiles.Add(entities[index]);
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetStartTiles() : Unity.Collections.NativeList<Unity.Entities.Entity>`  

```csharp
public NativeList<Entity> GetStartTiles()
	{
		return m_StartTiles;
	}
```

- `private LegacyGenerateMapTiles(System.Boolean editorMode) : System.Void`  

```csharp
private void LegacyGenerateMapTiles(bool editorMode)
	{
		if (!m_MapTileQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.DestroyEntity(m_MapTileQuery);
		}
		m_StartTiles.Clear();
		NativeArray<Entity> nativeArray = m_PrefabQuery.ToEntityArray(Allocator.TempJob);
		try
		{
			Entity entity = nativeArray[0];
			AreaData componentData = base.EntityManager.GetComponentData<AreaData>(entity);
			int entityCount = 529;
			NativeArray<Entity> entities = base.EntityManager.CreateEntity(componentData.m_Archetype, entityCount, Allocator.TempJob);
			if (!editorMode)
			{
				base.EntityManager.AddComponent<Native>(entities);
			}
			AddOwner(new int2(10, 10), entities);
			AddOwner(new int2(11, 10), entities);
			AddOwner(new int2(12, 10), entities);
			AddOwner(new int2(10, 11), entities);
			AddOwner(new int2(11, 11), entities);
			AddOwner(new int2(12, 11), entities);
			AddOwner(new int2(10, 12), entities);
			AddOwner(new int2(11, 12), entities);
			AddOwner(new int2(12, 12), entities);
			IJobParallelForExtensions.Schedule(new GenerateMapTilesJob
			{
				m_Entities = entities,
				m_Prefab = entity,
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RW_ComponentLookup, ref base.CheckedStateRef),
				m_AreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Area_RW_ComponentLookup, ref base.CheckedStateRef),
				m_NodeData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RW_BufferLookup, ref base.CheckedStateRef)
			}, entities.Length, 4).Complete();
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabQuery = GetEntityQuery(ComponentType.ReadOnly<MapTileData>(), ComponentType.ReadOnly<AreaData>(), ComponentType.ReadOnly<PrefabData>(), ComponentType.Exclude<Locked>());
		m_MapTileQuery = GetEntityQuery(ComponentType.ReadOnly<MapTile>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_DeletedMapTileQuery = GetEntityQuery(ComponentType.ReadOnly<MapTile>(), ComponentType.ReadOnly<Deleted>(), ComponentType.Exclude<Temp>());
		m_StartTiles = new NativeList<Entity>(Allocator.Persistent);
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_StartTiles.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_DeletedMapTileQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		base.Dependency.Complete();
		foreach (Entity item in m_DeletedMapTileQuery.ToEntityArray(Allocator.Temp))
		{
			int num = m_StartTiles.IndexOf(item);
			if (num >= 0)
			{
				m_StartTiles.RemoveAtSwapBack(num);
			}
		}
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if (context.purpose == Purpose.NewGame)
		{
			if (context.version >= Version.editorMapTiles)
			{
				for (int i = 0; i < m_StartTiles.Length; i++)
				{
					if (m_StartTiles[i] == Entity.Null)
					{
						m_StartTiles.RemoveAtSwapBack(i);
					}
				}
				if (m_StartTiles.Length != 0)
				{
					base.EntityManager.RemoveComponent<Native>(m_StartTiles.AsArray());
				}
			}
			else
			{
				LegacyGenerateMapTiles(editorMode: false);
			}
		}
		else if (context.purpose == Purpose.NewMap)
		{
			LegacyGenerateMapTiles(editorMode: true);
		}
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_StartTiles.Clear();
	}
```


## Nested types

- `Game.Areas.MapTileSystem+GenerateMapTilesJob`  
- `Game.Areas.MapTileSystem+TypeHandle`  

