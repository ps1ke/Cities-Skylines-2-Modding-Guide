# Game.Prefabs.DeliveryTruckSelectItem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Prefabs.DeliveryTruckSelectItem>`  

## Code

```csharp
public sealed struct DeliveryTruckSelectItem : System.IComparable<Game.Prefabs.DeliveryTruckSelectItem>
{
    public System.Int32 m_Capacity;
    public System.Int32 m_Cost;
    public Game.Economy.Resource m_Resources;
    public Unity.Entities.Entity m_Prefab1;
    public Unity.Entities.Entity m_Prefab2;
    public Unity.Entities.Entity m_Prefab3;
    public Unity.Entities.Entity m_Prefab4;

    public System.Int32 CompareTo(Game.Prefabs.DeliveryTruckSelectItem other);
}
```


## Fields

- `public System.Int32 m_Capacity`  

```csharp
public System.Int32 m_Capacity;
```

- `public System.Int32 m_Cost`  

```csharp
public System.Int32 m_Cost;
```

- `public Game.Economy.Resource m_Resources`  

```csharp
public Game.Economy.Resource m_Resources;
```

- `public Unity.Entities.Entity m_Prefab1`  

```csharp
public Unity.Entities.Entity m_Prefab1;
```

- `public Unity.Entities.Entity m_Prefab2`  

```csharp
public Unity.Entities.Entity m_Prefab2;
```

- `public Unity.Entities.Entity m_Prefab3`  

```csharp
public Unity.Entities.Entity m_Prefab3;
```

- `public Unity.Entities.Entity m_Prefab4`  

```csharp
public Unity.Entities.Entity m_Prefab4;
```


## Methods

- `public CompareTo(Game.Prefabs.DeliveryTruckSelectItem other) : System.Int32`  

```csharp
public int CompareTo(DeliveryTruckSelectItem other)
	{
		return m_Capacity - other.m_Capacity;
	}
```


