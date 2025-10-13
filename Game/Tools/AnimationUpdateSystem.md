# Game.Tools.AnimationUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AnimationUpdateSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_AnimatedQuery;
    private Game.Tools.AnimationUpdateSystem+TypeHandle __TypeHandle;

    public AnimationUpdateSystem();

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

- `private Unity.Entities.EntityQuery m_AnimatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_AnimatedQuery;
```

- `private Game.Tools.AnimationUpdateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.AnimationUpdateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AnimationUpdateSystem()`  

```csharp
[Preserve]
	public AnimationUpdateSystem()
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
		m_UpdatedQuery = GetEntityQuery(ComponentType.ReadWrite<Animation>(), ComponentType.ReadOnly<Game.Objects.Transform>(), ComponentType.ReadOnly<Updated>(), ComponentType.Exclude<Deleted>());
		m_AnimatedQuery = GetEntityQuery(ComponentType.ReadOnly<Animation>(), ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<Game.Objects.Transform>());
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
		NativeParallelMultiHashMap<Entity, Animation> animationMap = new NativeParallelMultiHashMap<Entity, Animation>(100, Allocator.TempJob);
		AnimationMapJob jobData = new AnimationMapJob
		{
			m_AnimationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Animation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AnimationMap = animationMap
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new AnimationUpdateJob
		{
			m_DeltaTime = UnityEngine.Time.deltaTime,
			m_AnimationMap = animationMap,
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AnimationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Animation_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InterpolatedTransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef)
		}, dependsOn: JobChunkExtensions.Schedule(jobData, m_AnimatedQuery, base.Dependency), query: m_UpdatedQuery);
		animationMap.Dispose(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Tools.AnimationUpdateSystem+AnimationMapJob`  
- `Game.Tools.AnimationUpdateSystem+AnimationUpdateJob`  
- `Game.Tools.AnimationUpdateSystem+TypeHandle`  

