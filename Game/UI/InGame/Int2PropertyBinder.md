# Game.UI.InGame.PrefabUISystem+Int2PropertyBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Code

```csharp
public abstract class Int2PropertyBinder : Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder
{
    public readonly System.String m_LabelId;
    public readonly System.String m_Unit;
    public readonly System.Boolean m_Signed;
    public readonly System.String m_Icon;
    public readonly System.String m_ValueIcon;

    protected Int2PropertyBinder(System.String labelId, System.String unit, System.Boolean signed, System.String icon, System.String valueIcon);

    public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public abstract Unity.Mathematics.int2 GetValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public abstract System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public readonly System.String m_LabelId`  

```csharp
public readonly System.String m_LabelId;
```

- `public readonly System.String m_Unit`  

```csharp
public readonly System.String m_Unit;
```

- `public readonly System.Boolean m_Signed`  

```csharp
public readonly System.Boolean m_Signed;
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

- `protected Int2PropertyBinder(System.String labelId, System.String unit, System.Boolean signed = False, System.String icon = null, System.String valueIcon = null)`  

```csharp
protected Int2PropertyBinder(System.String labelId, System.String unit, System.Boolean signed, System.String icon, System.String valueIcon);
```


## Methods

- `public Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public abstract GetValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Unity.Mathematics.int2`  

```csharp
public abstract Unity.Mathematics.int2 GetValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public abstract Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public abstract System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


