# Game.Simulation.IMapTilePurchaseSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IMapTilePurchaseSystem
{
    public System.Boolean selecting { get; set; }
    public System.Int32 cost { get; }
    public Game.Simulation.TilePurchaseErrorFlags status { get; }

    public abstract System.Single GetFeatureAmount(Game.Areas.MapFeature feature);
    public abstract System.Void PurchaseSelection();
    public abstract System.Void Update();
}
```


## Properties

- `public System.Boolean selecting { get; set }`  

```csharp
public System.Boolean selecting { get; set; }
```

- `public System.Int32 cost { get }`  

```csharp
public System.Int32 cost { get; }
```

- `public Game.Simulation.TilePurchaseErrorFlags status { get }`  

```csharp
public Game.Simulation.TilePurchaseErrorFlags status { get; }
```


## Methods

- `public abstract GetFeatureAmount(Game.Areas.MapFeature feature) : System.Single`  

```csharp
public abstract System.Single GetFeatureAmount(Game.Areas.MapFeature feature);
```

- `public abstract PurchaseSelection() : System.Void`  

```csharp
public abstract System.Void PurchaseSelection();
```

- `public abstract Update() : System.Void`  

```csharp
public abstract System.Void Update();
```


