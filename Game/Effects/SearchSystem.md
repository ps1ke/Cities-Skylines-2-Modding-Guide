# Game.Effects.SearchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SearchSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Effects.EffectFlagSystem m_EffectFlagSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Effects.EffectControlData m_EffectControlData;
    private Colossal.Collections.NativeQuadTree<Game.Effects.SourceInfo, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
    private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Effects.SearchSystem+AddedSource> m_AddedSources;
    private Unity.Entities.EntityQuery m_UpdatedEffectsQuery;
    private Unity.Entities.EntityQuery m_AllEffectsQuery;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private System.Boolean m_Loaded;
    private Game.Effects.SearchSystem+TypeHandle __TypeHandle;

    public SearchSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
    public static Game.Common.QuadTreeBoundsXZ GetBounds(Unity.Collections.NativeArray<Game.Objects.Transform> transforms, Unity.Collections.NativeArray<Game.Net.Curve> curves, System.Int32 index, Game.Prefabs.Effect effect, Unity.Entities.ComponentLookup`1[[Game.Prefabs.LightEffectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabLightEffectData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.AudioEffectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabAudioEffectData);
    private System.Boolean GetLoaded();
    public Colossal.Collections.NativeQuadTree<Game.Effects.SourceInfo, Game.Common.QuadTreeBoundsXZ> GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Effects.EffectFlagSystem m_EffectFlagSystem`  

```csharp
private Game.Effects.EffectFlagSystem m_EffectFlagSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Effects.EffectControlData m_EffectControlData`  

```csharp
private Game.Effects.EffectControlData m_EffectControlData;
```

- `private Colossal.Collections.NativeQuadTree<Game.Effects.SourceInfo, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Game.Effects.SourceInfo, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
```

- `private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Effects.SearchSystem+AddedSource> m_AddedSources`  

```csharp
private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Effects.SearchSystem+AddedSource> m_AddedSources;
```

- `private Unity.Entities.EntityQuery m_UpdatedEffectsQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedEffectsQuery;
```

- `private Unity.Entities.EntityQuery m_AllEffectsQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllEffectsQuery;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Effects.SearchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Effects.SearchSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SearchSystem()`  

```csharp
[Preserve]
	public SearchSystem()
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

- `public AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddSearchTreeReader(JobHandle jobHandle)
	{
		m_ReadDependencies = JobHandle.CombineDependencies(m_ReadDependencies, jobHandle);
	}
```

- `public AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddSearchTreeWriter(JobHandle jobHandle)
	{
		m_WriteDependencies = jobHandle;
	}
```

- `public static GetBounds(Unity.Collections.NativeArray<Game.Objects.Transform> transforms, Unity.Collections.NativeArray<Game.Net.Curve> curves, System.Int32 index, Game.Prefabs.Effect effect, Unity.Entities.ComponentLookup`1[[Game.Prefabs.LightEffectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabLightEffectData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.AudioEffectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabAudioEffectData) : Game.Common.QuadTreeBoundsXZ`  

```csharp
public static QuadTreeBoundsXZ GetBounds(NativeArray<Transform> transforms, NativeArray<Curve> curves, int index, Effect effect, ref ComponentLookup<LightEffectData> prefabLightEffectData, ref ComponentLookup<AudioEffectData> prefabAudioEffectData)
	{
		float3 @float = effect.m_Position;
		quaternion rotation = effect.m_Rotation;
		Transform value2;
		if (CollectionUtils.TryGet(curves, index, out var value))
		{
			@float = MathUtils.Position(value.m_Bezier, 0.5f);
		}
		else if (CollectionUtils.TryGet(transforms, index, out value2))
		{
			Transform transform = ObjectUtils.LocalToWorld(value2, @float, rotation);
			@float = transform.m_Position;
			rotation = transform.m_Rotation;
		}
		Bounds3 bounds = new Bounds3(@float - 1f, @float + 1f);
		int num = RenderingUtils.CalculateLodLimit(RenderingUtils.GetRenderingSize(new float3(1f)));
		if (prefabLightEffectData.TryGetComponent(effect.m_Effect, out var componentData))
		{
			bounds |= new Bounds3(@float - componentData.m_Range, @float + componentData.m_Range);
			num = math.min(num, componentData.m_MinLod);
		}
		if (prefabAudioEffectData.TryGetComponent(effect.m_Effect, out var componentData2) && math.any(componentData2.m_SourceSize > 0f))
		{
			Bounds3 bounds2 = new Bounds3(-componentData2.m_SourceSize, componentData2.m_SourceSize);
			bounds |= ObjectUtils.CalculateBounds(@float, rotation, bounds2);
			num = math.min(num, RenderingUtils.CalculateLodLimit(RenderingUtils.GetRenderingSize(componentData2.m_SourceSize)));
		}
		return new QuadTreeBoundsXZ(bounds, (BoundsMask)0, num);
	}
```

- `private GetLoaded() : System.Boolean`  

```csharp
private bool GetLoaded()
	{
		if (m_Loaded)
		{
			m_Loaded = false;
			return true;
		}
		return false;
	}
```

- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Game.Effects.SourceInfo, Game.Common.QuadTreeBoundsXZ>`  

```csharp
public NativeQuadTree<SourceInfo, QuadTreeBoundsXZ> GetSearchTree(bool readOnly, out JobHandle dependencies)
	{
		dependencies = (readOnly ? m_WriteDependencies : JobHandle.CombineDependencies(m_ReadDependencies, m_WriteDependencies));
		return m_SearchTree;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EffectFlagSystem = base.World.GetOrCreateSystemManaged<EffectFlagSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_EffectControlData = new EffectControlData(this);
		m_SearchTree = new NativeQuadTree<SourceInfo, QuadTreeBoundsXZ>(1f, Allocator.Persistent);
		m_AddedSources = new NativeParallelMultiHashMap<Entity, AddedSource>(1000, Allocator.Persistent);
		m_UpdatedEffectsQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<EnabledEffect>() },
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<EffectsUpdated>(),
				ComponentType.ReadOnly<BatchesUpdated>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Object>(),
				ComponentType.ReadOnly<Game.Events.Event>(),
				ComponentType.ReadOnly<Temp>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<EnabledEffect>(),
				ComponentType.ReadOnly<Object>(),
				ComponentType.ReadOnly<Static>()
			},
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<EffectsUpdated>(),
				ComponentType.ReadOnly<BatchesUpdated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_AllEffectsQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<EnabledEffect>() },
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Object>(),
				ComponentType.ReadOnly<Game.Events.Event>(),
				ComponentType.ReadOnly<Temp>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<EnabledEffect>(),
				ComponentType.ReadOnly<Object>(),
				ComponentType.ReadOnly<Static>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_SearchTree.Dispose();
		m_AddedSources.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		EntityQuery query = (loaded ? m_AllEffectsQuery : m_UpdatedEffectsQuery);
		if (!query.IsEmptyIgnoreFilter)
		{
			m_EffectControlData.Update(this, m_EffectFlagSystem.GetData(), m_SimulationSystem.frameIndex, m_ToolSystem.selected);
			JobHandle dependencies;
			JobHandle jobHandle = JobChunkExtensions.Schedule(new UpdateSearchTreeJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EditorContainerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_InterpolatedTransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabEffectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_EffectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabLightEffectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LightEffectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabAudioEffectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AudioEffectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabEffects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_Effect_RO_BufferLookup, ref base.CheckedStateRef),
				m_Loaded = loaded,
				m_SearchTree = GetSearchTree(readOnly: false, out dependencies),
				m_AddedSources = m_AddedSources,
				m_EffectControlData = m_EffectControlData
			}, query, JobHandle.CombineDependencies(base.Dependency, dependencies));
			AddSearchTreeWriter(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		JobHandle dependencies;
		NativeQuadTree<SourceInfo, QuadTreeBoundsXZ> searchTree = GetSearchTree(readOnly: false, out dependencies);
		dependencies.Complete();
		searchTree.Clear();
		m_AddedSources.Clear();
		m_Loaded = true;
	}
```


## Nested types

- `Game.Effects.SearchSystem+AddedSource`  
- `Game.Effects.SearchSystem+UpdateSearchTreeJob`  
- `Game.Effects.SearchSystem+TypeHandle`  

