# Game.Simulation.DeliveryTruckAISystem+DeliveredStack

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct DeliveredStack
{
    public Unity.Entities.Entity vehicle;
    public Unity.Entities.Entity target;
    public Unity.Entities.Entity location;
    public Game.Economy.Resource resource;
    public System.Int32 amount;
    public Unity.Entities.Entity costPayer;
    public System.Single distance;
    public System.Boolean storageTransfer;
    public System.Boolean moneyRefund;

}
```


## Fields

- `public Unity.Entities.Entity vehicle`  

```csharp
public Unity.Entities.Entity vehicle;
```

- `public Unity.Entities.Entity target`  

```csharp
public Unity.Entities.Entity target;
```

- `public Unity.Entities.Entity location`  

```csharp
public Unity.Entities.Entity location;
```

- `public Game.Economy.Resource resource`  

```csharp
public Game.Economy.Resource resource;
```

- `public System.Int32 amount`  

```csharp
public System.Int32 amount;
```

- `public Unity.Entities.Entity costPayer`  

```csharp
public Unity.Entities.Entity costPayer;
```

- `public System.Single distance`  

```csharp
public System.Single distance;
```

- `public System.Boolean storageTransfer`  

```csharp
public System.Boolean storageTransfer;
```

- `public System.Boolean moneyRefund`  

```csharp
public System.Boolean moneyRefund;
```


