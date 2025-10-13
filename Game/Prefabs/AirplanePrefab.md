# Game.Prefabs.AirplanePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.AircraftPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AirplanePrefab : Game.Prefabs.AircraftPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Unity.Mathematics.float2 m_FlyingSpeed;
    public System.Single m_FlyingAcceleration;
    public System.Single m_FlyingBraking;
    public System.Single m_FlyingTurning;
    public System.Single m_FlyingAngularAcceleration;
    public System.Single m_ClimbAngle;
    public System.Single m_SlowPitchAngle;
    public System.Single m_TurningRollFactor;

    public AirplanePrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Unity.Mathematics.float2 m_FlyingSpeed`  

```csharp
public Unity.Mathematics.float2 m_FlyingSpeed;
```

- `public System.Single m_FlyingAcceleration`  

```csharp
public System.Single m_FlyingAcceleration;
```

- `public System.Single m_FlyingBraking`  

```csharp
public System.Single m_FlyingBraking;
```

- `public System.Single m_FlyingTurning`  

```csharp
public System.Single m_FlyingTurning;
```

- `public System.Single m_FlyingAngularAcceleration`  

```csharp
public System.Single m_FlyingAngularAcceleration;
```

- `public System.Single m_ClimbAngle`  

```csharp
public System.Single m_ClimbAngle;
```

- `public System.Single m_SlowPitchAngle`  

```csharp
public System.Single m_SlowPitchAngle;
```

- `public System.Single m_TurningRollFactor`  

```csharp
public System.Single m_TurningRollFactor;
```


## Constructors

- `public AirplanePrefab()`  

```csharp
public AirplanePrefab();
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


