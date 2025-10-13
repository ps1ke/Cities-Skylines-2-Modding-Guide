# Game.Prefabs.UnlockRequirement

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Prefabs.UnlockRequirement>`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct UnlockRequirement : Unity.Entities.IBufferElementData, System.IEquatable<Game.Prefabs.UnlockRequirement>
{
    public Unity.Entities.Entity m_Prefab;
    public Game.Prefabs.UnlockFlags m_Flags;

    public UnlockRequirement(Unity.Entities.Entity prefab, Game.Prefabs.UnlockFlags flags);

    public System.Boolean Equals(Game.Prefabs.UnlockRequirement other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public Game.Prefabs.UnlockFlags m_Flags`  

```csharp
public Game.Prefabs.UnlockFlags m_Flags;
```


## Constructors

- `public UnlockRequirement(Unity.Entities.Entity prefab, Game.Prefabs.UnlockFlags flags)`  

```csharp
public UnlockRequirement(Entity prefab, UnlockFlags flags)
	{
		m_Prefab = prefab;
		m_Flags = flags;
	}
```


## Methods

- `public Equals(Game.Prefabs.UnlockRequirement other) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj is UnlockRequirement other)
		{
			return Equals(other);
		}
		return false;
	}
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj is UnlockRequirement other)
		{
			return Equals(other);
		}
		return false;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return (m_Prefab.GetHashCode() * 397) ^ (int)m_Flags;
	}
```


