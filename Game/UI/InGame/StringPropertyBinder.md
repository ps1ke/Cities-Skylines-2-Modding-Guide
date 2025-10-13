# Game.UI.InGame.PrefabUISystem+StringPropertyBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Code

```csharp
public abstract class StringPropertyBinder : Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder
{
    public readonly System.String m_LabelId;
    public readonly System.String m_Icon;
    public readonly System.String m_ValueIcon;

    protected StringPropertyBinder(System.String labelId, System.String icon, System.String valueIcon);

    public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public abstract System.String GetValueId(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public abstract System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public readonly System.String m_LabelId`  

```csharp
public readonly System.String m_LabelId;
```

- `public readonly System.String m_Icon`  

```csharp
public readonly System.String m_Icon;
```

- `public readonly System.String m_ValueIcon`  

```csharp
public readonly System.String m_ValueIcon;
```


## Constructors

- `protected StringPropertyBinder(System.String labelId, System.String icon = null, System.String valueIcon = null)`  

```csharp
protected StringPropertyBinder(System.String labelId, System.String icon, System.String valueIcon);
```


## Methods

- `public Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public abstract GetValueId(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.String`  

```csharp
public abstract System.String GetValueId(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public abstract Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public abstract System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


