# Game.Prefabs.AircraftPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.VehiclePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public abstract class AircraftPrefab : Game.Prefabs.VehiclePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Vehicles.SizeClass m_SizeClass;
    public System.Single m_GroundMaxSpeed;
    public System.Single m_GroundAcceleration;
    public System.Single m_GroundBraking;
    public Unity.Mathematics.float2 m_GroundTurning;

    protected AircraftPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Vehicles.SizeClass m_SizeClass`  

```csharp
public Game.Vehicles.SizeClass m_SizeClass;
```

- `public System.Single m_GroundMaxSpeed`  

```csharp
public System.Single m_GroundMaxSpeed;
```

- `public System.Single m_GroundAcceleration`  

```csharp
public System.Single m_GroundAcceleration;
```

- `public System.Single m_GroundBraking`  

```csharp
public System.Single m_GroundBraking;
```

- `public Unity.Mathematics.float2 m_GroundTurning`  

```csharp
public Unity.Mathematics.float2 m_GroundTurning;
```


## Constructors

- `protected AircraftPrefab()`  

```csharp
protected AircraftPrefab();
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

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


