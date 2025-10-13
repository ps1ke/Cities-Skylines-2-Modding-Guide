# Game.Simulation.ITradeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ITradeSystem
{
    public abstract System.Single GetTradePrice(Game.Economy.Resource resource, Game.Prefabs.OutsideConnectionTransferType type, System.Boolean import, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects);
}
```


## Methods

- `public abstract GetTradePrice(Game.Economy.Resource resource, Game.Prefabs.OutsideConnectionTransferType type, System.Boolean import, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects) : System.Single`  

```csharp
public abstract System.Single GetTradePrice(Game.Economy.Resource resource, Game.Prefabs.OutsideConnectionTransferType type, System.Boolean import, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects);
```


