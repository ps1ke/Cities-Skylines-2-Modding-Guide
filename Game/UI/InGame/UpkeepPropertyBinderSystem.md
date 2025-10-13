# Game.UI.InGame.PrefabUISystem+UpkeepPropertyBinderSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpkeepPropertyBinderSystem : Game.GameSystemBase, Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Entities.EntityQuery m_BudgetDataQuery;

    public UpkeepPropertyBinderSystem();

    public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    private Unity.Mathematics.int2 GetValue(Unity.Entities.Entity entity);
    public System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Entities.EntityQuery m_BudgetDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_BudgetDataQuery;
```


## Constructors

- `public UpkeepPropertyBinderSystem()`  

```csharp
public UpkeepPropertyBinderSystem();
```


## Methods

- `public Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `private GetValue(Unity.Entities.Entity entity) : Unity.Mathematics.int2`  

```csharp
private Unity.Mathematics.int2 GetValue(Unity.Entities.Entity entity);
```

- `public Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


