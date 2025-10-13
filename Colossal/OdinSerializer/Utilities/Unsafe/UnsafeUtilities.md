# Colossal.OdinSerializer.Utilities.Unsafe.UnsafeUtilities

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities.Unsafe`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class UnsafeUtilities
{
    public static System.Void MemoryCopy(System.Void* from, System.Void* to, System.Int32 bytes);
    public static System.Void MemoryCopy(System.Object from, System.Object to, System.Int32 byteCount, System.Int32 fromByteOffset, System.Int32 toByteOffset);
    public static System.String StringFromBytes(System.Byte[] buffer, System.Int32 charLength, System.Boolean needs16BitSupport);
    public static System.Int32 StringToBytes(System.Byte[] buffer, System.String value, System.Boolean needs16BitSupport);
    public static T[] StructArrayFromBytes<T>(System.Byte[] bytes, System.Int32 byteLength);
    public static T[] StructArrayFromBytes<T>(System.Byte[] bytes, System.Int32 byteLength, System.Int32 byteOffset);
    public static System.Byte[] StructArrayToBytes<T>(T[] array);
    public static System.Byte[] StructArrayToBytes<T>(T[] array, System.Byte[]& bytes, System.Int32 byteOffset);
}
```


## Methods

- `public static MemoryCopy(System.Void* from, System.Void* to, System.Int32 bytes) : System.Void`  

```csharp
public static System.Void MemoryCopy(System.Void* from, System.Void* to, System.Int32 bytes);
```

- `public static MemoryCopy(System.Object from, System.Object to, System.Int32 byteCount, System.Int32 fromByteOffset, System.Int32 toByteOffset) : System.Void`  

```csharp
public static System.Void MemoryCopy(System.Object from, System.Object to, System.Int32 byteCount, System.Int32 fromByteOffset, System.Int32 toByteOffset);
```

- `public static StringFromBytes(System.Byte[] buffer, System.Int32 charLength, System.Boolean needs16BitSupport) : System.String`  

```csharp
public static System.String StringFromBytes(System.Byte[] buffer, System.Int32 charLength, System.Boolean needs16BitSupport);
```

- `public static StringToBytes(System.Byte[] buffer, System.String value, System.Boolean needs16BitSupport) : System.Int32`  

```csharp
public static System.Int32 StringToBytes(System.Byte[] buffer, System.String value, System.Boolean needs16BitSupport);
```

- `public static StructArrayFromBytes<T>(System.Byte[] bytes, System.Int32 byteLength) : T[]`  

```csharp
public static T[] StructArrayFromBytes<T>(System.Byte[] bytes, System.Int32 byteLength);
```

- `public static StructArrayFromBytes<T>(System.Byte[] bytes, System.Int32 byteLength, System.Int32 byteOffset) : T[]`  

```csharp
public static T[] StructArrayFromBytes<T>(System.Byte[] bytes, System.Int32 byteLength, System.Int32 byteOffset);
```

- `public static StructArrayToBytes<T>(T[] array) : System.Byte[]`  

```csharp
public static System.Byte[] StructArrayToBytes<T>(T[] array);
```

- `public static StructArrayToBytes<T>(T[] array, System.Byte[]& bytes, System.Int32 byteOffset) : System.Byte[]`  

```csharp
public static System.Byte[] StructArrayToBytes<T>(T[] array, System.Byte[]& bytes, System.Int32 byteOffset);
```


## Nested types

- `Colossal.OdinSerializer.Utilities.Unsafe.UnsafeUtilities+Struct256Bit`  

