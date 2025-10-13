# Game.Prefabs.PrefabID

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Prefabs.PrefabID>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PrefabID : System.IEquatable<Game.Prefabs.PrefabID>, Colossal.Serialization.Entities.ISerializable
{
    private System.String m_Type;
    private System.String m_Name;

    public PrefabID(Game.Prefabs.PrefabBase prefab);
    public PrefabID(System.String type, System.String name);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Prefabs.PrefabID other);
    public virtual System.Int32 GetHashCode();
    public System.String GetName();
    public System.Void Serialize<TWriter>(TWriter writer);
    public virtual System.String ToString();
}
```


## Fields

- `private System.String m_Type`  

```csharp
private System.String m_Type;
```

- `private System.String m_Name`  

```csharp
private System.String m_Name;
```


## Constructors

- `public PrefabID(Game.Prefabs.PrefabBase prefab)`  

```csharp
public PrefabID(string type, string name)
	{
		m_Type = type;
		m_Name = name;
	}
```

- `public PrefabID(System.String type, System.String name)`  

```csharp
public PrefabID(string type, string name)
	{
		m_Type = type;
		m_Name = name;
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Prefabs.PrefabID other) : System.Boolean`  

```csharp
public bool Equals(PrefabID other)
	{
		if (m_Type.Equals(other.m_Type))
		{
			return m_Name.Equals(other.m_Name);
		}
		return false;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_Name.GetHashCode();
	}
```

- `public GetName() : System.String`  

```csharp
public string GetName()
	{
		return m_Name;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public virtual ToString() : System.String`  

```csharp
public override string ToString()
	{
		return $"{m_Type}:{m_Name}";
	}
```


