# Colossal.OdinSerializer.WeakMultiDimensionalArrayFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Fields

- `private readonly System.Int32 ArrayRank`  
- `private readonly System.Type ElementType`  
- `private readonly Colossal.OdinSerializer.Serializer ValueReaderWriter`  
- `private static const System.String RANKS_NAME`  
- `private static const System.Char RANKS_SEPARATOR`  

## Constructors

- `public WeakMultiDimensionalArrayFormatter(System.Type arrayType, System.Type elementType)`  

## Methods

- `protected virtual DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  
- `protected virtual GetUninitializedObject() : System.Object`  
- `private IterateArrayRead(System.Array a, System.Action<System.Object> read) : System.Void`  
- `private IterateArrayRead(System.Array a, System.Int32 rank, System.Int32[] indices, System.Action<System.Object> read) : System.Void`  
- `private IterateArrayWrite(System.Array a, System.Func<System.Object> write) : System.Void`  
- `private IterateArrayWrite(System.Array a, System.Int32 rank, System.Int32[] indices, System.Func<System.Object> write) : System.Void`  
- `protected virtual SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

## Nested types

- `Colossal.OdinSerializer.WeakMultiDimensionalArrayFormatter+<>c__DisplayClass7_0`  
- `Colossal.OdinSerializer.WeakMultiDimensionalArrayFormatter+<>c__DisplayClass8_0`  

