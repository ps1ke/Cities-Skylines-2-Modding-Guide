# Game.Prefabs.TrackLane

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TrackLane : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.NetLanePrefab m_FallbackLane;
    public Game.Prefabs.ObjectPrefab m_EndObject;
    public Game.Net.TrackTypes m_TrackType;
    public System.Single m_Width;
    public System.Single m_MaxCurviness;
    public System.Boolean m_Twoway;

    public TrackLane();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.NetLanePrefab m_FallbackLane`  

```csharp
public Game.Prefabs.NetLanePrefab m_FallbackLane;
```

- `public Game.Prefabs.ObjectPrefab m_EndObject`  

```csharp
public Game.Prefabs.ObjectPrefab m_EndObject;
```

- `public Game.Net.TrackTypes m_TrackType`  

```csharp
public Game.Net.TrackTypes m_TrackType;
```

- `public System.Single m_Width`  

```csharp
public System.Single m_Width;
```

- `public System.Single m_MaxCurviness`  

```csharp
public System.Single m_MaxCurviness;
```

- `public System.Boolean m_Twoway`  

```csharp
public System.Boolean m_Twoway;
```


## Constructors

- `public TrackLane()`  

```csharp
public TrackLane();
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


