# Game.Reflection.GetterWithDepsAccessor

**Assembly:** `Game`  
**Namespace:** `Game.Reflection`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.Reflection.IValueAccessor`, `System.IEquatable<Game.Reflection.GetterWithDepsAccessor>`  

## Code

```csharp
public class GetterWithDepsAccessor : Game.Reflection.IValueAccessor, System.IEquatable<Game.Reflection.GetterWithDepsAccessor>
{
    private readonly Game.Reflection.IValueAccessor m_Parent;
    private readonly System.Reflection.MethodInfo m_Getter;
    private readonly System.Object[] m_Parameters;
    private readonly System.Int32 m_DepsIndex;

    public System.Type valueType { get; }

    public GetterWithDepsAccessor(Game.Reflection.IValueAccessor parent, System.Reflection.MethodInfo getter, System.Object[] parameters, System.Int32 depsIndex);

    public System.Boolean Equals(Game.Reflection.GetterWithDepsAccessor other);
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

- `private readonly System.Object[] m_Parameters`  

```csharp
private readonly System.Object[] m_Parameters;
```

- `private readonly System.Int32 m_DepsIndex`  

```csharp
private readonly System.Int32 m_DepsIndex;
```


## Properties

- `public System.Type valueType { get }`  

```csharp
public System.Type valueType { get; }
```


## Constructors

- `public GetterWithDepsAccessor(Game.Reflection.IValueAccessor parent, System.Reflection.MethodInfo getter, System.Object[] parameters = null, System.Int32 depsIndex = -1)`  

```csharp
public GetterWithDepsAccessor([NotNull] IValueAccessor parent, [NotNull] MethodInfo getter, [CanBeNull] object[] parameters = null, int depsIndex = -1)
	{
		m_Parent = parent ?? throw new ArgumentNullException("parent");
		m_Getter = getter ?? throw new ArgumentNullException("getter");
		m_Parameters = parameters;
		m_DepsIndex = depsIndex;
	}
```


## Methods

- `public Equals(Game.Reflection.GetterWithDepsAccessor other) : System.Boolean`  

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
		return Equals((GetterWithDepsAccessor)obj);
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
		return Equals((GetterWithDepsAccessor)obj);
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
		object result = m_Getter.Invoke(value, m_Parameters);
		if (m_DepsIndex != -1 && m_Parameters != null)
		{
			((JobHandle)m_Parameters[m_DepsIndex]).Complete();
		}
		return result;
	}
```

- `public SetValue(System.Object value) : System.Void`  

```csharp
public void SetValue(object value)
	{
		throw new InvalidOperationException("GetterWithDepsAccessor is readonly");
	}
```


