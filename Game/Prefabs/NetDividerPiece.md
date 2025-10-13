# Game.Prefabs.NetDividerPiece

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class NetDividerPiece : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Boolean m_PreserveShape;
    public System.Boolean m_BlockTraffic;
    public System.Boolean m_BlockCrosswalk;

    public NetDividerPiece();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public System.Boolean m_PreserveShape`  

```csharp
public System.Boolean m_PreserveShape;
```

- `public System.Boolean m_BlockTraffic`  

```csharp
public System.Boolean m_BlockTraffic;
```

- `public System.Boolean m_BlockCrosswalk`  

```csharp
public System.Boolean m_BlockCrosswalk;
```


## Constructors

- `public NetDividerPiece()`  

```csharp
public NetDividerPiece();
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


