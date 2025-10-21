# Game.Prefabs.NetUpgrade

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class NetUpgrade : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.NetPieceRequirements[] m_SetState;
    public Game.Prefabs.NetPieceRequirements[] m_UnsetState;
    public System.Boolean m_Standalone;
    public System.Boolean m_Underground;

    public NetUpgrade();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.NetPieceRequirements[] m_SetState`  

```csharp
public Game.Prefabs.NetPieceRequirements[] m_SetState;
```

- `public Game.Prefabs.NetPieceRequirements[] m_UnsetState`  

```csharp
public Game.Prefabs.NetPieceRequirements[] m_UnsetState;
```

- `public System.Boolean m_Standalone`  

```csharp
public System.Boolean m_Standalone;
```

- `public System.Boolean m_Underground`  

```csharp
public System.Boolean m_Underground;
```


## Constructors

- `public NetUpgrade()`  

```csharp
public NetUpgrade();
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


