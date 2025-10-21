# Game.Prefabs.ToolError

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ToolError : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Tools.ErrorType m_Error;
    public System.Boolean m_TemporaryOnly;
    public System.Boolean m_DisableInGame;
    public System.Boolean m_DisableInEditor;

    public ToolError();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Tools.ErrorType m_Error`  

```csharp
public Game.Tools.ErrorType m_Error;
```

- `public System.Boolean m_TemporaryOnly`  

```csharp
public System.Boolean m_TemporaryOnly;
```

- `public System.Boolean m_DisableInGame`  

```csharp
public System.Boolean m_DisableInGame;
```

- `public System.Boolean m_DisableInEditor`  

```csharp
public System.Boolean m_DisableInEditor;
```


## Constructors

- `public ToolError()`  

```csharp
public ToolError();
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


