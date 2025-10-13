# Colossal.OdinSerializer.NodeInfo

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct NodeInfo
{
    public readonly System.String Name;
    public readonly System.Int32 Id;
    public readonly System.Type Type;
    public readonly System.Boolean IsArray;
    public readonly System.Boolean IsEmpty;
    public static readonly Colossal.OdinSerializer.NodeInfo Empty;

    public NodeInfo(System.String name, System.Int32 id, System.Type type, System.Boolean isArray);
    private NodeInfo(System.Boolean parameter);

    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public readonly System.String Name`  

```csharp
public readonly System.String Name;
```

- `public readonly System.Int32 Id`  

```csharp
public readonly System.Int32 Id;
```

- `public readonly System.Type Type`  

```csharp
public readonly System.Type Type;
```

- `public readonly System.Boolean IsArray`  

```csharp
public readonly System.Boolean IsArray;
```

- `public readonly System.Boolean IsEmpty`  

```csharp
public readonly System.Boolean IsEmpty;
```

- `public static readonly Colossal.OdinSerializer.NodeInfo Empty`  

```csharp
public static readonly Colossal.OdinSerializer.NodeInfo Empty;
```


## Constructors

- `public NodeInfo(System.String name, System.Int32 id, System.Type type, System.Boolean isArray)`  

```csharp
public NodeInfo(System.String name, System.Int32 id, System.Type type, System.Boolean isArray);
```

- `private NodeInfo(System.Boolean parameter)`  

```csharp
private NodeInfo(System.Boolean parameter);
```


## Methods

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


