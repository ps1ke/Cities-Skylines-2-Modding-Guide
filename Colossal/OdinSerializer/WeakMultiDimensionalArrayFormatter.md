# Colossal.OdinSerializer.WeakMultiDimensionalArrayFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public sealed class WeakMultiDimensionalArrayFormatter : Colossal.OdinSerializer.WeakBaseFormatter, Colossal.OdinSerializer.IFormatter
{
    private readonly System.Int32 ArrayRank;
    private readonly System.Type ElementType;
    private readonly Colossal.OdinSerializer.Serializer ValueReaderWriter;
    private static const System.String RANKS_NAME;
    private static const System.Char RANKS_SEPARATOR;

    public WeakMultiDimensionalArrayFormatter(System.Type arrayType, System.Type elementType);

    protected virtual System.Void DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Object GetUninitializedObject();
    private System.Void IterateArrayRead(System.Array a, System.Action<System.Object> read);
    private System.Void IterateArrayRead(System.Array a, System.Int32 rank, System.Int32[] indices, System.Action<System.Object> read);
    private System.Void IterateArrayWrite(System.Array a, System.Func<System.Object> write);
    private System.Void IterateArrayWrite(System.Array a, System.Int32 rank, System.Int32[] indices, System.Func<System.Object> write);
    protected virtual System.Void SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private readonly System.Int32 ArrayRank`  

```csharp
private readonly System.Int32 ArrayRank;
```

- `private readonly System.Type ElementType`  

```csharp
private readonly System.Type ElementType;
```

- `private readonly Colossal.OdinSerializer.Serializer ValueReaderWriter`  

```csharp
private readonly Colossal.OdinSerializer.Serializer ValueReaderWriter;
```

- `private static const System.String RANKS_NAME`  

```csharp
private static const System.String RANKS_NAME;
```

- `private static const System.Char RANKS_SEPARATOR`  

```csharp
private static const System.Char RANKS_SEPARATOR;
```


## Constructors

- `public WeakMultiDimensionalArrayFormatter(System.Type arrayType, System.Type elementType)`  

```csharp
public WeakMultiDimensionalArrayFormatter(System.Type arrayType, System.Type elementType);
```


## Methods

- `protected virtual DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual GetUninitializedObject() : System.Object`  

```csharp
protected virtual System.Object GetUninitializedObject();
```

- `private IterateArrayRead(System.Array a, System.Action<System.Object> read) : System.Void`  

```csharp
private System.Void IterateArrayRead(System.Array a, System.Action<System.Object> read);
```

- `private IterateArrayRead(System.Array a, System.Int32 rank, System.Int32[] indices, System.Action<System.Object> read) : System.Void`  

```csharp
private System.Void IterateArrayRead(System.Array a, System.Int32 rank, System.Int32[] indices, System.Action<System.Object> read);
```

- `private IterateArrayWrite(System.Array a, System.Func<System.Object> write) : System.Void`  

```csharp
private System.Void IterateArrayWrite(System.Array a, System.Func<System.Object> write);
```

- `private IterateArrayWrite(System.Array a, System.Int32 rank, System.Int32[] indices, System.Func<System.Object> write) : System.Void`  

```csharp
private System.Void IterateArrayWrite(System.Array a, System.Int32 rank, System.Int32[] indices, System.Func<System.Object> write);
```

- `protected virtual SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
```


## Nested types

- `Colossal.OdinSerializer.WeakMultiDimensionalArrayFormatter+<>c__DisplayClass7_0`  
- `Colossal.OdinSerializer.WeakMultiDimensionalArrayFormatter+<>c__DisplayClass8_0`  

