# Colossal.UI.Binding.JsonReader

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonReader`  

## Code

```csharp
public class JsonReader : Colossal.UI.Binding.IJsonReader
{
    private System.IntPtr <binder>k__BackingField;
    private readonly System.String <debugName>k__BackingField;

    public System.IntPtr binder { get; set; }
    public System.String debugName { get; }

    protected JsonReader();
    public JsonReader(System.String debugName);

    public System.Int32 GetArgumentsCount();
    public cohtml.Net.ValueType PeekValueType();
    public System.Void Read(System.Boolean& value);
    public System.Void Read(System.UInt32& value);
    public System.Void Read(System.Int32& value);
    public System.Void Read(System.Single& value);
    public System.Void Read(System.Double& value);
    public System.Void Read(System.String& value);
    public System.UInt64 ReadArrayBegin();
    public System.Void ReadArrayElement(System.UInt64 index);
    public System.Void ReadArrayEnd();
    public System.UInt64 ReadMapBegin();
    public System.Void ReadMapEnd();
    public System.Void ReadMapKeyValue();
    public System.Boolean ReadProperty(System.String name);
    public System.Void SkipValue();
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

- `protected JsonReader()`  

```csharp
protected JsonReader();
```

- `public JsonReader(System.String debugName)`  

```csharp
public JsonReader(System.String debugName);
```


## Methods

- `public GetArgumentsCount() : System.Int32`  

```csharp
public System.Int32 GetArgumentsCount();
```

- `public PeekValueType() : cohtml.Net.ValueType`  

```csharp
public cohtml.Net.ValueType PeekValueType();
```

- `public Read(System.Boolean& value) : System.Void`  

```csharp
public System.Void Read(System.Boolean& value);
```

- `public Read(System.UInt32& value) : System.Void`  

```csharp
public System.Void Read(System.UInt32& value);
```

- `public Read(System.Int32& value) : System.Void`  

```csharp
public System.Void Read(System.Int32& value);
```

- `public Read(System.Single& value) : System.Void`  

```csharp
public System.Void Read(System.Single& value);
```

- `public Read(System.Double& value) : System.Void`  

```csharp
public System.Void Read(System.Double& value);
```

- `public Read(System.String& value) : System.Void`  

```csharp
public System.Void Read(System.String& value);
```

- `public ReadArrayBegin() : System.UInt64`  

```csharp
public System.UInt64 ReadArrayBegin();
```

- `public ReadArrayElement(System.UInt64 index) : System.Void`  

```csharp
public System.Void ReadArrayElement(System.UInt64 index);
```

- `public ReadArrayEnd() : System.Void`  

```csharp
public System.Void ReadArrayEnd();
```

- `public ReadMapBegin() : System.UInt64`  

```csharp
public System.UInt64 ReadMapBegin();
```

- `public ReadMapEnd() : System.Void`  

```csharp
public System.Void ReadMapEnd();
```

- `public ReadMapKeyValue() : System.Void`  

```csharp
public System.Void ReadMapKeyValue();
```

- `public ReadProperty(System.String name) : System.Boolean`  

```csharp
public System.Boolean ReadProperty(System.String name);
```

- `public SkipValue() : System.Void`  

```csharp
public System.Void SkipValue();
```


