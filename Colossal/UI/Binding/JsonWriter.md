# Colossal.UI.Binding.JsonWriter

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWriter`  

## Code

```csharp
public class JsonWriter : Colossal.UI.Binding.IJsonWriter
{
    private System.IntPtr <binder>k__BackingField;
    private readonly System.String <debugName>k__BackingField;

    public System.IntPtr binder { get; set; }
    public System.String debugName { get; }

    protected JsonWriter();
    public JsonWriter(System.String debugName);

    public System.Void ArrayBegin(System.UInt32 size);
    public System.Void ArrayEnd();
    public System.Void BeginEvent(System.String name, System.Int32 arguments);
    public System.Void EndEvent();
    public System.Void MapBegin(System.UInt32 size);
    public System.Void MapEnd();
    public System.Void PropertyName(System.String name);
    public System.Void TypeBegin(System.String name);
    public System.Void TypeEnd();
    public System.Void Write(System.Boolean value);
    public System.Void Write(System.Int32 value);
    public System.Void Write(System.UInt32 value);
    public System.Void Write(System.Single value);
    public System.Void Write(System.Double value);
    public System.Void Write(System.String value);
    public System.Void WriteNull();
}
```


## Fields

- `private System.IntPtr <binder>k__BackingField`  

```csharp
private System.IntPtr <binder>k__BackingField;
```

- `private readonly System.String <debugName>k__BackingField`  

```csharp
private readonly System.String <debugName>k__BackingField;
```


## Properties

- `public System.IntPtr binder { get; set }`  

```csharp
public System.IntPtr binder { get; set; }
```

- `public System.String debugName { get }`  

```csharp
public System.String debugName { get; }
```


## Constructors

- `protected JsonWriter()`  

```csharp
protected JsonWriter();
```

- `public JsonWriter(System.String debugName)`  

```csharp
public JsonWriter(System.String debugName);
```


## Methods

- `public ArrayBegin(System.UInt32 size) : System.Void`  

```csharp
public System.Void ArrayBegin(System.UInt32 size);
```

- `public ArrayEnd() : System.Void`  

```csharp
public System.Void ArrayEnd();
```

- `public BeginEvent(System.String name, System.Int32 arguments) : System.Void`  

```csharp
public System.Void BeginEvent(System.String name, System.Int32 arguments);
```

- `public EndEvent() : System.Void`  

```csharp
public System.Void EndEvent();
```

- `public MapBegin(System.UInt32 size) : System.Void`  

```csharp
public System.Void MapBegin(System.UInt32 size);
```

- `public MapEnd() : System.Void`  

```csharp
public System.Void MapEnd();
```

- `public PropertyName(System.String name) : System.Void`  

```csharp
public System.Void PropertyName(System.String name);
```

- `public TypeBegin(System.String name) : System.Void`  

```csharp
public System.Void TypeBegin(System.String name);
```

- `public TypeEnd() : System.Void`  

```csharp
public System.Void TypeEnd();
```

- `public Write(System.Boolean value) : System.Void`  

```csharp
public System.Void Write(System.Boolean value);
```

- `public Write(System.Int32 value) : System.Void`  

```csharp
public System.Void Write(System.Int32 value);
```

- `public Write(System.UInt32 value) : System.Void`  

```csharp
public System.Void Write(System.UInt32 value);
```

- `public Write(System.Single value) : System.Void`  

```csharp
public System.Void Write(System.Single value);
```

- `public Write(System.Double value) : System.Void`  

```csharp
public System.Void Write(System.Double value);
```

- `public Write(System.String value) : System.Void`  

```csharp
public System.Void Write(System.String value);
```

- `public WriteNull() : System.Void`  

```csharp
public System.Void WriteNull();
```


