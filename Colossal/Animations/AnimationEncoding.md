# Colossal.Animations.AnimationEncoding

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Animations`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class AnimationEncoding
{
    private static const System.Int32 kPosBits;
    private static const System.Int32 kRotBits;

    public static System.Void CalcBoundingBox(System.ReadOnlySpan<Colossal.Animations.Animation+ElementRaw> input, Unity.Mathematics.float3& positionsMin, Unity.Mathematics.float3& positionsRange);
    public static Colossal.Animations.Animation+ElementRaw DecodeElement(Colossal.Animations.Animation+Element input, Unity.Mathematics.float3 positionsMin, Unity.Mathematics.float3 positionsRange);
    public static Colossal.Animations.Animation+Element EncodeElement(Colossal.Animations.Animation+ElementRaw input, Unity.Mathematics.float3 positionsMin, Unity.Mathematics.float3 positionsRange);
    public static System.Void EncodeElements(System.ReadOnlySpan<Colossal.Animations.Animation+ElementRaw> input, System.Span<Colossal.Animations.Animation+Element> output, Unity.Mathematics.float3 positionsMin, Unity.Mathematics.float3 positionsRange);
    private static Unity.Mathematics.float3 FixedToFloat3(Unity.Mathematics.uint3 u, Unity.Mathematics.float3 min, Unity.Mathematics.float3 range, System.Int32 bits);
    private static Unity.Mathematics.uint3 Float3ToFixed(Unity.Mathematics.float3 v, Unity.Mathematics.float3 min, Unity.Mathematics.float3 range, System.Int32 bits);
    private static Unity.Mathematics.uint3 PackQuat(Unity.Mathematics.float4 q, System.Int32 bits, System.UInt32& index);
    private static Unity.Mathematics.float4 UnpackQuat(Unity.Mathematics.uint3 packed, System.UInt32 index, System.Int32 bits);
}
```


## Fields

- `private static const System.Int32 kPosBits`  

```csharp
private static const System.Int32 kPosBits;
```

- `private static const System.Int32 kRotBits`  

```csharp
private static const System.Int32 kRotBits;
```


## Methods

- `public static CalcBoundingBox(System.ReadOnlySpan<Colossal.Animations.Animation+ElementRaw> input, Unity.Mathematics.float3& positionsMin, Unity.Mathematics.float3& positionsRange) : System.Void`  

```csharp
public static System.Void CalcBoundingBox(System.ReadOnlySpan<Colossal.Animations.Animation+ElementRaw> input, Unity.Mathematics.float3& positionsMin, Unity.Mathematics.float3& positionsRange);
```

- `public static DecodeElement(Colossal.Animations.Animation+Element input, Unity.Mathematics.float3 positionsMin, Unity.Mathematics.float3 positionsRange) : Colossal.Animations.Animation+ElementRaw`  

```csharp
public static Colossal.Animations.Animation+ElementRaw DecodeElement(Colossal.Animations.Animation+Element input, Unity.Mathematics.float3 positionsMin, Unity.Mathematics.float3 positionsRange);
```

- `public static EncodeElement(Colossal.Animations.Animation+ElementRaw input, Unity.Mathematics.float3 positionsMin, Unity.Mathematics.float3 positionsRange) : Colossal.Animations.Animation+Element`  

```csharp
public static Colossal.Animations.Animation+Element EncodeElement(Colossal.Animations.Animation+ElementRaw input, Unity.Mathematics.float3 positionsMin, Unity.Mathematics.float3 positionsRange);
```

- `public static EncodeElements(System.ReadOnlySpan<Colossal.Animations.Animation+ElementRaw> input, System.Span<Colossal.Animations.Animation+Element> output, Unity.Mathematics.float3 positionsMin, Unity.Mathematics.float3 positionsRange) : System.Void`  

```csharp
public static System.Void EncodeElements(System.ReadOnlySpan<Colossal.Animations.Animation+ElementRaw> input, System.Span<Colossal.Animations.Animation+Element> output, Unity.Mathematics.float3 positionsMin, Unity.Mathematics.float3 positionsRange);
```

- `private static FixedToFloat3(Unity.Mathematics.uint3 u, Unity.Mathematics.float3 min, Unity.Mathematics.float3 range, System.Int32 bits) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 FixedToFloat3(Unity.Mathematics.uint3 u, Unity.Mathematics.float3 min, Unity.Mathematics.float3 range, System.Int32 bits);
```

- `private static Float3ToFixed(Unity.Mathematics.float3 v, Unity.Mathematics.float3 min, Unity.Mathematics.float3 range, System.Int32 bits) : Unity.Mathematics.uint3`  

```csharp
private static Unity.Mathematics.uint3 Float3ToFixed(Unity.Mathematics.float3 v, Unity.Mathematics.float3 min, Unity.Mathematics.float3 range, System.Int32 bits);
```

- `private static PackQuat(Unity.Mathematics.float4 q, System.Int32 bits, System.UInt32& index) : Unity.Mathematics.uint3`  

```csharp
private static Unity.Mathematics.uint3 PackQuat(Unity.Mathematics.float4 q, System.Int32 bits, System.UInt32& index);
```

- `private static UnpackQuat(Unity.Mathematics.uint3 packed, System.UInt32 index, System.Int32 bits) : Unity.Mathematics.float4`  

```csharp
private static Unity.Mathematics.float4 UnpackQuat(Unity.Mathematics.uint3 packed, System.UInt32 index, System.Int32 bits);
```


