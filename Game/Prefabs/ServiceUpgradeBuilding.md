# Game.Prefabs.ServiceUpgradeBuilding

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct ServiceUpgradeBuilding : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Building;

    public ServiceUpgradeBuilding(Unity.Entities.Entity building);

}
```


## Fields

- `public Unity.Entities.Entity m_Building`  

```csharp
public Unity.Entities.Entity m_Building;
```


## Constructors

- `public ServiceUpgradeBuilding(Unity.Entities.Entity building)`  

```csharp
public ServiceUpgradeBuilding(Entity building)
	{
		m_Building = building;
	}
```


