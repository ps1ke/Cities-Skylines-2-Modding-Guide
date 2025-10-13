# Colossal.AssetPipeline.PostProcessors.AttributePackingPostProcessor+Colossal.AssetPipeline.PostProcessors.ArrayUInt32To8_0000011E$PostfixBurstDelegate

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class ArrayUInt32To8_0000011E$PostfixBurstDelegate : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public ArrayUInt32To8_0000011E$PostfixBurstDelegate(System.Object , System.IntPtr );

    public virtual System.IAsyncResult BeginInvoke(Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& srcData, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& dstData, System.Int32 count, System.AsyncCallback , System.Object );
    public virtual System.Void EndInvoke(System.IAsyncResult );
    public virtual System.Void Invoke(Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& srcData, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& dstData, System.Int32 count);
}
```


## Constructors

- `public ArrayUInt32To8_0000011E$PostfixBurstDelegate(System.Object , System.IntPtr )`  

```csharp
public ArrayUInt32To8_0000011E$PostfixBurstDelegate(System.Object , System.IntPtr );
```


## Methods

- `public virtual BeginInvoke(Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& srcData, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& dstData, System.Int32 count, System.AsyncCallback , System.Object ) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& srcData, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& dstData, System.Int32 count, System.AsyncCallback , System.Object );
```

- `public virtual EndInvoke(System.IAsyncResult ) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult );
```

- `public virtual Invoke(Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& srcData, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& dstData, System.Int32 count) : System.Void`  

```csharp
public virtual System.Void Invoke(Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& srcData, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& dstData, System.Int32 count);
```


