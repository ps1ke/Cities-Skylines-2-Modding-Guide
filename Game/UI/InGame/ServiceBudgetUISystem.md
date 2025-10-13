# Game.UI.InGame.ServiceBudgetUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ServiceBudgetUISystem : Game.UI.UISystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem;
    private Game.Simulation.IServiceFeeSystem m_ServiceFeeSystem;
    private Unity.Entities.EntityQuery m_ServiceQuery;
    private Game.UI.InGame.ServiceBudgetUISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_2035132663_0;
    private Unity.Entities.EntityQuery __query_2035132663_1;
    private Unity.Entities.EntityQuery __query_2035132663_2;
    private Unity.Entities.EntityQuery __query_2035132663_3;
    private static const System.String kGroup;

    public ServiceBudgetUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Int32 GetTotalBudget(Unity.Entities.Entity service, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    private System.Void ResetService(Unity.Entities.Entity service);
    private System.Void SetServiceBudget(Unity.Entities.Entity service, System.Int32 percentage);
    private System.Void SetServiceFee(Game.City.PlayerResource resource, System.Single amount);
    private System.Void WriteServiceDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity serviceEntity);
    private System.Void WriteServiceFees(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity serviceEntity);
    private System.Void WriteServices(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem`  

```csharp
private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem;
```

- `private Game.Simulation.IServiceFeeSystem m_ServiceFeeSystem`  

```csharp
private Game.Simulation.IServiceFeeSystem m_ServiceFeeSystem;
```

- `private Unity.Entities.EntityQuery m_ServiceQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceQuery;
```

- `private Game.UI.InGame.ServiceBudgetUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.ServiceBudgetUISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_2035132663_0`  

```csharp
private Unity.Entities.EntityQuery __query_2035132663_0;
```

- `private Unity.Entities.EntityQuery __query_2035132663_1`  

```csharp
private Unity.Entities.EntityQuery __query_2035132663_1;
```

- `private Unity.Entities.EntityQuery __query_2035132663_2`  

```csharp
private Unity.Entities.EntityQuery __query_2035132663_2;
```

- `private Unity.Entities.EntityQuery __query_2035132663_3`  

```csharp
private Unity.Entities.EntityQuery __query_2035132663_3;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public ServiceBudgetUISystem()`  

```csharp
[Preserve]
	public ServiceBudgetUISystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<ServiceFeeParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_2035132663_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<OutsideTradeParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_2035132663_1 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<CitizenHappinessParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_2035132663_2 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<BuildingEfficiencyParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_2035132663_3 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `private GetTotalBudget(Unity.Entities.Entity service, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees) : System.Int32`  

```csharp
private int GetTotalBudget(Entity service, DynamicBuffer<ServiceFee> fees)
	{
		m_CityServiceBudgetSystem.GetEstimatedServiceBudget(service, out var upkeep);
		int num = -upkeep;
		if (base.EntityManager.TryGetBuffer(service, isReadOnly: true, out DynamicBuffer<CollectedCityServiceFeeData> buffer))
		{
			foreach (CollectedCityServiceFeeData item in buffer)
			{
				PlayerResource playerResource = (PlayerResource)item.m_PlayerResource;
				float fee;
				int num2 = (ServiceFeeSystem.TryGetFee(playerResource, fees, out fee) ? m_ServiceFeeSystem.GetServiceFeeIncomeEstimate(playerResource, fee) : m_ServiceFeeSystem.GetServiceFees(playerResource).x);
				int3 serviceFees = m_ServiceFeeSystem.GetServiceFees(playerResource);
				num += num2;
				num += serviceFees.y;
				num -= serviceFees.z;
			}
		}
		return num;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_CityServiceBudgetSystem = base.World.GetOrCreateSystemManaged<CityServiceBudgetSystem>();
		m_ServiceFeeSystem = base.World.GetOrCreateSystemManaged<ServiceFeeSystem>();
		m_ServiceQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<UIObjectData>(), ComponentType.ReadOnly<ServiceData>());
		RequireForUpdate<ServiceFeeParameterData>();
		RequireForUpdate<OutsideTradeParameterData>();
		RequireForUpdate<CitizenHappinessParameterData>();
		RequireForUpdate<BuildingEfficiencyParameterData>();
		AddUpdateBinding(new RawValueBinding("serviceBudget", "services", WriteServices));
		AddUpdateBinding(new RawMapBinding<Entity>("serviceBudget", "serviceDetails", WriteServiceDetails));
		AddBinding(new TriggerBinding<Entity, int>("serviceBudget", "setServiceBudget", SetServiceBudget));
		AddBinding(new TriggerBinding<PlayerResource, float>("serviceBudget", "setServiceFee", SetServiceFee, new PlayerResourceReader()));
		AddBinding(new TriggerBinding<Entity>("serviceBudget", "resetService", ResetService));
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

- `private ResetService(Unity.Entities.Entity service) : System.Void`  

```csharp
private void ResetService(Entity service)
	{
		SetServiceBudget(service, 100);
		if (!base.EntityManager.TryGetBuffer(service, isReadOnly: true, out DynamicBuffer<CollectedCityServiceFeeData> buffer))
		{
			return;
		}
		ServiceFeeParameterData singleton = __query_2035132663_0.GetSingleton<ServiceFeeParameterData>();
		foreach (CollectedCityServiceFeeData item in buffer)
		{
			PlayerResource playerResource = (PlayerResource)item.m_PlayerResource;
			SetServiceFee(playerResource, singleton.GetFeeParameters(playerResource).m_Default);
		}
	}
```

- `private SetServiceBudget(Unity.Entities.Entity service, System.Int32 percentage) : System.Void`  

```csharp
private void SetServiceBudget(Entity service, int percentage)
	{
		m_CityServiceBudgetSystem.SetServiceBudget(service, percentage);
	}
```

- `private SetServiceFee(Game.City.PlayerResource resource, System.Single amount) : System.Void`  

```csharp
private void SetServiceFee(PlayerResource resource, float amount)
	{
		if (resource != PlayerResource.Parking && base.EntityManager.HasComponent<ServiceFee>(m_CitySystem.City))
		{
			DynamicBuffer<ServiceFee> buffer = base.EntityManager.GetBuffer<ServiceFee>(m_CitySystem.City);
			ServiceFeeSystem.SetFee(resource, buffer, amount);
		}
	}
```

- `private WriteServiceDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity serviceEntity) : System.Void`  

```csharp
private void WriteServiceDetails(IJsonWriter writer, Entity serviceEntity)
	{
		if (base.EntityManager.TryGetComponent<ServiceData>(serviceEntity, out var component) && base.EntityManager.TryGetComponent<PrefabData>(serviceEntity, out var component2))
		{
			ServicePrefab prefab = m_PrefabSystem.GetPrefab<ServicePrefab>(component2);
			m_CityServiceBudgetSystem.GetEstimatedServiceBudget(serviceEntity, out var upkeep);
			writer.TypeBegin("serviceBudget.ServiceDetails");
			writer.PropertyName("entity");
			writer.Write(serviceEntity);
			writer.PropertyName("name");
			writer.Write(prefab.name);
			writer.PropertyName("icon");
			writer.Write(ImageSystem.GetIcon(prefab));
			writer.PropertyName("locked");
			writer.Write(base.EntityManager.HasEnabledComponent<Locked>(serviceEntity));
			writer.PropertyName("budgetAdjustable");
			writer.Write(component.m_BudgetAdjustable);
			int serviceBudget = m_CityServiceBudgetSystem.GetServiceBudget(serviceEntity);
			writer.PropertyName("budgetPercentage");
			writer.Write(serviceBudget);
			writer.PropertyName("efficiency");
			writer.Write(m_CityServiceBudgetSystem.GetServiceEfficiency(serviceEntity, serviceBudget));
			writer.PropertyName("upkeep");
			writer.Write(-upkeep);
			writer.PropertyName("fees");
			WriteServiceFees(writer, serviceEntity);
			writer.TypeEnd();
		}
		else
		{
			writer.WriteNull();
		}
	}
```

- `private WriteServiceFees(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity serviceEntity) : System.Void`  

```csharp
private void WriteServiceFees(IJsonWriter writer, Entity serviceEntity)
	{
		if (base.EntityManager.TryGetBuffer(serviceEntity, isReadOnly: true, out DynamicBuffer<CollectedCityServiceFeeData> buffer) && buffer.Length > 0)
		{
			ServiceFeeParameterData feeParameters = __query_2035132663_0.GetSingleton<ServiceFeeParameterData>();
			OutsideTradeParameterData singleton = __query_2035132663_1.GetSingleton<OutsideTradeParameterData>();
			CitizenHappinessParameterData happinessParameters = __query_2035132663_2.GetSingleton<CitizenHappinessParameterData>();
			BuildingEfficiencyParameterData efficiencyParameters = __query_2035132663_3.GetSingleton<BuildingEfficiencyParameterData>();
			DynamicBuffer<ServiceFee> buffer2 = base.EntityManager.GetBuffer<ServiceFee>(m_CitySystem.City, isReadOnly: true);
			writer.ArrayBegin(buffer.Length);
			foreach (CollectedCityServiceFeeData item in buffer)
			{
				PlayerResource playerResource = (PlayerResource)item.m_PlayerResource;
				FeeParameters feeParameters2 = feeParameters.GetFeeParameters(playerResource);
				float fee;
				int value = (ServiceFeeSystem.TryGetFee(playerResource, buffer2, out fee) ? m_ServiceFeeSystem.GetServiceFeeIncomeEstimate(playerResource, fee) : m_ServiceFeeSystem.GetServiceFees(playerResource).x);
				float relativeFee = fee / feeParameters2.m_Default;
				int3 serviceFees = m_ServiceFeeSystem.GetServiceFees(playerResource);
				writer.TypeBegin("serviceBudget.ServiceFee");
				writer.PropertyName("resource");
				writer.Write((int)playerResource);
				writer.PropertyName("name");
				writer.Write(Enum.GetName(typeof(PlayerResource), playerResource));
				writer.PropertyName("fee");
				writer.Write(fee);
				writer.PropertyName("min");
				writer.Write(0);
				writer.PropertyName("max");
				writer.Write(feeParameters2.m_Max);
				writer.PropertyName("adjustable");
				writer.Write(feeParameters2.m_Adjustable);
				writer.PropertyName("importable");
				writer.Write(singleton.Importable(playerResource));
				writer.PropertyName("exportable");
				writer.Write(singleton.Exportable(playerResource));
				writer.PropertyName("incomeInternal");
				writer.Write(value);
				writer.PropertyName("incomeExports");
				writer.Write(serviceFees.y);
				writer.PropertyName("expenseImports");
				writer.Write(-serviceFees.z);
				writer.PropertyName("consumptionMultiplier");
				writer.Write(ServiceFeeSystem.GetConsumptionMultiplier(playerResource, relativeFee, in feeParameters));
				writer.PropertyName("efficiencyMultiplier");
				writer.Write(ServiceFeeSystem.GetEfficiencyMultiplier(playerResource, relativeFee, in efficiencyParameters));
				writer.PropertyName("happinessEffect");
				writer.Write(ServiceFeeSystem.GetHappinessEffect(playerResource, relativeFee, in happinessParameters));
				writer.TypeEnd();
			}
			writer.ArrayEnd();
		}
		else
		{
			writer.WriteEmptyArray();
		}
	}
```

- `private WriteServices(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void WriteServices(IJsonWriter writer)
	{
		NativeList<UIObjectInfo> sortedObjects = UIObjectInfo.GetSortedObjects(m_ServiceQuery, Allocator.Temp);
		DynamicBuffer<ServiceFee> buffer = base.EntityManager.GetBuffer<ServiceFee>(m_CitySystem.City, isReadOnly: true);
		writer.ArrayBegin(sortedObjects.Length);
		foreach (UIObjectInfo item in sortedObjects)
		{
			ServicePrefab prefab = m_PrefabSystem.GetPrefab<ServicePrefab>(item.prefabData);
			int totalBudget = GetTotalBudget(item.entity, buffer);
			writer.Write(new ServiceInfo
			{
				entity = item.entity,
				name = prefab.name,
				icon = ImageSystem.GetIcon(prefab),
				locked = base.EntityManager.HasEnabledComponent<Locked>(item.entity),
				budget = totalBudget
			});
		}
		writer.ArrayEnd();
		sortedObjects.Dispose();
	}
```


## Nested types

- `Game.UI.InGame.ServiceBudgetUISystem+ServiceInfo`  
- `Game.UI.InGame.ServiceBudgetUISystem+PlayerResourceReader`  
- `Game.UI.InGame.ServiceBudgetUISystem+TypeHandle`  

