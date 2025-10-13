# Game.Simulation.IBudgetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IBudgetSystem
{
    public System.Boolean HasData { get; }
    public System.UInt32 LastUpdate { get; }

    public abstract Unity.Mathematics.float2 GetCitizenWellbeing();
    public abstract System.Int32 GetCompanyCount(System.Boolean service, Game.Economy.Resource resource);
    public abstract System.Int32 GetCompanyWealth(System.Boolean service, Game.Economy.Resource resource);
    public abstract Unity.Mathematics.int2 GetCompanyWorkers(System.Boolean service, Game.Economy.Resource resource);
    public abstract System.Int32 GetHouseholdCount();
    public abstract System.Int32 GetHouseholdWealth();
    public abstract Unity.Mathematics.int2 GetHouseholdWorkers();
    public abstract Unity.Mathematics.int2 GetLodgingData();
    public abstract System.Int32 GetTotalTradeWorth();
    public abstract System.Int32 GetTouristCount();
    public abstract System.Int32 GetTouristIncome();
    public abstract System.Int32 GetTrade(Game.Economy.Resource resource);
    public abstract System.Int32 GetTradeWorth(Game.Economy.Resource resource);
}
```


## Properties

- `public System.Boolean HasData { get }`  

```csharp
public System.Boolean HasData { get; }
```

- `public System.UInt32 LastUpdate { get }`  

```csharp
public System.UInt32 LastUpdate { get; }
```


## Methods

- `public abstract GetCitizenWellbeing() : Unity.Mathematics.float2`  

```csharp
public abstract Unity.Mathematics.float2 GetCitizenWellbeing();
```

- `public abstract GetCompanyCount(System.Boolean service, Game.Economy.Resource resource) : System.Int32`  

```csharp
public abstract System.Int32 GetCompanyCount(System.Boolean service, Game.Economy.Resource resource);
```

- `public abstract GetCompanyWealth(System.Boolean service, Game.Economy.Resource resource) : System.Int32`  

```csharp
public abstract System.Int32 GetCompanyWealth(System.Boolean service, Game.Economy.Resource resource);
```

- `public abstract GetCompanyWorkers(System.Boolean service, Game.Economy.Resource resource) : Unity.Mathematics.int2`  

```csharp
public abstract Unity.Mathematics.int2 GetCompanyWorkers(System.Boolean service, Game.Economy.Resource resource);
```

- `public abstract GetHouseholdCount() : System.Int32`  

```csharp
public abstract System.Int32 GetHouseholdCount();
```

- `public abstract GetHouseholdWealth() : System.Int32`  

```csharp
public abstract System.Int32 GetHouseholdWealth();
```

- `public abstract GetHouseholdWorkers() : Unity.Mathematics.int2`  

```csharp
public abstract Unity.Mathematics.int2 GetHouseholdWorkers();
```

- `public abstract GetLodgingData() : Unity.Mathematics.int2`  

```csharp
public abstract Unity.Mathematics.int2 GetLodgingData();
```

- `public abstract GetTotalTradeWorth() : System.Int32`  

```csharp
public abstract System.Int32 GetTotalTradeWorth();
```

- `public abstract GetTouristCount() : System.Int32`  

```csharp
public abstract System.Int32 GetTouristCount();
```

- `public abstract GetTouristIncome() : System.Int32`  

```csharp
public abstract System.Int32 GetTouristIncome();
```

- `public abstract GetTrade(Game.Economy.Resource resource) : System.Int32`  

```csharp
public abstract System.Int32 GetTrade(Game.Economy.Resource resource);
```

- `public abstract GetTradeWorth(Game.Economy.Resource resource) : System.Int32`  

```csharp
public abstract System.Int32 GetTradeWorth(Game.Economy.Resource resource);
```


