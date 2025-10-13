# Colossal.OdinSerializer.SerializationUtility

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class SerializationUtility
{
    public static System.Object CreateCopy(System.Object obj);
    public static Colossal.OdinSerializer.IDataReader CreateReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context, Colossal.OdinSerializer.DataFormat format);
    public static Colossal.OdinSerializer.IDataWriter CreateWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context, Colossal.OdinSerializer.DataFormat format);
    public static T DeserializeValue<T>(Colossal.OdinSerializer.IDataReader reader);
    public static T DeserializeValue<T>(Colossal.OdinSerializer.IDataReader reader, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects);
    public static T DeserializeValue<T>(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context);
    public static T DeserializeValue<T>(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects, Colossal.OdinSerializer.DeserializationContext context);
    public static T DeserializeValue<T>(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context);
    public static T DeserializeValue<T>(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects, Colossal.OdinSerializer.DeserializationContext context);
    public static System.Object DeserializeValueWeak(Colossal.OdinSerializer.IDataReader reader);
    public static System.Object DeserializeValueWeak(Colossal.OdinSerializer.IDataReader reader, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects);
    public static System.Object DeserializeValueWeak(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context);
    public static System.Object DeserializeValueWeak(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects, Colossal.OdinSerializer.DeserializationContext context);
    public static System.Object DeserializeValueWeak(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context);
    public static System.Object DeserializeValueWeak(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects);
    private static Colossal.OdinSerializer.IDataReader GetCachedReader(System.IDisposable& cache, Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context);
    private static Colossal.OdinSerializer.IDataWriter GetCachedWriter(System.IDisposable& cache, Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context);
    public static System.Type PeekType(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context);
    public static System.Void SerializeValue<T>(T value, Colossal.OdinSerializer.IDataWriter writer);
    public static System.Void SerializeValue<T>(T value, Colossal.OdinSerializer.IDataWriter writer, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects);
    public static System.Void SerializeValue<T>(T value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context);
    public static System.Void SerializeValue<T>(T value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects, Colossal.OdinSerializer.SerializationContext context);
    public static System.Byte[] SerializeValue<T>(T value, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context);
    public static System.Byte[] SerializeValue<T>(T value, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects, Colossal.OdinSerializer.SerializationContext context);
    public static System.Void SerializeValueWeak(System.Object value, Colossal.OdinSerializer.IDataWriter writer);
    public static System.Void SerializeValueWeak(System.Object value, Colossal.OdinSerializer.IDataWriter writer, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects);
    public static System.Void SerializeValueWeak(System.Object value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context);
    public static System.Void SerializeValueWeak(System.Object value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects, Colossal.OdinSerializer.SerializationContext context);
    public static System.Byte[] SerializeValueWeak(System.Object value, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context);
    public static System.Byte[] SerializeValueWeak(System.Object value, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects);
}
```


## Methods

- `public static CreateCopy(System.Object obj) : System.Object`  

```csharp
public static System.Object CreateCopy(System.Object obj);
```

- `public static CreateReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context, Colossal.OdinSerializer.DataFormat format) : Colossal.OdinSerializer.IDataReader`  

```csharp
public static Colossal.OdinSerializer.IDataReader CreateReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context, Colossal.OdinSerializer.DataFormat format);
```

- `public static CreateWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context, Colossal.OdinSerializer.DataFormat format) : Colossal.OdinSerializer.IDataWriter`  

```csharp
public static Colossal.OdinSerializer.IDataWriter CreateWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context, Colossal.OdinSerializer.DataFormat format);
```

- `public static DeserializeValue<T>(Colossal.OdinSerializer.IDataReader reader) : T`  

```csharp
public static T DeserializeValue<T>(Colossal.OdinSerializer.IDataReader reader);
```

- `public static DeserializeValue<T>(Colossal.OdinSerializer.IDataReader reader, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects) : T`  

```csharp
public static T DeserializeValue<T>(Colossal.OdinSerializer.IDataReader reader, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects);
```

- `public static DeserializeValue<T>(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context = null) : T`  

```csharp
public static T DeserializeValue<T>(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context);
```

- `public static DeserializeValue<T>(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects, Colossal.OdinSerializer.DeserializationContext context = null) : T`  

```csharp
public static T DeserializeValue<T>(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects, Colossal.OdinSerializer.DeserializationContext context);
```

- `public static DeserializeValue<T>(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context = null) : T`  

```csharp
public static T DeserializeValue<T>(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context);
```

- `public static DeserializeValue<T>(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects, Colossal.OdinSerializer.DeserializationContext context = null) : T`  

```csharp
public static T DeserializeValue<T>(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects, Colossal.OdinSerializer.DeserializationContext context);
```

- `public static DeserializeValueWeak(Colossal.OdinSerializer.IDataReader reader) : System.Object`  

```csharp
public static System.Object DeserializeValueWeak(Colossal.OdinSerializer.IDataReader reader);
```

- `public static DeserializeValueWeak(Colossal.OdinSerializer.IDataReader reader, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects) : System.Object`  

```csharp
public static System.Object DeserializeValueWeak(Colossal.OdinSerializer.IDataReader reader, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects);
```

- `public static DeserializeValueWeak(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context = null) : System.Object`  

```csharp
public static System.Object DeserializeValueWeak(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context);
```

- `public static DeserializeValueWeak(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects, Colossal.OdinSerializer.DeserializationContext context = null) : System.Object`  

```csharp
public static System.Object DeserializeValueWeak(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects, Colossal.OdinSerializer.DeserializationContext context);
```

- `public static DeserializeValueWeak(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context = null) : System.Object`  

```csharp
public static System.Object DeserializeValueWeak(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context);
```

- `public static DeserializeValueWeak(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects) : System.Object`  

```csharp
public static System.Object DeserializeValueWeak(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects);
```

- `private static GetCachedReader(System.IDisposable& cache, Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context) : Colossal.OdinSerializer.IDataReader`  

```csharp
private static Colossal.OdinSerializer.IDataReader GetCachedReader(System.IDisposable& cache, Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context);
```

- `private static GetCachedWriter(System.IDisposable& cache, Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context) : Colossal.OdinSerializer.IDataWriter`  

```csharp
private static Colossal.OdinSerializer.IDataWriter GetCachedWriter(System.IDisposable& cache, Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context);
```

- `public static PeekType(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context = null) : System.Type`  

```csharp
public static System.Type PeekType(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context);
```

- `public static SerializeValue<T>(T value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public static System.Void SerializeValue<T>(T value, Colossal.OdinSerializer.IDataWriter writer);
```

- `public static SerializeValue<T>(T value, Colossal.OdinSerializer.IDataWriter writer, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects) : System.Void`  

```csharp
public static System.Void SerializeValue<T>(T value, Colossal.OdinSerializer.IDataWriter writer, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects);
```

- `public static SerializeValue<T>(T value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context = null) : System.Void`  

```csharp
public static System.Void SerializeValue<T>(T value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context);
```

- `public static SerializeValue<T>(T value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects, Colossal.OdinSerializer.SerializationContext context = null) : System.Void`  

```csharp
public static System.Void SerializeValue<T>(T value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects, Colossal.OdinSerializer.SerializationContext context);
```

- `public static SerializeValue<T>(T value, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context = null) : System.Byte[]`  

```csharp
public static System.Byte[] SerializeValue<T>(T value, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context);
```

- `public static SerializeValue<T>(T value, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects, Colossal.OdinSerializer.SerializationContext context = null) : System.Byte[]`  

```csharp
public static System.Byte[] SerializeValue<T>(T value, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects, Colossal.OdinSerializer.SerializationContext context);
```

- `public static SerializeValueWeak(System.Object value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public static System.Void SerializeValueWeak(System.Object value, Colossal.OdinSerializer.IDataWriter writer);
```

- `public static SerializeValueWeak(System.Object value, Colossal.OdinSerializer.IDataWriter writer, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects) : System.Void`  

```csharp
public static System.Void SerializeValueWeak(System.Object value, Colossal.OdinSerializer.IDataWriter writer, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects);
```

- `public static SerializeValueWeak(System.Object value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context = null) : System.Void`  

```csharp
public static System.Void SerializeValueWeak(System.Object value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context);
```

- `public static SerializeValueWeak(System.Object value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects, Colossal.OdinSerializer.SerializationContext context = null) : System.Void`  

```csharp
public static System.Void SerializeValueWeak(System.Object value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects, Colossal.OdinSerializer.SerializationContext context);
```

- `public static SerializeValueWeak(System.Object value, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context = null) : System.Byte[]`  

```csharp
public static System.Byte[] SerializeValueWeak(System.Object value, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context);
```

- `public static SerializeValueWeak(System.Object value, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects) : System.Byte[]`  

```csharp
public static System.Byte[] SerializeValueWeak(System.Object value, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects);
```


