# Game.Prefabs.TrainPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.VehiclePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ExcludeGeneratedModTag`  

## Code

```csharp
public abstract class TrainPrefab : Game.Prefabs.VehiclePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Net.TrackTypes m_TrackType;
    public Game.Vehicles.EnergyTypes m_EnergyType;
    public System.Single m_MaxSpeed;
    public System.Single m_Acceleration;
    public System.Single m_Braking;
    public Unity.Mathematics.float2 m_Turning;
    public Unity.Mathematics.float2 m_BogieOffset;
    public Unity.Mathematics.float2 m_AttachOffset;

    public System.Collections.Generic.IEnumerable<System.String> modTags { get; }

    protected TrainPrefab();

    private System.Collections.Generic.IEnumerable<System.String> <>n__0();
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    protected virtual System.Void RefreshArchetype(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Net.TrackTypes m_TrackType`  

```csharp
public Game.Net.TrackTypes m_TrackType;
```

- `public Game.Vehicles.EnergyTypes m_EnergyType`  

```csharp
public Game.Vehicles.EnergyTypes m_EnergyType;
```

- `public System.Single m_MaxSpeed`  

```csharp
public System.Single m_MaxSpeed;
```

- `public System.Single m_Acceleration`  

```csharp
public System.Single m_Acceleration;
```

- `public System.Single m_Braking`  

```csharp
public System.Single m_Braking;
```

- `public Unity.Mathematics.float2 m_Turning`  

```csharp
public Unity.Mathematics.float2 m_Turning;
```

- `public Unity.Mathematics.float2 m_BogieOffset`  

```csharp
public Unity.Mathematics.float2 m_BogieOffset;
```

- `public Unity.Mathematics.float2 m_AttachOffset`  

```csharp
public Unity.Mathematics.float2 m_AttachOffset;
```


## Properties

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modTags { get; }
```


## Constructors

- `protected TrainPrefab()`  

```csharp
protected TrainPrefab();
```


## Methods

- `private <>n__0() : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
private System.Collections.Generic.IEnumerable<System.String> <>n__0();
```

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

- `protected virtual RefreshArchetype(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected virtual System.Void RefreshArchetype(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


## Nested types

- `Game.Prefabs.TrainPrefab+<get_modTags>d__13`  

