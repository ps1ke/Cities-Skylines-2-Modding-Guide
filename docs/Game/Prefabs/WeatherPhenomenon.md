# Game.Prefabs.WeatherPhenomenon

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WeatherPhenomenon : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Single m_OccurrenceProbability;
    public Colossal.Mathematics.Bounds1 m_OccurenceTemperature;
    public Colossal.Mathematics.Bounds1 m_OccurenceRain;
    public Colossal.Mathematics.Bounds1 m_Duration;
    public Colossal.Mathematics.Bounds1 m_PhenomenonRadius;
    public Colossal.Mathematics.Bounds1 m_HotspotRadius;
    public Colossal.Mathematics.Bounds1 m_LightningInterval;
    public System.Single m_HotspotInstability;
    public System.Single m_DamageSeverity;
    public System.Single m_DangerLevel;
    public System.Boolean m_Evacuate;
    public System.Boolean m_StayIndoors;

    public WeatherPhenomenon();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_OccurrenceProbability`  

```csharp
public System.Single m_OccurrenceProbability;
```

- `public Colossal.Mathematics.Bounds1 m_OccurenceTemperature`  

```csharp
public Colossal.Mathematics.Bounds1 m_OccurenceTemperature;
```

- `public Colossal.Mathematics.Bounds1 m_OccurenceRain`  

```csharp
public Colossal.Mathematics.Bounds1 m_OccurenceRain;
```

- `public Colossal.Mathematics.Bounds1 m_Duration`  

```csharp
public Colossal.Mathematics.Bounds1 m_Duration;
```

- `public Colossal.Mathematics.Bounds1 m_PhenomenonRadius`  

```csharp
public Colossal.Mathematics.Bounds1 m_PhenomenonRadius;
```

- `public Colossal.Mathematics.Bounds1 m_HotspotRadius`  

```csharp
public Colossal.Mathematics.Bounds1 m_HotspotRadius;
```

- `public Colossal.Mathematics.Bounds1 m_LightningInterval`  

```csharp
public Colossal.Mathematics.Bounds1 m_LightningInterval;
```

- `public System.Single m_HotspotInstability`  

```csharp
public System.Single m_HotspotInstability;
```

- `public System.Single m_DamageSeverity`  

```csharp
public System.Single m_DamageSeverity;
```

- `public System.Single m_DangerLevel`  

```csharp
public System.Single m_DangerLevel;
```

- `public System.Boolean m_Evacuate`  

```csharp
public System.Boolean m_Evacuate;
```

- `public System.Boolean m_StayIndoors`  

```csharp
public System.Boolean m_StayIndoors;
```


## Constructors

- `public WeatherPhenomenon()`  

```csharp
public WeatherPhenomenon();
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


