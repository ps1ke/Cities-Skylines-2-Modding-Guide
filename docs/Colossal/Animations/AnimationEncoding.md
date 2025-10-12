# Colossal.Animations.AnimationEncoding

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Animations`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static const System.Int32 kPosBits`  
- `private static const System.Int32 kRotBits`  

## Methods

- `public static CalcBoundingBox(System.ReadOnlySpan<Colossal.Animations.Animation+ElementRaw> input, Unity.Mathematics.float3& positionsMin, Unity.Mathematics.float3& positionsRange) : System.Void`  
- `public static DecodeElement(Colossal.Animations.Animation+Element input, Unity.Mathematics.float3 positionsMin, Unity.Mathematics.float3 positionsRange) : Colossal.Animations.Animation+ElementRaw`  
- `public static EncodeElement(Colossal.Animations.Animation+ElementRaw input, Unity.Mathematics.float3 positionsMin, Unity.Mathematics.float3 positionsRange) : Colossal.Animations.Animation+Element`  
- `public static EncodeElements(System.ReadOnlySpan<Colossal.Animations.Animation+ElementRaw> input, System.Span<Colossal.Animations.Animation+Element> output, Unity.Mathematics.float3 positionsMin, Unity.Mathematics.float3 positionsRange) : System.Void`  
- `private static FixedToFloat3(Unity.Mathematics.uint3 u, Unity.Mathematics.float3 min, Unity.Mathematics.float3 range, System.Int32 bits) : Unity.Mathematics.float3`  
- `private static Float3ToFixed(Unity.Mathematics.float3 v, Unity.Mathematics.float3 min, Unity.Mathematics.float3 range, System.Int32 bits) : Unity.Mathematics.uint3`  
- `private static PackQuat(Unity.Mathematics.float4 q, System.Int32 bits, System.UInt32& index) : Unity.Mathematics.uint3`  
- `private static UnpackQuat(Unity.Mathematics.uint3 packed, System.UInt32 index, System.Int32 bits) : Unity.Mathematics.float4`  

