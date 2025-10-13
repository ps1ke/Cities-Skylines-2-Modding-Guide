# Colossal.OdinSerializer.TwoWaySerializationBinder

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Code

```csharp
public abstract class TwoWaySerializationBinder
{
    public static readonly Colossal.OdinSerializer.TwoWaySerializationBinder Default;

    protected TwoWaySerializationBinder();

    public abstract System.String BindToName(System.Type type, Colossal.OdinSerializer.DebugContext debugContext);
    public abstract System.Type BindToType(System.String typeName, Colossal.OdinSerializer.DebugContext debugContext);
    public abstract System.Boolean ContainsType(System.String typeName);
}
```


## Fields

- `public static readonly Colossal.OdinSerializer.TwoWaySerializationBinder Default`  

```csharp
public static readonly Colossal.OdinSerializer.TwoWaySerializationBinder Default;
```


## Constructors

- `protected TwoWaySerializationBinder()`  

```csharp
protected TwoWaySerializationBinder();
```


## Methods

- `public abstract BindToName(System.Type type, Colossal.OdinSerializer.DebugContext debugContext = null) : System.String`  

```csharp
public abstract System.String BindToName(System.Type type, Colossal.OdinSerializer.DebugContext debugContext);
```

- `public abstract BindToType(System.String typeName, Colossal.OdinSerializer.DebugContext debugContext = null) : System.Type`  

```csharp
public abstract System.Type BindToType(System.String typeName, Colossal.OdinSerializer.DebugContext debugContext);
```

- `public abstract ContainsType(System.String typeName) : System.Boolean`  

```csharp
public abstract System.Boolean ContainsType(System.String typeName);
```


