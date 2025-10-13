# Colossal.UI.Binding.IJsonWriter

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IJsonWriter
{
    public System.String debugName { get; }

    public abstract System.Void ArrayBegin(System.UInt32 size);
    public abstract System.Void ArrayEnd();
    public abstract System.Void MapBegin(System.UInt32 size);
    public abstract System.Void MapEnd();
    public abstract System.Void PropertyName(System.String name);
    public abstract System.Void TypeBegin(System.String name);
    public abstract System.Void TypeEnd();
    public abstract System.Void Write(System.Boolean value);
    public abstract System.Void Write(System.Int32 value);
    public abstract System.Void Write(System.UInt32 value);
    public abstract System.Void Write(System.Single value);
    public abstract System.Void Write(System.Double value);
    public abstract System.Void Write(System.String value);
    public abstract System.Void WriteNull();
}
```


## Properties

- `public System.String debugName { get }`  

```csharp
public System.String debugName { get; }
```


## Methods

- `public abstract ArrayBegin(System.UInt32 size) : System.Void`  

```csharp
public abstract System.Void ArrayBegin(System.UInt32 size);
```

- `public abstract ArrayEnd() : System.Void`  

```csharp
public abstract System.Void ArrayEnd();
```

- `public abstract MapBegin(System.UInt32 size) : System.Void`  

```csharp
public abstract System.Void MapBegin(System.UInt32 size);
```

- `public abstract MapEnd() : System.Void`  

```csharp
public abstract System.Void MapEnd();
```

- `public abstract PropertyName(System.String name) : System.Void`  

```csharp
public abstract System.Void PropertyName(System.String name);
```

- `public abstract TypeBegin(System.String name) : System.Void`  

```csharp
public abstract System.Void TypeBegin(System.String name);
```

- `public abstract TypeEnd() : System.Void`  

```csharp
public abstract System.Void TypeEnd();
```

- `public abstract Write(System.Boolean value) : System.Void`  

```csharp
public abstract System.Void Write(System.Boolean value);
```

- `public abstract Write(System.Int32 value) : System.Void`  

```csharp
public abstract System.Void Write(System.Int32 value);
```

- `public abstract Write(System.UInt32 value) : System.Void`  

```csharp
public abstract System.Void Write(System.UInt32 value);
```

- `public abstract Write(System.Single value) : System.Void`  

```csharp
public abstract System.Void Write(System.Single value);
```

- `public abstract Write(System.Double value) : System.Void`  

```csharp
public abstract System.Void Write(System.Double value);
```

- `public abstract Write(System.String value) : System.Void`  

```csharp
public abstract System.Void Write(System.String value);
```

- `public abstract WriteNull() : System.Void`  

```csharp
public abstract System.Void WriteNull();
```


