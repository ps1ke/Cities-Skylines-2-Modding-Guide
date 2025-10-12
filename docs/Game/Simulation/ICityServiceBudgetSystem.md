# Game.Simulation.ICityServiceBudgetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** interface abstract public  


## Methods

- `public abstract GetBalance() : System.Int32`  
- `public abstract GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep) : System.Void`  
- `public abstract GetExpense(Game.City.ExpenseSource source) : System.Int32`  
- `public abstract GetIncome(Game.City.IncomeSource source) : System.Int32`  
- `public abstract GetMoneyDelta() : System.Int32`  
- `public abstract GetNumberOfServiceBuildings(Unity.Entities.Entity serviceBuildingPrefab) : System.Int32`  
- `public abstract GetServiceBudget(Unity.Entities.Entity servicePrefab) : System.Int32`  
- `public abstract GetServiceBuildings(Unity.Entities.Entity servicePrefab) : Unity.Entities.Entity[]`  
- `public abstract GetServiceEfficiency(Unity.Entities.Entity servicePrefab, System.Int32 budget) : System.Int32`  
- `public abstract GetTotalExpenses() : System.Int32`  
- `public abstract GetTotalIncome() : System.Int32`  
- `public abstract GetTotalTaxIncome() : System.Int32`  
- `public abstract GetWorkersAndWorkplaces(Unity.Entities.Entity serviceBuildingPrefab) : Unity.Mathematics.int2`  
- `public abstract SetServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32 percentage) : System.Void`  

