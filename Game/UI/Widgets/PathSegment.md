# Game.UI.Widgets.PathSegment

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `Colossal.UI.Binding.IJsonReadable`, `System.IEquatable<Game.UI.Widgets.PathSegment>`  

## Code

```csharp
public sealed struct PathSegment : Colossal.UI.Binding.IJsonWritable, Colossal.UI.Binding.IJsonReadable, System.IEquatable<Game.UI.Widgets.PathSegment>
{
    public System.String m_Key;
    public System.Int32 m_Index;

    public static Game.UI.Widgets.PathSegment Empty { get; }

    public PathSegment(System.String key);
    public PathSegment(System.Int32 index);

    public System.Boolean Equals(Game.UI.Widgets.PathSegment other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
    public virtual System.String ToString();
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.String m_Key`  

```csharp
public System.String m_Key;
```

- `public System.Int32 m_Index`  

```csharp
public System.Int32 m_Index;
```


## Properties

- `public static Game.UI.Widgets.PathSegment Empty { get }`  

```csharp
public static Game.UI.Widgets.PathSegment Empty { get; }
```


## Constructors

- `public PathSegment(System.String key)`  

```csharp
public static implicit operator PathSegment(int index)
	{
		return new PathSegment(index);
	}
```

- `public PathSegment(System.Int32 index)`  

```csharp
public static implicit operator PathSegment(int index)
	{
		return new PathSegment(index);
	}
```


## Methods

- `public Equals(Game.UI.Widgets.PathSegment other) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj is PathSegment other)
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
		if (obj is PathSegment other)
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
		return (((m_Key != null) ? m_Key.GetHashCode() : 0) * 397) ^ m_Index;
	}
```

- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public void Read(IJsonReader reader)
	{
		switch (reader.PeekValueType())
		{
		case cohtml.Net.ValueType.String:
			reader.Read(out m_Key);
			m_Index = -1;
			break;
		case cohtml.Net.ValueType.Number:
			m_Key = null;
			reader.Read(out m_Index);
			break;
		default:
			reader.SkipValue();
			m_Key = null;
			m_Index = -1;
			break;
		}
	}
```

- `public virtual ToString() : System.String`  

```csharp
public override string ToString()
	{
		return m_Key ?? m_Index.ToString();
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		if (m_Key != null)
		{
			writer.Write(m_Key);
		}
		else if (m_Index != -1)
		{
			writer.Write(m_Index);
		}
		else
		{
			writer.WriteNull();
		}
	}
```


