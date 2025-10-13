# Game.Buildings.LocalEffectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LocalEffectSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdatedProvidersQuery;
    private Unity.Entities.EntityQuery m_AllProvidersQuery;
    private Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> m_SearchTree;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private System.Boolean m_Loaded;
    private Game.Buildings.LocalEffectSystem+TypeHandle __TypeHandle;

    public LocalEffectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddLocalEffectReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddLocalEffectWriter(Unity.Jobs.JobHandle jobHandle);
    public static System.Void AddToTempList(Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalModifierData> localModifiers, System.Boolean disabled);
    public static System.Boolean GetEffectBounds(Game.Objects.Transform transform, Game.Prefabs.LocalModifierData localModifier, Game.Buildings.LocalEffectSystem+EffectBounds& effectBounds);
    public static System.Boolean GetEffectBounds(Game.Objects.Transform transform, System.Single efficiency, Game.Prefabs.LocalModifierData localModifier, Game.Buildings.LocalEffectSystem+EffectBounds& effectBounds);
    private System.Boolean GetLoaded();
    public Game.Buildings.LocalEffectSystem+ReadData GetReadData(Unity.Jobs.JobHandle& dependencies);
    public Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    public static System.Void InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalModifierData> localModifiers);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedProvidersQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedProvidersQuery;
```

- `private Unity.Entities.EntityQuery m_AllProvidersQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllProvidersQuery;
```

- `private Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> m_SearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> m_SearchTree;
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

- `private Game.Buildings.LocalEffectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.LocalEffectSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LocalEffectSystem()`  

```csharp
[Preserve]
	public LocalEffectSystem()
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

- `public AddLocalEffectReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddLocalEffectReader(JobHandle jobHandle)
	{
		m_ReadDependencies = JobHandle.CombineDependencies(m_ReadDependencies, jobHandle);
	}
```

- `public AddLocalEffectWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddLocalEffectWriter(JobHandle jobHandle)
	{
		m_WriteDependencies = JobHandle.CombineDependencies(m_WriteDependencies, jobHandle);
	}
```

- `public static AddToTempList(Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalModifierData> localModifiers, System.Boolean disabled) : System.Void`  

```csharp
public static void AddToTempList(NativeList<LocalModifierData> tempModifierList, DynamicBuffer<LocalModifierData> localModifiers, bool disabled)
	{
		for (int i = 0; i < localModifiers.Length; i++)
		{
			LocalModifierData value = localModifiers[i];
			if (disabled)
			{
				value.m_Delta = default(Bounds1);
				value.m_Radius = default(Bounds1);
			}
			int num = 0;
			while (true)
			{
				if (num < tempModifierList.Length)
				{
					LocalModifierData value2 = tempModifierList[num];
					if (value2.m_Type == value.m_Type)
					{
						if (value2.m_Mode != value.m_Mode)
						{
							throw new Exception($"Modifier mode mismatch (type: {value.m_Type})");
						}
						value2.m_Delta.min += value.m_Delta.min;
						value2.m_Delta.max += value.m_Delta.max;
						switch (value2.m_RadiusCombineMode)
						{
						case ModifierRadiusCombineMode.Additive:
							value2.m_Radius.min += value.m_Radius.min;
							value2.m_Radius.max += value.m_Radius.max;
							break;
						case ModifierRadiusCombineMode.Maximal:
							value2.m_Radius.min = math.max(value2.m_Radius.min, value.m_Radius.min);
							value2.m_Radius.max = math.max(value2.m_Radius.max, value.m_Radius.max);
							break;
						}
						tempModifierList[num] = value2;
						break;
					}
					num++;
					continue;
				}
				tempModifierList.Add(in value);
				break;
			}
		}
	}
```

- `public static GetEffectBounds(Game.Objects.Transform transform, Game.Prefabs.LocalModifierData localModifier, Game.Buildings.LocalEffectSystem+EffectBounds& effectBounds) : System.Boolean`  

```csharp
public static bool GetEffectBounds(Transform transform, float efficiency, LocalModifierData localModifier, out EffectBounds effectBounds)
	{
		efficiency = math.sqrt(efficiency);
		float num = math.lerp(localModifier.m_Radius.min, localModifier.m_Radius.max, math.sqrt(efficiency));
		float num2 = math.lerp(localModifier.m_Delta.min, localModifier.m_Delta.max, efficiency);
		Bounds2 bounds = new Bounds2(transform.m_Position.xz - num, transform.m_Position.xz + num);
		uint typeMask = (uint)(1 << (int)localModifier.m_Type);
		num2 = math.select(num2, 1f / math.max(0.001f, 1f + num2) - 1f, localModifier.m_Mode == ModifierValueMode.InverseRelative);
		float2 delta = math.select(new float2(0f, num2), new float2(num2, 0f), localModifier.m_Mode == ModifierValueMode.Absolute);
		effectBounds = new EffectBounds(bounds, typeMask, delta);
		if (num >= 1f)
		{
			return num2 != 0f;
		}
		return false;
	}
```

- `public static GetEffectBounds(Game.Objects.Transform transform, System.Single efficiency, Game.Prefabs.LocalModifierData localModifier, Game.Buildings.LocalEffectSystem+EffectBounds& effectBounds) : System.Boolean`  

```csharp
public static bool GetEffectBounds(Transform transform, float efficiency, LocalModifierData localModifier, out EffectBounds effectBounds)
	{
		efficiency = math.sqrt(efficiency);
		float num = math.lerp(localModifier.m_Radius.min, localModifier.m_Radius.max, math.sqrt(efficiency));
		float num2 = math.lerp(localModifier.m_Delta.min, localModifier.m_Delta.max, efficiency);
		Bounds2 bounds = new Bounds2(transform.m_Position.xz - num, transform.m_Position.xz + num);
		uint typeMask = (uint)(1 << (int)localModifier.m_Type);
		num2 = math.select(num2, 1f / math.max(0.001f, 1f + num2) - 1f, localModifier.m_Mode == ModifierValueMode.InverseRelative);
		float2 delta = math.select(new float2(0f, num2), new float2(num2, 0f), localModifier.m_Mode == ModifierValueMode.Absolute);
		effectBounds = new EffectBounds(bounds, typeMask, delta);
		if (num >= 1f)
		{
			return num2 != 0f;
		}
		return false;
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

- `public GetReadData(Unity.Jobs.JobHandle& dependencies) : Game.Buildings.LocalEffectSystem+ReadData`  

```csharp
public ReadData GetReadData(out JobHandle dependencies)
	{
		dependencies = m_WriteDependencies;
		return new ReadData(m_SearchTree);
	}
```

- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds>`  

```csharp
public NativeQuadTree<EffectItem, EffectBounds> GetSearchTree(bool readOnly, out JobHandle dependencies)
	{
		dependencies = (readOnly ? m_WriteDependencies : JobHandle.CombineDependencies(m_ReadDependencies, m_WriteDependencies));
		return m_SearchTree;
	}
```

- `public static InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalModifierData> localModifiers) : System.Void`  

```csharp
public static void InitializeTempList(NativeList<LocalModifierData> tempModifierList, DynamicBuffer<LocalModifierData> localModifiers)
	{
		tempModifierList.Clear();
		tempModifierList.AddRange(localModifiers.AsNativeArray());
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_UpdatedProvidersQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<LocalEffectProvider>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_AllProvidersQuery = GetEntityQuery(ComponentType.ReadOnly<LocalEffectProvider>(), ComponentType.Exclude<Temp>());
		m_SearchTree = new NativeQuadTree<EffectItem, EffectBounds>(1f, Allocator.Persistent);
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
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_Loaded = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		EntityQuery entityQuery = (loaded ? m_AllProvidersQuery : m_UpdatedProvidersQuery);
		if (!entityQuery.IsEmptyIgnoreFilter)
		{
			JobHandle outJobHandle;
			NativeList<ArchetypeChunk> chunks = entityQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
			JobHandle dependencies;
			JobHandle jobHandle = IJobExtensions.Schedule(new UpdateLocalEffectsJob
			{
				m_Loaded = loaded,
				m_Chunks = chunks,
				m_SearchTree = GetSearchTree(readOnly: false, out dependencies),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DestroyedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_SignatureType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Signature_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LocalModifierData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_LocalModifierData_RO_BufferLookup, ref base.CheckedStateRef)
			}, JobHandle.CombineDependencies(base.Dependency, outJobHandle, dependencies));
			chunks.Dispose(jobHandle);
			AddLocalEffectWriter(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Buildings.LocalEffectSystem+EffectItem`  
- `Game.Buildings.LocalEffectSystem+EffectBounds`  
- `Game.Buildings.LocalEffectSystem+ReadData`  
- `Game.Buildings.LocalEffectSystem+UpdateLocalEffectsJob`  
- `Game.Buildings.LocalEffectSystem+TypeHandle`  

