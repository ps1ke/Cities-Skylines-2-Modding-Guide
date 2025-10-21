# Game.Prefabs.CarLane

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CarLane : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.NetLanePrefab m_NotTrackLane;
    public Game.Prefabs.NetLanePrefab m_NotBusLane;
    public Game.Net.RoadTypes m_RoadType;
    public Game.Vehicles.SizeClass m_MaxSize;
    public System.Single m_Width;
    public System.Boolean m_StartingLane;
    public System.Boolean m_EndingLane;
    public System.Boolean m_Twoway;
    public System.Boolean m_BusLane;

    public CarLane();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.NetLanePrefab m_NotTrackLane`  

```csharp
public Game.Prefabs.NetLanePrefab m_NotTrackLane;
```

- `public Game.Prefabs.NetLanePrefab m_NotBusLane`  

```csharp
public Game.Prefabs.NetLanePrefab m_NotBusLane;
```

- `public Game.Net.RoadTypes m_RoadType`  

```csharp
public Game.Net.RoadTypes m_RoadType;
```

- `public Game.Vehicles.SizeClass m_MaxSize`  

```csharp
public Game.Vehicles.SizeClass m_MaxSize;
```

- `public System.Single m_Width`  

```csharp
public System.Single m_Width;
```

- `public System.Boolean m_StartingLane`  

```csharp
public System.Boolean m_StartingLane;
```

- `public System.Boolean m_EndingLane`  

```csharp
public System.Boolean m_EndingLane;
```

- `public System.Boolean m_Twoway`  

```csharp
public System.Boolean m_Twoway;
```

- `public System.Boolean m_BusLane`  

```csharp
public System.Boolean m_BusLane;
```


## Constructors

- `public CarLane()`  

```csharp
public CarLane();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


