# Game.Simulation.CityModifierUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityModifierUpdateSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CityQuery;
    private Unity.Entities.EntityQuery m_EffectProviderQuery;
    private Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData m_CityModifierRefreshData;
    private Game.Simulation.CityModifierUpdateSystem+TypeHandle __TypeHandle;

    public CityModifierUpdateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Void AddToTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.CityModifierData> cityModifiers);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static System.Void InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList);
    public static System.Void InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.CityModifierData> cityModifiers);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CityQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityQuery;
```

- `private Unity.Entities.EntityQuery m_EffectProviderQuery`  

```csharp
private Unity.Entities.EntityQuery m_EffectProviderQuery;
```

- `private Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData m_CityModifierRefreshData`  

```csharp
private Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData m_CityModifierRefreshData;
```

- `private Game.Simulation.CityModifierUpdateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CityModifierUpdateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CityModifierUpdateSystem()`  

```csharp
[Preserve]
	public CityModifierUpdateSystem()
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

- `public static AddToTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.CityModifierData> cityModifiers) : System.Void`  

```csharp
public static void AddToTempList(NativeList<CityModifierData> tempModifierList, DynamicBuffer<CityModifierData> cityModifiers)
	{
		for (int i = 0; i < cityModifiers.Length; i++)
		{
			CityModifierData value = cityModifiers[i];
			int num = 0;
			while (true)
			{
				if (num < tempModifierList.Length)
				{
					CityModifierData value2 = tempModifierList[num];
					if (value2.m_Type == value.m_Type)
					{
						if (value2.m_Mode != value.m_Mode)
						{
							throw new Exception($"Modifier mode mismatch (type: {value.m_Type})");
						}
						value2.m_Range.min += value.m_Range.min;
						value2.m_Range.max += value.m_Range.max;
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

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 256;
	}
```

- `public static InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList) : System.Void`  

```csharp
public static void InitializeTempList(NativeList<CityModifierData> tempModifierList, DynamicBuffer<CityModifierData> cityModifiers)
	{
		tempModifierList.Clear();
		tempModifierList.AddRange(cityModifiers.AsNativeArray());
	}
```

- `public static InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.CityModifierData> cityModifiers) : System.Void`  

```csharp
public static void InitializeTempList(NativeList<CityModifierData> tempModifierList, DynamicBuffer<CityModifierData> cityModifiers)
	{
		tempModifierList.Clear();
		tempModifierList.AddRange(cityModifiers.AsNativeArray());
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityModifierRefreshData = new CityModifierRefreshData(this);
		m_CityQuery = GetEntityQuery(ComponentType.ReadWrite<Game.City.City>());
		m_EffectProviderQuery = GetEntityQuery(ComponentType.ReadOnly<CityEffectProvider>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_CityQuery);
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
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> effectProviderChunks = m_EffectProviderQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		m_CityModifierRefreshData.Update(this);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new UpdateCityModifiersJob
		{
			m_CityModifierRefreshData = m_CityModifierRefreshData,
			m_EffectProviderChunks = effectProviderChunks,
			m_PolicyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Policies_Policy_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_City_City_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CityModifierType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_City_CityModifier_RW_BufferTypeHandle, ref base.CheckedStateRef)
		}, m_CityQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		effectProviderChunks.Dispose(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.CityModifierUpdateSystem+UpdateCityModifiersJob`  
- `Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData`  
- `Game.Simulation.CityModifierUpdateSystem+TypeHandle`  

