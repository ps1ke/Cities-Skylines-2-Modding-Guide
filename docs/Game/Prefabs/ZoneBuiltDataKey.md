# Game.Prefabs.ZoneBuiltDataKey

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Prefabs.ZoneBuiltDataKey>`  

## Code

```csharp
public sealed struct ZoneBuiltDataKey : System.IEquatable<Game.Prefabs.ZoneBuiltDataKey>
{
    public Unity.Entities.Entity m_Zone;
    public System.Int32 m_Level;

    public System.Boolean Equals(Game.Prefabs.ZoneBuiltDataKey other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Zone`  

```csharp
public Unity.Entities.Entity m_Zone;
```

- `public System.Int32 m_Level`  

```csharp
public System.Int32 m_Level;
```


## Methods

- `public Equals(Game.Prefabs.ZoneBuiltDataKey other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Prefabs.ZoneBuiltDataKey other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


