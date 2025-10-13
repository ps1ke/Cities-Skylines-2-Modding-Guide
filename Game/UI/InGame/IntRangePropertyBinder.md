# Game.UI.InGame.PrefabUISystem+IntRangePropertyBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Code

```csharp
public abstract class IntRangePropertyBinder : Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder
{
    public readonly System.String m_LabelId;
    public readonly System.String m_Unit;
    public readonly System.Boolean m_Signed;
    public readonly System.String m_Icon;
    public readonly System.String m_ValueIcon;

    protected IntRangePropertyBinder(System.String labelId, System.String unit, System.Boolean signed, System.String icon, System.String valueIcon);

    public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public abstract System.Int32 GetMaxValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public abstract System.Int32 GetMinValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
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

- `protected IntRangePropertyBinder(System.String labelId, System.String unit, System.Boolean signed = False, System.String icon = null, System.String valueIcon = null)`  

```csharp
protected IntRangePropertyBinder(System.String labelId, System.String unit, System.Boolean signed, System.String icon, System.String valueIcon);
```


## Methods

- `public Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public abstract GetMaxValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Int32`  

```csharp
public abstract System.Int32 GetMaxValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public abstract GetMinValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Int32`  

```csharp
public abstract System.Int32 GetMinValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public abstract Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public abstract System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


