# Game.Simulation.IBudgetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** interface abstract public  


## Properties

- `public System.Boolean HasData { get }`  
- `public System.UInt32 LastUpdate { get }`  

## Methods

- `public abstract GetCitizenWellbeing() : Unity.Mathematics.float2`  
- `public abstract GetCompanyCount(System.Boolean service, Game.Economy.Resource resource) : System.Int32`  
- `public abstract GetCompanyWealth(System.Boolean service, Game.Economy.Resource resource) : System.Int32`  
- `public abstract GetCompanyWorkers(System.Boolean service, Game.Economy.Resource resource) : Unity.Mathematics.int2`  
- `public abstract GetHouseholdCount() : System.Int32`  
- `public abstract GetHouseholdWealth() : System.Int32`  
- `public abstract GetHouseholdWorkers() : Unity.Mathematics.int2`  
- `public abstract GetLodgingData() : Unity.Mathematics.int2`  
- `public abstract GetTotalTradeWorth() : System.Int32`  
- `public abstract GetTouristCount() : System.Int32`  
- `public abstract GetTouristIncome() : System.Int32`  
- `public abstract GetTrade(Game.Economy.Resource resource) : System.Int32`  
- `public abstract GetTradeWorth(Game.Economy.Resource resource) : System.Int32`  

