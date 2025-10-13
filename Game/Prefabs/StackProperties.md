# Game.Prefabs.StackProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class StackProperties : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.StackDirection m_Direction;
    public Game.Prefabs.StackOrder m_Order;
    public System.Single m_StartOverlap;
    public System.Single m_EndOverlap;
    public System.Boolean m_ForbidScaling;

    public StackProperties();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.StackDirection m_Direction`  

```csharp
public Game.Prefabs.StackDirection m_Direction;
```

- `public Game.Prefabs.StackOrder m_Order`  

```csharp
public Game.Prefabs.StackOrder m_Order;
```

- `public System.Single m_StartOverlap`  

```csharp
public System.Single m_StartOverlap;
```

- `public System.Single m_EndOverlap`  

```csharp
public System.Single m_EndOverlap;
```

- `public System.Boolean m_ForbidScaling`  

```csharp
public System.Boolean m_ForbidScaling;
```


## Constructors

- `public StackProperties()`  

```csharp
public StackProperties();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
	}
```


