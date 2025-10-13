# Game.Reflection.FieldAccessor

**Assembly:** `Game`  
**Namespace:** `Game.Reflection`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.Reflection.IValueAccessor`, `System.IEquatable<Game.Reflection.FieldAccessor>`  

## Code

```csharp
public class FieldAccessor : Game.Reflection.IValueAccessor, System.IEquatable<Game.Reflection.FieldAccessor>
{
    private readonly Game.Reflection.IValueAccessor m_Parent;
    private readonly System.Reflection.FieldInfo m_Field;

    public System.Type valueType { get; }
    public Game.Reflection.IValueAccessor parent { get; }

    public FieldAccessor(Game.Reflection.IValueAccessor parent, System.Reflection.FieldInfo field);

    public System.Boolean Equals(Game.Reflection.FieldAccessor other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public System.Object GetValue();
    public System.Void SetValue(System.Object value);
}
```


## Fields

- `private readonly Game.Reflection.IValueAccessor m_Parent`  

```csharp
private readonly Game.Reflection.IValueAccessor m_Parent;
```

- `private readonly System.Reflection.FieldInfo m_Field`  

```csharp
private readonly System.Reflection.FieldInfo m_Field;
```


## Properties

- `public System.Type valueType { get }`  

```csharp
public System.Type valueType { get; }
```

- `public Game.Reflection.IValueAccessor parent { get }`  

```csharp
public Game.Reflection.IValueAccessor parent { get; }
```


## Constructors

- `public FieldAccessor(Game.Reflection.IValueAccessor parent, System.Reflection.FieldInfo field)`  

```csharp
public FieldAccessor([NotNull] IValueAccessor parent, [NotNull] FieldInfo field)
	{
		m_Parent = parent ?? throw new ArgumentNullException("parent");
		m_Field = field ?? throw new ArgumentNullException("field");
	}
```


## Methods

- `public Equals(Game.Reflection.FieldAccessor other) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj == null)
		{
			return false;
		}
		if (this == obj)
		{
			return true;
		}
		if (obj.GetType() != GetType())
		{
			return false;
		}
		return Equals((FieldAccessor)obj);
	}
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj == null)
		{
			return false;
		}
		if (this == obj)
		{
			return true;
		}
		if (obj.GetType() != GetType())
		{
			return false;
		}
		return Equals((FieldAccessor)obj);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return (m_Parent.GetHashCode() * 397) ^ m_Field.GetHashCode();
	}
```

- `public GetValue() : System.Object`  

```csharp
public object GetValue()
	{
		object value = m_Parent.GetValue();
		return m_Field.GetValue(value);
	}
```

- `public SetValue(System.Object value) : System.Void`  

```csharp
public void SetValue(object value)
	{
		object value2 = m_Parent.GetValue();
		m_Field.SetValue(value2, value);
		if (m_Parent.valueType.IsValueType)
		{
			m_Parent.SetValue(value2);
		}
	}
```


