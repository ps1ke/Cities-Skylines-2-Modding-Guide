# Colossal.OdinSerializer.SerializationUtility

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `public static CreateCopy(System.Object obj) : System.Object`  
- `public static CreateReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context, Colossal.OdinSerializer.DataFormat format) : Colossal.OdinSerializer.IDataReader`  
- `public static CreateWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context, Colossal.OdinSerializer.DataFormat format) : Colossal.OdinSerializer.IDataWriter`  
- `public static DeserializeValue<T>(Colossal.OdinSerializer.IDataReader reader) : T`  
- `public static DeserializeValue<T>(Colossal.OdinSerializer.IDataReader reader, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects) : T`  
- `public static DeserializeValue<T>(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context = null) : T`  
- `public static DeserializeValue<T>(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects, Colossal.OdinSerializer.DeserializationContext context = null) : T`  
- `public static DeserializeValue<T>(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context = null) : T`  
- `public static DeserializeValue<T>(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects, Colossal.OdinSerializer.DeserializationContext context = null) : T`  
- `public static DeserializeValueWeak(Colossal.OdinSerializer.IDataReader reader) : System.Object`  
- `public static DeserializeValueWeak(Colossal.OdinSerializer.IDataReader reader, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects) : System.Object`  
- `public static DeserializeValueWeak(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context = null) : System.Object`  
- `public static DeserializeValueWeak(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects, Colossal.OdinSerializer.DeserializationContext context = null) : System.Object`  
- `public static DeserializeValueWeak(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context = null) : System.Object`  
- `public static DeserializeValueWeak(System.Byte[] bytes, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects) : System.Object`  
- `private static GetCachedReader(System.IDisposable& cache, Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context) : Colossal.OdinSerializer.IDataReader`  
- `private static GetCachedWriter(System.IDisposable& cache, Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context) : Colossal.OdinSerializer.IDataWriter`  
- `public static PeekType(System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context = null) : System.Type`  
- `public static SerializeValue<T>(T value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  
- `public static SerializeValue<T>(T value, Colossal.OdinSerializer.IDataWriter writer, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects) : System.Void`  
- `public static SerializeValue<T>(T value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context = null) : System.Void`  
- `public static SerializeValue<T>(T value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects, Colossal.OdinSerializer.SerializationContext context = null) : System.Void`  
- `public static SerializeValue<T>(T value, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context = null) : System.Byte[]`  
- `public static SerializeValue<T>(T value, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects, Colossal.OdinSerializer.SerializationContext context = null) : System.Byte[]`  
- `public static SerializeValueWeak(System.Object value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  
- `public static SerializeValueWeak(System.Object value, Colossal.OdinSerializer.IDataWriter writer, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects) : System.Void`  
- `public static SerializeValueWeak(System.Object value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context = null) : System.Void`  
- `public static SerializeValueWeak(System.Object value, System.IO.Stream stream, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects, Colossal.OdinSerializer.SerializationContext context = null) : System.Void`  
- `public static SerializeValueWeak(System.Object value, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.SerializationContext context = null) : System.Byte[]`  
- `public static SerializeValueWeak(System.Object value, Colossal.OdinSerializer.DataFormat format, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unityObjects) : System.Byte[]`  

