# Game.Areas.AreaSearchItem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Areas.AreaSearchItem>`  

## Code

```csharp
public sealed struct AreaSearchItem : System.IEquatable<Game.Areas.AreaSearchItem>
{
    public Unity.Entities.Entity m_Area;
    public System.Int32 m_Triangle;

    public AreaSearchItem(Unity.Entities.Entity area, System.Int32 triangle);

    public System.Boolean Equals(Game.Areas.AreaSearchItem other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Area`  

```csharp
public Unity.Entities.Entity m_Area;
```

- `public System.Int32 m_Triangle`  

```csharp
public System.Int32 m_Triangle;
```


## Constructors

- `public AreaSearchItem(Unity.Entities.Entity area, System.Int32 triangle)`  

```csharp
public AreaSearchItem(Unity.Entities.Entity area, System.Int32 triangle);
```


## Methods

- `public Equals(Game.Areas.AreaSearchItem other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Areas.AreaSearchItem other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


