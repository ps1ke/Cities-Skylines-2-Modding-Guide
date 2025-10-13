# Colossal.UI.Binding.IJsonReader

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IJsonReader
{
    public System.String debugName { get; }

    public abstract System.Int32 GetArgumentsCount();
    public abstract cohtml.Net.ValueType PeekValueType();
    public abstract System.Void Read(System.Boolean& value);
    public abstract System.Void Read(System.UInt32& value);
    public abstract System.Void Read(System.Int32& value);
    public abstract System.Void Read(System.Single& value);
    public abstract System.Void Read(System.Double& value);
    public abstract System.Void Read(System.String& value);
    public abstract System.UInt64 ReadArrayBegin();
    public abstract System.Void ReadArrayElement(System.UInt64 index);
    public abstract System.Void ReadArrayEnd();
    public abstract System.UInt64 ReadMapBegin();
    public abstract System.Void ReadMapEnd();
    public abstract System.Void ReadMapKeyValue();
    public abstract System.Boolean ReadProperty(System.String name);
    public abstract System.Void SkipValue();
}
```


## Properties

- `public System.String debugName { get }`  

```csharp
public System.String debugName { get; }
```


## Methods

- `public abstract GetArgumentsCount() : System.Int32`  

```csharp
public abstract System.Int32 GetArgumentsCount();
```

- `public abstract PeekValueType() : cohtml.Net.ValueType`  

```csharp
public abstract cohtml.Net.ValueType PeekValueType();
```

- `public abstract Read(System.Boolean& value) : System.Void`  

```csharp
public abstract System.Void Read(System.Boolean& value);
```

- `public abstract Read(System.UInt32& value) : System.Void`  

```csharp
public abstract System.Void Read(System.UInt32& value);
```

- `public abstract Read(System.Int32& value) : System.Void`  

```csharp
public abstract System.Void Read(System.Int32& value);
```

- `public abstract Read(System.Single& value) : System.Void`  

```csharp
public abstract System.Void Read(System.Single& value);
```

- `public abstract Read(System.Double& value) : System.Void`  

```csharp
public abstract System.Void Read(System.Double& value);
```

- `public abstract Read(System.String& value) : System.Void`  

```csharp
public abstract System.Void Read(System.String& value);
```

- `public abstract ReadArrayBegin() : System.UInt64`  

```csharp
public abstract System.UInt64 ReadArrayBegin();
```

- `public abstract ReadArrayElement(System.UInt64 index) : System.Void`  

```csharp
public abstract System.Void ReadArrayElement(System.UInt64 index);
```

- `public abstract ReadArrayEnd() : System.Void`  

```csharp
public abstract System.Void ReadArrayEnd();
```

- `public abstract ReadMapBegin() : System.UInt64`  

```csharp
public abstract System.UInt64 ReadMapBegin();
```

- `public abstract ReadMapEnd() : System.Void`  

```csharp
public abstract System.Void ReadMapEnd();
```

- `public abstract ReadMapKeyValue() : System.Void`  

```csharp
public abstract System.Void ReadMapKeyValue();
```

- `public abstract ReadProperty(System.String name) : System.Boolean`  

```csharp
public abstract System.Boolean ReadProperty(System.String name);
```

- `public abstract SkipValue() : System.Void`  

```csharp
public abstract System.Void SkipValue();
```


