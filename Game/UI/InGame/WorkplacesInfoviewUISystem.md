# Game.UI.InGame.WorkplacesInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WorkplacesInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_WorkplaceQuery;
    private Unity.Entities.EntityQuery m_WorkplaceModifiedQuery;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.EmploymentData> m_EmployeesData;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.EmploymentData> m_WorkplacesData;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Workplaces;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Workers;
    private Unity.Collections.NativeArray<System.Int32> m_IntResults;
    private Unity.Collections.NativeArray<Game.UI.InGame.EmploymentData> m_EmploymentDataResults;
    private Game.UI.InGame.WorkplacesInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public WorkplacesInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Game.UI.InGame.EmploymentData GetEmployeesData();
    private System.Int32 GetWorkers();
    private System.Int32 GetWorkplaces();
    private Game.UI.InGame.EmploymentData GetWorkplacesData();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void ResetResults();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_WorkplaceQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkplaceQuery;
```

- `private Unity.Entities.EntityQuery m_WorkplaceModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkplaceModifiedQuery;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.EmploymentData> m_EmployeesData`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.EmploymentData> m_EmployeesData;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.EmploymentData> m_WorkplacesData`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.EmploymentData> m_WorkplacesData;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Workplaces`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Workplaces;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Workers`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Workers;
```

- `private Unity.Collections.NativeArray<System.Int32> m_IntResults`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_IntResults;
```

- `private Unity.Collections.NativeArray<Game.UI.InGame.EmploymentData> m_EmploymentDataResults`  

```csharp
private Unity.Collections.NativeArray<Game.UI.InGame.EmploymentData> m_EmploymentDataResults;
```

- `private Game.UI.InGame.WorkplacesInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.WorkplacesInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```

- `protected System.Boolean Modified { protected get }`  

```csharp
protected System.Boolean Modified { protected get; }
```


## Constructors

- `public WorkplacesInfoviewUISystem()`  

```csharp
[Preserve]
	public WorkplacesInfoviewUISystem()
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

- `private GetEmployeesData() : Game.UI.InGame.EmploymentData`  

```csharp
private EmploymentData GetEmployeesData()
	{
		if (!m_EmploymentDataResults.IsCreated || m_EmploymentDataResults.Length != 2)
		{
			return default(EmploymentData);
		}
		return m_EmploymentDataResults[1];
	}
```

- `private GetWorkers() : System.Int32`  

```csharp
private int GetWorkers()
	{
		if (!m_IntResults.IsCreated || m_IntResults.Length != 2)
		{
			return 0;
		}
		return m_IntResults[1];
	}
```

- `private GetWorkplaces() : System.Int32`  

```csharp
private int GetWorkplaces()
	{
		if (!m_IntResults.IsCreated || m_IntResults.Length != 2)
		{
			return 0;
		}
		return m_IntResults[0];
	}
```

- `private GetWorkplacesData() : Game.UI.InGame.EmploymentData`  

```csharp
private EmploymentData GetWorkplacesData()
	{
		if (!m_EmploymentDataResults.IsCreated || m_EmploymentDataResults.Length != 2)
		{
			return default(EmploymentData);
		}
		return m_EmploymentDataResults[0];
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_WorkplaceQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Employee>(),
				ComponentType.ReadOnly<WorkProvider>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<PropertyRenter>(),
				ComponentType.ReadOnly<Building>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Objects.OutsideConnection>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_WorkplaceModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Employee>(),
				ComponentType.ReadOnly<WorkProvider>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_IntResults = new NativeArray<int>(2, Allocator.Persistent);
		m_EmploymentDataResults = new NativeArray<EmploymentData>(2, Allocator.Persistent);
		AddBinding(m_WorkplacesData = new GetterValueBinding<EmploymentData>("workplaces", "workplacesData", GetWorkplacesData, new ValueWriter<EmploymentData>()));
		AddBinding(m_EmployeesData = new GetterValueBinding<EmploymentData>("workplaces", "employeesData", GetEmployeesData, new ValueWriter<EmploymentData>()));
		AddBinding(m_Workplaces = new GetterValueBinding<int>("workplaces", "workplaces", GetWorkplaces));
		AddBinding(m_Workers = new GetterValueBinding<int>("workplaces", "employees", GetWorkers));
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
		m_IntResults.Dispose();
		m_EmploymentDataResults.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		ResetResults();
		JobChunkExtensions.Schedule(new CalculateWorkplaceDataJob
		{
			m_EntityHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_EmployeeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_Employee_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_WorkProviderHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_WorkProvider_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PropertyRenterHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WorkplaceDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkplaceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableBuildingFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_IntResults = m_IntResults,
			m_EmploymentDataResults = m_EmploymentDataResults
		}, m_WorkplaceQuery, base.Dependency).Complete();
		m_EmployeesData.Update();
		m_WorkplacesData.Update();
		m_Workplaces.Update();
		m_Workers.Update();
	}
```

- `private ResetResults() : System.Void`  

```csharp
private void ResetResults()
	{
		for (int i = 0; i < 2; i++)
		{
			m_EmploymentDataResults[i] = default(EmploymentData);
			m_IntResults[i] = 0;
		}
	}
```


## Nested types

- `Game.UI.InGame.WorkplacesInfoviewUISystem+Result`  
- `Game.UI.InGame.WorkplacesInfoviewUISystem+CalculateWorkplaceDataJob`  
- `Game.UI.InGame.WorkplacesInfoviewUISystem+TypeHandle`  

