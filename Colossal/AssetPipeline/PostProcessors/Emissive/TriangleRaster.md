# Colossal.AssetPipeline.PostProcessors.Emissive.TriangleRaster

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Emissive`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class TriangleRaster
{
    private static const System.Int32 kSubpixelBits;
    private static const System.Int32 kSubpixelScale;

    private static System.Int64 Det2x2FillConvention(System.Int32 a, System.Int32 b, System.Int32 c, System.Int32 d);
    private static System.Int64 Det2x2Fixed(System.Int32 a, System.Int32 b, System.Int32 c, System.Int32 d);
    public static System.Void DrawTriangle<T>(T shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2 pt0, Unity.Mathematics.float2 pt1, Unity.Mathematics.float2 pt2);
    private static Unity.Mathematics.int2 FixedCeil(Unity.Mathematics.int2 x);
    private static System.Int32 FloatToFixed(System.Single x);
    private static Unity.Mathematics.int2 Max3(Unity.Mathematics.int2 a, Unity.Mathematics.int2 b, Unity.Mathematics.int2 c);
    private static Unity.Mathematics.int2 Min3(Unity.Mathematics.int2 a, Unity.Mathematics.int2 b, Unity.Mathematics.int2 c);
    private static Unity.Mathematics.int2 PointToFixed(Unity.Mathematics.float2 p, System.Single width, System.Single height);
}
```


## Fields

- `private static const System.Int32 kSubpixelBits`  

```csharp
private static const System.Int32 kSubpixelBits;
```

- `private static const System.Int32 kSubpixelScale`  

```csharp
private static const System.Int32 kSubpixelScale;
```


## Methods

- `private static Det2x2FillConvention(System.Int32 a, System.Int32 b, System.Int32 c, System.Int32 d) : System.Int64`  

```csharp
private static System.Int64 Det2x2FillConvention(System.Int32 a, System.Int32 b, System.Int32 c, System.Int32 d);
```

- `private static Det2x2Fixed(System.Int32 a, System.Int32 b, System.Int32 c, System.Int32 d) : System.Int64`  

```csharp
private static System.Int64 Det2x2Fixed(System.Int32 a, System.Int32 b, System.Int32 c, System.Int32 d);
```

- `public static DrawTriangle<T>(T shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2 pt0, Unity.Mathematics.float2 pt1, Unity.Mathematics.float2 pt2) : System.Void`  

```csharp
public static System.Void DrawTriangle<T>(T shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2 pt0, Unity.Mathematics.float2 pt1, Unity.Mathematics.float2 pt2);
```

- `private static FixedCeil(Unity.Mathematics.int2 x) : Unity.Mathematics.int2`  

```csharp
private static Unity.Mathematics.int2 FixedCeil(Unity.Mathematics.int2 x);
```

- `private static FloatToFixed(System.Single x) : System.Int32`  

```csharp
private static System.Int32 FloatToFixed(System.Single x);
```

- `private static Max3(Unity.Mathematics.int2 a, Unity.Mathematics.int2 b, Unity.Mathematics.int2 c) : Unity.Mathematics.int2`  

```csharp
private static Unity.Mathematics.int2 Max3(Unity.Mathematics.int2 a, Unity.Mathematics.int2 b, Unity.Mathematics.int2 c);
```

- `private static Min3(Unity.Mathematics.int2 a, Unity.Mathematics.int2 b, Unity.Mathematics.int2 c) : Unity.Mathematics.int2`  

```csharp
private static Unity.Mathematics.int2 Min3(Unity.Mathematics.int2 a, Unity.Mathematics.int2 b, Unity.Mathematics.int2 c);
```

- `private static PointToFixed(Unity.Mathematics.float2 p, System.Single width, System.Single height) : Unity.Mathematics.int2`  

```csharp
private static Unity.Mathematics.int2 PointToFixed(Unity.Mathematics.float2 p, System.Single width, System.Single height);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.Emissive.TriangleRaster+IShader`  

