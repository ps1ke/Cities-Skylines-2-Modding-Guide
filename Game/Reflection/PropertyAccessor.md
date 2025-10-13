# Game.Reflection.PropertyAccessor

**Assembly:** `Game`  
**Namespace:** `Game.Reflection`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.Reflection.IValueAccessor`, `System.IEquatable<Game.Reflection.PropertyAccessor>`  

## Code

```csharp
public class PropertyAccessor : Game.Reflection.IValueAccessor, System.IEquatable<Game.Reflection.PropertyAccessor>
{
    private readonly Game.Reflection.IValueAccessor m_Parent;
    private readonly System.Reflection.MethodInfo m_Getter;
    private readonly System.Reflection.MethodInfo m_Setter;

    public System.Type valueType { get; }

    public PropertyAccessor(Game.Reflection.IValueAccessor parent, System.Reflection.MethodInfo getter, System.Reflection.MethodInfo setter);

    public System.Boolean Equals(Game.Reflection.PropertyAccessor other);
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

- `private readonly System.Reflection.MethodInfo m_Getter`  

```csharp
private readonly System.Reflection.MethodInfo m_Getter;
```

- `private readonly System.Reflection.MethodInfo m_Setter`  

```csharp
private readonly System.Reflection.MethodInfo m_Setter;
```


## Properties

- `public System.Type valueType { get }`  

```csharp
public System.Type valueType { get; }
```


## Constructors

- `public PropertyAccessor(Game.Reflection.IValueAccessor parent, System.Reflection.MethodInfo getter, System.Reflection.MethodInfo setter)`  

```csharp
public PropertyAccessor([NotNull] IValueAccessor parent, [NotNull] MethodInfo getter, [CanBeNull] MethodInfo setter)
	{
		m_Parent = parent ?? throw new ArgumentNullException("parent");
		m_Getter = getter ?? throw new ArgumentNullException("getter");
		m_Setter = setter;
	}
```


## Methods

- `public Equals(Game.Reflection.PropertyAccessor other) : System.Boolean`  

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
		return Equals((PropertyAccessor)obj);
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
		return Equals((PropertyAccessor)obj);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return (m_Parent.GetHashCode() * 397) ^ m_Getter.GetHashCode();
	}
```

- `public GetValue() : System.Object`  

```csharp
public object GetValue()
	{
		object value = m_Parent.GetValue();
		return m_Getter.Invoke(value, null);
	}
```

- `public SetValue(System.Object value) : System.Void`  

```csharp
public void SetValue(object value)
	{
		if (m_Setter != null)
		{
			object value2 = m_Parent.GetValue();
			m_Setter.Invoke(value2, new object[1] { value });
		}
	}
```


