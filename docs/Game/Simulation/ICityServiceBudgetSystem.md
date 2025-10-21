# Game.Simulation.ICityServiceBudgetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ICityServiceBudgetSystem
{
    public abstract System.Int32 GetBalance();
    public abstract System.Void GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep);
    public abstract System.Int32 GetExpense(Game.City.ExpenseSource source);
    public abstract System.Int32 GetIncome(Game.City.IncomeSource source);
    public abstract System.Int32 GetMoneyDelta();
    public abstract System.Int32 GetNumberOfServiceBuildings(Unity.Entities.Entity serviceBuildingPrefab);
    public abstract System.Int32 GetServiceBudget(Unity.Entities.Entity servicePrefab);
    public abstract Unity.Entities.Entity[] GetServiceBuildings(Unity.Entities.Entity servicePrefab);
    public abstract System.Int32 GetServiceEfficiency(Unity.Entities.Entity servicePrefab, System.Int32 budget);
    public abstract System.Int32 GetTotalExpenses();
    public abstract System.Int32 GetTotalIncome();
    public abstract System.Int32 GetTotalTaxIncome();
    public abstract Unity.Mathematics.int2 GetWorkersAndWorkplaces(Unity.Entities.Entity serviceBuildingPrefab);
    public abstract System.Void SetServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32 percentage);
}
```


## Methods

- `public abstract GetBalance() : System.Int32`  

```csharp
public abstract System.Int32 GetBalance();
```

- `public abstract GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep) : System.Void`  

```csharp
public abstract System.Void GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep);
```

- `public abstract GetExpense(Game.City.ExpenseSource source) : System.Int32`  

```csharp
public abstract System.Int32 GetExpense(Game.City.ExpenseSource source);
```

- `public abstract GetIncome(Game.City.IncomeSource source) : System.Int32`  

```csharp
public abstract System.Int32 GetIncome(Game.City.IncomeSource source);
```

- `public abstract GetMoneyDelta() : System.Int32`  

```csharp
public abstract System.Int32 GetMoneyDelta();
```

- `public abstract GetNumberOfServiceBuildings(Unity.Entities.Entity serviceBuildingPrefab) : System.Int32`  

```csharp
public abstract System.Int32 GetNumberOfServiceBuildings(Unity.Entities.Entity serviceBuildingPrefab);
```

- `public abstract GetServiceBudget(Unity.Entities.Entity servicePrefab) : System.Int32`  

```csharp
public abstract System.Int32 GetServiceBudget(Unity.Entities.Entity servicePrefab);
```

- `public abstract GetServiceBuildings(Unity.Entities.Entity servicePrefab) : Unity.Entities.Entity[]`  

```csharp
public abstract Unity.Entities.Entity[] GetServiceBuildings(Unity.Entities.Entity servicePrefab);
```

- `public abstract GetServiceEfficiency(Unity.Entities.Entity servicePrefab, System.Int32 budget) : System.Int32`  

```csharp
public abstract System.Int32 GetServiceEfficiency(Unity.Entities.Entity servicePrefab, System.Int32 budget);
```

- `public abstract GetTotalExpenses() : System.Int32`  

```csharp
public abstract System.Int32 GetTotalExpenses();
```

- `public abstract GetTotalIncome() : System.Int32`  

```csharp
public abstract System.Int32 GetTotalIncome();
```

- `public abstract GetTotalTaxIncome() : System.Int32`  

```csharp
public abstract System.Int32 GetTotalTaxIncome();
```

- `public abstract GetWorkersAndWorkplaces(Unity.Entities.Entity serviceBuildingPrefab) : Unity.Mathematics.int2`  

```csharp
public abstract Unity.Mathematics.int2 GetWorkersAndWorkplaces(Unity.Entities.Entity serviceBuildingPrefab);
```

- `public abstract SetServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32 percentage) : System.Void`  

```csharp
public abstract System.Void SetServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32 percentage);
```


