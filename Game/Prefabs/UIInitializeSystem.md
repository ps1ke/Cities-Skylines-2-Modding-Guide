# Game.Prefabs.UIInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UIInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_PolicyQuery;
    private Game.Prefabs.UIInitializeSystem+TypeHandle __TypeHandle;

    public System.Collections.Generic.IEnumerable<Game.Prefabs.PolicyPrefab> policies { get; }

    public UIInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void RemoveFrom(Unity.Entities.Entity entity, Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> uiGroupElements);
    private System.Void RemoveFrom(Unity.Entities.Entity entity, Unity.Entities.DynamicBuffer<Game.Prefabs.UnlockRequirement> unlockRequirements);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_PolicyQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolicyQuery;
```

- `private Game.Prefabs.UIInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.UIInitializeSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Collections.Generic.IEnumerable<Game.Prefabs.PolicyPrefab> policies { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Prefabs.PolicyPrefab> policies { get; }
```


## Constructors

- `public UIInitializeSystem()`  

```csharp
[Preserve]
	public UIInitializeSystem()
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
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<Deleted>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<UIObjectData>(),
				ComponentType.ReadOnly<UIAssetCategoryData>()
			}
		});
		m_PolicyQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<PolicyData>()
			}
		});
		RequireForUpdate(m_PrefabQuery);
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
		NativeArray<ArchetypeChunk> nativeArray = m_PrefabQuery.ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<UIObjectData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_UIObjectData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<UIAssetCategoryData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_UIAssetCategoryData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			CompleteDependency();
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
				NativeArray<UIObjectData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle);
				NativeArray<UIAssetCategoryData> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle2);
				for (int j = 0; j < nativeArray3.Length; j++)
				{
					Entity entity = nativeArray2[j];
					UIObjectData uIObjectData = nativeArray3[j];
					if (base.EntityManager.TryGetBuffer(uIObjectData.m_Group, isReadOnly: false, out DynamicBuffer<UIGroupElement> buffer))
					{
						RemoveFrom(entity, buffer);
					}
					if (base.EntityManager.TryGetBuffer(uIObjectData.m_Group, isReadOnly: false, out DynamicBuffer<UnlockRequirement> buffer2))
					{
						RemoveFrom(entity, buffer2);
					}
				}
				for (int k = 0; k < nativeArray4.Length; k++)
				{
					Entity entity2 = nativeArray2[k];
					UIAssetCategoryData uIAssetCategoryData = nativeArray4[k];
					if (base.EntityManager.TryGetBuffer(uIAssetCategoryData.m_Menu, isReadOnly: false, out DynamicBuffer<UIGroupElement> buffer3))
					{
						RemoveFrom(entity2, buffer3);
					}
					if (base.EntityManager.TryGetBuffer(uIAssetCategoryData.m_Menu, isReadOnly: false, out DynamicBuffer<UnlockRequirement> buffer4))
					{
						RemoveFrom(entity2, buffer4);
					}
				}
			}
		}
		finally
		{
			nativeArray.Dispose(base.Dependency);
		}
	}
```

- `private RemoveFrom(Unity.Entities.Entity entity, Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> uiGroupElements) : System.Void`  

```csharp
private void RemoveFrom(Entity entity, DynamicBuffer<UnlockRequirement> unlockRequirements)
	{
		for (int i = 0; i < unlockRequirements.Length; i++)
		{
			if (unlockRequirements[i].m_Prefab == entity)
			{
				unlockRequirements.RemoveAtSwapBack(i);
				break;
			}
		}
	}
```

- `private RemoveFrom(Unity.Entities.Entity entity, Unity.Entities.DynamicBuffer<Game.Prefabs.UnlockRequirement> unlockRequirements) : System.Void`  

```csharp
private void RemoveFrom(Entity entity, DynamicBuffer<UnlockRequirement> unlockRequirements)
	{
		for (int i = 0; i < unlockRequirements.Length; i++)
		{
			if (unlockRequirements[i].m_Prefab == entity)
			{
				unlockRequirements.RemoveAtSwapBack(i);
				break;
			}
		}
	}
```


## Nested types

- `Game.Prefabs.UIInitializeSystem+TypeHandle`  
- `Game.Prefabs.UIInitializeSystem+<get_policies>d__4`  

