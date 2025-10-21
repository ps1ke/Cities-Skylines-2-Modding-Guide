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
public PropertyAccessor(Game.Reflection.IValueAccessor parent, System.Reflection.MethodInfo getter, System.Reflection.MethodInfo setter);
```


## Methods

- `public Equals(Game.Reflection.PropertyAccessor other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Reflection.PropertyAccessor other);
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


