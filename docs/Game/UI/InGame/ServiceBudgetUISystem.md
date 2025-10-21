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
public ServiceBudgetUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetTotalBudget(Unity.Entities.Entity service, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees) : System.Int32`  

```csharp
private System.Int32 GetTotalBudget(Unity.Entities.Entity service, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `private ResetService(Unity.Entities.Entity service) : System.Void`  

```csharp
private System.Void ResetService(Unity.Entities.Entity service);
```

- `private SetServiceBudget(Unity.Entities.Entity service, System.Int32 percentage) : System.Void`  

```csharp
private System.Void SetServiceBudget(Unity.Entities.Entity service, System.Int32 percentage);
```

- `private SetServiceFee(Game.City.PlayerResource resource, System.Single amount) : System.Void`  

```csharp
private System.Void SetServiceFee(Game.City.PlayerResource resource, System.Single amount);
```

- `private WriteServiceDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity serviceEntity) : System.Void`  

```csharp
private System.Void WriteServiceDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity serviceEntity);
```

- `private WriteServiceFees(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity serviceEntity) : System.Void`  

```csharp
private System.Void WriteServiceFees(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity serviceEntity);
```

- `private WriteServices(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void WriteServices(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.InGame.ServiceBudgetUISystem+ServiceInfo`  
- `Game.UI.InGame.ServiceBudgetUISystem+PlayerResourceReader`  
- `Game.UI.InGame.ServiceBudgetUISystem+TypeHandle`  

