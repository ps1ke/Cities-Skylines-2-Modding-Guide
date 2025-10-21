# Game.UI.InGame.PrefabUISystem+ElectricityPropertyBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Code

```csharp
public abstract class ElectricityPropertyBinder : Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder
{
    public readonly System.String m_LabelId;

    protected ElectricityPropertyBinder(System.String labelId);

    public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public abstract System.Void GetValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& minCapacity, System.Int32& maxCapacity, Game.Net.Layer& voltageLayers);
    public abstract System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public readonly System.String m_LabelId`  

```csharp
public readonly System.String m_LabelId;
```


## Constructors

- `protected ElectricityPropertyBinder(System.String labelId)`  

```csharp
protected ElectricityPropertyBinder(System.String labelId);
```


## Methods

- `public Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public abstract GetValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& minCapacity, System.Int32& maxCapacity, Game.Net.Layer& voltageLayers) : System.Void`  

```csharp
public abstract System.Void GetValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& minCapacity, System.Int32& maxCapacity, Game.Net.Layer& voltageLayers);
```

- `public abstract Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public abstract System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


