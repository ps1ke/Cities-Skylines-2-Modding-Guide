# Game.Input.ProxyModifier

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Input.ProxyModifier>`  

## Code

```csharp
public sealed struct ProxyModifier : System.IEquatable<Game.Input.ProxyModifier>
{
    public Game.Input.ActionComponent m_Component;
    public System.String m_Name;
    public System.String m_Path;
    public static readonly Game.Input.ProxyModifier+Comparer pathComparer;

    public static Game.Input.ProxyModifier+Comparer defaultComparer { get; }

    public System.Boolean Equals(Game.Input.ProxyModifier other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public virtual System.String ToString();
}
```


## Fields

- `public Game.Input.ActionComponent m_Component`  

```csharp
public Game.Input.ActionComponent m_Component;
```

- `public System.String m_Name`  

```csharp
public System.String m_Name;
```

- `public System.String m_Path`  

```csharp
public System.String m_Path;
```

- `public static readonly Game.Input.ProxyModifier+Comparer pathComparer`  

```csharp
public static readonly Game.Input.ProxyModifier+Comparer pathComparer;
```


## Properties

- `public static Game.Input.ProxyModifier+Comparer defaultComparer { get }`  

```csharp
public static Game.Input.ProxyModifier+Comparer defaultComparer { get; }
```


## Methods

- `public Equals(Game.Input.ProxyModifier other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Input.ProxyModifier other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


## Nested types

- `Game.Input.ProxyModifier+Comparer`  

