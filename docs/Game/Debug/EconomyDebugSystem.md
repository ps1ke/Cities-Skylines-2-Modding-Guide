# Game.Debug.EconomyDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EconomyDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_AgentQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Debug.BaseDebugSystem+Option m_ResidentialOption;
    private Game.Debug.BaseDebugSystem+Option m_CommercialOption;
    private Game.Debug.BaseDebugSystem+Option m_CommercialStorageOption;
    private Game.Debug.BaseDebugSystem+Option m_IndustrialOption;
    private Game.Debug.BaseDebugSystem+Option m_UntaxedIncomeOption;
    private Game.Debug.BaseDebugSystem+Option m_StorageUsedOption;
    private Game.Debug.BaseDebugSystem+Option m_HouseholdNeedOption;
    private Game.Debug.BaseDebugSystem+Option m_ProfitabilityOption;
    private Game.Debug.BaseDebugSystem+Option m_TradeCostOption;
    private Game.Debug.EconomyDebugSystem+TypeHandle __TypeHandle;

    public EconomyDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public static System.Void PrintAgeDebug();
    public static System.Void PrintCompanyDebug(Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas);
    public static System.Void PrintSchoolDebug();
    public static System.Void PrintTradeDebug(Game.Simulation.ITradeSystem tradeSystem, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects);
    public static System.Void RemoveExtraCompanies();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_AgentQuery`  

```csharp
private Unity.Entities.EntityQuery m_AgentQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_ResidentialOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ResidentialOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_CommercialOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_CommercialOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_CommercialStorageOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_CommercialStorageOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_IndustrialOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_IndustrialOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_UntaxedIncomeOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_UntaxedIncomeOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_StorageUsedOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_StorageUsedOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_HouseholdNeedOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_HouseholdNeedOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ProfitabilityOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ProfitabilityOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_TradeCostOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_TradeCostOption;
```

- `private Game.Debug.EconomyDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.EconomyDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EconomyDebugSystem()`  

```csharp
public EconomyDebugSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public static PrintAgeDebug() : System.Void`  

```csharp
public static System.Void PrintAgeDebug();
```

- `public static PrintCompanyDebug(Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas) : System.Void`  

```csharp
public static System.Void PrintCompanyDebug(Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas);
```

- `public static PrintSchoolDebug() : System.Void`  

```csharp
public static System.Void PrintSchoolDebug();
```

- `public static PrintTradeDebug(Game.Simulation.ITradeSystem tradeSystem, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects) : System.Void`  

```csharp
public static System.Void PrintTradeDebug(Game.Simulation.ITradeSystem tradeSystem, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects);
```

- `public static RemoveExtraCompanies() : System.Void`  

```csharp
public static System.Void RemoveExtraCompanies();
```


## Nested types

- `Game.Debug.EconomyDebugSystem+EconomyGizmoJob`  
- `Game.Debug.EconomyDebugSystem+TypeHandle`  

