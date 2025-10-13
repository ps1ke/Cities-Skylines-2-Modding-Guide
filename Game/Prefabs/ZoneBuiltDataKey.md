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
public bool Equals(ZoneBuiltDataKey other)
	{
		if (m_Zone.Equals(other.m_Zone))
		{
			return m_Level.Equals(other.m_Level);
		}
		return false;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return (17 * 31 + m_Zone.GetHashCode()) * 31 + m_Level.GetHashCode();
	}
```


