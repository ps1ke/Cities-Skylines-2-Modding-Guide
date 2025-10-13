# Game.Prefabs.LaneDirectionObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class LaneDirectionObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.LaneDirectionType m_Left;
    public Game.Prefabs.LaneDirectionType m_Forward;
    public Game.Prefabs.LaneDirectionType m_Right;

    public LaneDirectionObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.LaneDirectionType m_Left`  

```csharp
public Game.Prefabs.LaneDirectionType m_Left;
```

- `public Game.Prefabs.LaneDirectionType m_Forward`  

```csharp
public Game.Prefabs.LaneDirectionType m_Forward;
```

- `public Game.Prefabs.LaneDirectionType m_Right`  

```csharp
public Game.Prefabs.LaneDirectionType m_Right;
```


## Constructors

- `public LaneDirectionObject()`  

```csharp
public LaneDirectionObject();
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

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


