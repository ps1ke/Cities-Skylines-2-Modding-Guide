# Game.Prefabs.UndergroundMesh

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UndergroundMesh : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Boolean m_IsTunnel;
    public System.Boolean m_IsPipeline;
    public System.Boolean m_IsSubPipeline;

    public UndergroundMesh();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public System.Boolean m_IsTunnel`  

```csharp
public System.Boolean m_IsTunnel;
```

- `public System.Boolean m_IsPipeline`  

```csharp
public System.Boolean m_IsPipeline;
```

- `public System.Boolean m_IsSubPipeline`  

```csharp
public System.Boolean m_IsSubPipeline;
```


## Constructors

- `public UndergroundMesh()`  

```csharp
public UndergroundMesh();
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


