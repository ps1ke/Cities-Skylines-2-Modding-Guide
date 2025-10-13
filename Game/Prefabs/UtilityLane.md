# Game.Prefabs.UtilityLane

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UtilityLane : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Net.UtilityTypes m_UtilityType;
    public Game.Prefabs.NetLanePrefab m_LocalConnectionLane;
    public Game.Prefabs.NetLanePrefab m_LocalConnectionLane2;
    public Game.Prefabs.ObjectPrefab m_NodeObject;
    public System.Single m_Width;
    public System.Single m_VisualCapacity;
    public System.Single m_Hanging;
    public System.Boolean m_Underground;

    public UtilityLane();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Net.UtilityTypes m_UtilityType`  

```csharp
public Game.Net.UtilityTypes m_UtilityType;
```

- `public Game.Prefabs.NetLanePrefab m_LocalConnectionLane`  

```csharp
public Game.Prefabs.NetLanePrefab m_LocalConnectionLane;
```

- `public Game.Prefabs.NetLanePrefab m_LocalConnectionLane2`  

```csharp
public Game.Prefabs.NetLanePrefab m_LocalConnectionLane2;
```

- `public Game.Prefabs.ObjectPrefab m_NodeObject`  

```csharp
public Game.Prefabs.ObjectPrefab m_NodeObject;
```

- `public System.Single m_Width`  

```csharp
public System.Single m_Width;
```

- `public System.Single m_VisualCapacity`  

```csharp
public System.Single m_VisualCapacity;
```

- `public System.Single m_Hanging`  

```csharp
public System.Single m_Hanging;
```

- `public System.Boolean m_Underground`  

```csharp
public System.Boolean m_Underground;
```


## Constructors

- `public UtilityLane()`  

```csharp
public UtilityLane();
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


