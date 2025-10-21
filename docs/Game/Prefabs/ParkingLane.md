# Game.Prefabs.ParkingLane

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ParkingLane : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Net.RoadTypes m_RoadType;
    public Unity.Mathematics.float2 m_SlotSize;
    public System.Single m_SlotAngle;
    public System.Boolean m_SpecialVehicles;

    public ParkingLane();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Net.RoadTypes m_RoadType`  

```csharp
public Game.Net.RoadTypes m_RoadType;
```

- `public Unity.Mathematics.float2 m_SlotSize`  

```csharp
public Unity.Mathematics.float2 m_SlotSize;
```

- `public System.Single m_SlotAngle`  

```csharp
public System.Single m_SlotAngle;
```

- `public System.Boolean m_SpecialVehicles`  

```csharp
public System.Boolean m_SpecialVehicles;
```


## Constructors

- `public ParkingLane()`  

```csharp
public ParkingLane();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


