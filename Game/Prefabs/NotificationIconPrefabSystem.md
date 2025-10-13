# Game.Prefabs.NotificationIconPrefabSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NotificationIconPrefabSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.NotificationIconRenderSystem m_NotificationIconRenderSystem;
    private Game.Prefabs.NotificationIconPrefabSystem+TypeHandle __TypeHandle;

    public NotificationIconPrefabSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.NotificationIconRenderSystem m_NotificationIconRenderSystem`  

```csharp
private Game.Rendering.NotificationIconRenderSystem m_NotificationIconRenderSystem;
```

- `private Game.Prefabs.NotificationIconPrefabSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.NotificationIconPrefabSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NotificationIconPrefabSystem()`  

```csharp
[Preserve]
	public NotificationIconPrefabSystem()
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
		m_NotificationIconRenderSystem = base.World.GetOrCreateSystemManaged<NotificationIconRenderSystem>();
		m_UpdatedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<NotificationIconData>(),
				ComponentType.ReadOnly<PrefabData>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_PrefabQuery = GetEntityQuery(ComponentType.ReadOnly<NotificationIconData>(), ComponentType.ReadOnly<PrefabData>(), ComponentType.Exclude<Deleted>());
		RequireForUpdate(m_UpdatedQuery);
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
		int num = 1;
		try
		{
			ComponentTypeHandle<PrefabData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<NotificationIconDisplayData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NotificationIconDisplayData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<PrefabData> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle);
				NativeArray<NotificationIconDisplayData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle2);
				for (int j = 0; j < nativeArray3.Length; j++)
				{
					NotificationIconPrefab prefab = m_PrefabSystem.GetPrefab<NotificationIconPrefab>(nativeArray2[j]);
					NotificationIconDisplayData value = nativeArray3[j];
					value.m_IconIndex = num++;
					value.m_MinParams = new float2(prefab.m_DisplaySize.min, prefab.m_PulsateAmplitude.min);
					value.m_MaxParams = new float2(prefab.m_DisplaySize.max, prefab.m_PulsateAmplitude.max);
					value.m_CategoryMask = math.select(2147483648u, value.m_CategoryMask, value.m_CategoryMask != 0);
					nativeArray3[j] = value;
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
		m_NotificationIconRenderSystem.DisplayDataUpdated();
	}
```


## Nested types

- `Game.Prefabs.NotificationIconPrefabSystem+TypeHandle`  

