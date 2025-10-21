# Game.Prefabs.OutsideConnection

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class OutsideConnection : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Economy.ResourceInEditor[] m_TradedResources;
    public System.Boolean m_Commuting;
    public Game.Prefabs.OutsideConnectionTransferType m_TransferType;
    public System.Single m_Remoteness;

    public OutsideConnection();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Economy.ResourceInEditor[] m_TradedResources`  

```csharp
public Game.Economy.ResourceInEditor[] m_TradedResources;
```

- `public System.Boolean m_Commuting`  

```csharp
public System.Boolean m_Commuting;
```

- `public Game.Prefabs.OutsideConnectionTransferType m_TransferType`  

```csharp
public Game.Prefabs.OutsideConnectionTransferType m_TransferType;
```

- `public System.Single m_Remoteness`  

```csharp
public System.Single m_Remoteness;
```


## Constructors

- `public OutsideConnection()`  

```csharp
public OutsideConnection();
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


