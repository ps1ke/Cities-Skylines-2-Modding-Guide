# Colossal.AssetPipeline.Native.NativeMath

**Assembly:** `Colossal.AssetPipeline.Native`  
**Namespace:** `Colossal.AssetPipeline.Native`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class NativeMath
{
    public static System.Void ArrayFloatDropMantissaBits(System.IntPtr src, System.Int64 srcCount, System.Int32 dropBits);
    public static System.Void ArrayFloatToHalf(System.IntPtr src, System.Int64 srcCount, System.Int32 srcDim, System.IntPtr dst, System.Int32 dstDim);
    public static System.Void ArrayHalfToFloat(System.IntPtr src, System.Int64 srcCount, System.Int32 srcDim, System.IntPtr dst, System.Int32 dstDim);
    public static System.Void ArrayNormalsToOctahedral(System.IntPtr src, System.Int64 srcCount, System.IntPtr dst);
    public static System.Void ArrayOctahedralToNormals(System.IntPtr src, System.Int64 srcCount, System.IntPtr dst);
    public static System.Void ArrayOctahedralToTangents(System.IntPtr src, System.Int64 srcCount, System.IntPtr dst);
    public static System.Void ArrayTangentsToOctahedral(System.IntPtr src, System.Int64 srcCount, System.IntPtr dst);
}
```


## Methods

- `public static ArrayFloatDropMantissaBits(System.IntPtr src, System.Int64 srcCount, System.Int32 dropBits) : System.Void`  

```csharp
public static System.Void ArrayFloatDropMantissaBits(System.IntPtr src, System.Int64 srcCount, System.Int32 dropBits);
```

- `public static ArrayFloatToHalf(System.IntPtr src, System.Int64 srcCount, System.Int32 srcDim, System.IntPtr dst, System.Int32 dstDim) : System.Void`  

```csharp
public static System.Void ArrayFloatToHalf(System.IntPtr src, System.Int64 srcCount, System.Int32 srcDim, System.IntPtr dst, System.Int32 dstDim);
```

- `public static ArrayHalfToFloat(System.IntPtr src, System.Int64 srcCount, System.Int32 srcDim, System.IntPtr dst, System.Int32 dstDim) : System.Void`  

```csharp
public static System.Void ArrayHalfToFloat(System.IntPtr src, System.Int64 srcCount, System.Int32 srcDim, System.IntPtr dst, System.Int32 dstDim);
```

- `public static ArrayNormalsToOctahedral(System.IntPtr src, System.Int64 srcCount, System.IntPtr dst) : System.Void`  

```csharp
public static System.Void ArrayNormalsToOctahedral(System.IntPtr src, System.Int64 srcCount, System.IntPtr dst);
```

- `public static ArrayOctahedralToNormals(System.IntPtr src, System.Int64 srcCount, System.IntPtr dst) : System.Void`  

```csharp
public static System.Void ArrayOctahedralToNormals(System.IntPtr src, System.Int64 srcCount, System.IntPtr dst);
```

- `public static ArrayOctahedralToTangents(System.IntPtr src, System.Int64 srcCount, System.IntPtr dst) : System.Void`  

```csharp
public static System.Void ArrayOctahedralToTangents(System.IntPtr src, System.Int64 srcCount, System.IntPtr dst);
```

- `public static ArrayTangentsToOctahedral(System.IntPtr src, System.Int64 srcCount, System.IntPtr dst) : System.Void`  

```csharp
public static System.Void ArrayTangentsToOctahedral(System.IntPtr src, System.Int64 srcCount, System.IntPtr dst);
```


