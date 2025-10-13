# Game.Debug.TreeSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class TreeSpawnSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_Prefabs;
    private Unity.Entities.EntityQuery m_TreeQuery;

    public TreeSpawnSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_Prefabs`  

```csharp
private Unity.Entities.EntityQuery m_Prefabs;
```

- `private Unity.Entities.EntityQuery m_TreeQuery`  

```csharp
private Unity.Entities.EntityQuery m_TreeQuery;
```


## Constructors

- `public TreeSpawnSystem()`  

```csharp
[Preserve]
	public TreeSpawnSystem()
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
		m_LoadGameSystem = base.World.GetOrCreateSystemManaged<LoadGameSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_Prefabs = GetEntityQuery(ComponentType.ReadOnly<TreeData>(), ComponentType.Exclude<PlaceholderObjectElement>());
		m_TreeQuery = GetEntityQuery(ComponentType.ReadOnly<Tree>());
		RequireForUpdate(m_Prefabs);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_LoadGameSystem.context.purpose != Purpose.NewGame || !m_TreeQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		Unity.Mathematics.Random random = new Unity.Mathematics.Random((uint)DateTime.Now.Ticks);
		TerrainHeightData data = m_TerrainSystem.GetHeightData(waitForPending: true);
		NativeArray<Entity> nativeArray = m_Prefabs.ToEntityArray(Allocator.TempJob);
		try
		{
			Transform componentData2 = default(Transform);
			Tree componentData3 = default(Tree);
			for (int i = 0; i < 5000; i++)
			{
				Entity entity = nativeArray[random.NextInt(nativeArray.Length)];
				ObjectData componentData = base.EntityManager.GetComponentData<ObjectData>(entity);
				float2 @float = random.NextFloat2(-1000f, 1000f);
				componentData2.m_Rotation = quaternion.RotateY(random.NextFloat(MathF.PI * 2f));
				componentData2.m_Position = new float3(@float.x, 0f, @float.y);
				componentData2.m_Position.y = TerrainUtils.SampleHeight(ref data, componentData2.m_Position);
				switch (random.NextInt(13))
				{
				case 2:
				case 3:
					componentData3.m_State = TreeState.Teen;
					break;
				case 4:
				case 5:
				case 6:
				case 7:
					componentData3.m_State = TreeState.Adult;
					break;
				case 8:
				case 9:
				case 10:
				case 11:
					componentData3.m_State = TreeState.Elderly;
					break;
				case 12:
					componentData3.m_State = TreeState.Dead;
					break;
				default:
					componentData3.m_State = (TreeState)0;
					break;
				}
				componentData3.m_Growth = (byte)random.NextInt(256);
				Entity entity2 = base.EntityManager.CreateEntity(componentData.m_Archetype);
				base.EntityManager.SetComponentData(entity2, new PrefabRef(entity));
				base.EntityManager.SetComponentData(entity2, componentData2);
				base.EntityManager.SetComponentData(entity2, componentData3);
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```


