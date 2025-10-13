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
public GetterWithDepsAccessor(Game.Reflection.IValueAccessor parent, System.Reflection.MethodInfo getter, System.Object[] parameters, System.Int32 depsIndex);
```


## Methods

- `public Equals(Game.Reflection.GetterWithDepsAccessor other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Reflection.GetterWithDepsAccessor other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public GetValue() : System.Object`  

```csharp
public System.Object GetValue();
```

- `public SetValue(System.Object value) : System.Void`  

```csharp
public System.Void SetValue(System.Object value);
```


