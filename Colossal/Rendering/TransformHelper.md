# Colossal.Rendering.TransformHelper

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct TransformHelper
{
    private static Unity.Mathematics.float3x4 m_Identity;

    public static Unity.Mathematics.float3x4 identity { get; }

    public static Unity.Mathematics.float3x4 Convert(Unity.Mathematics.float4x4 Value);
    public static Unity.Mathematics.float4x4 Convert(Unity.Mathematics.float3x4 Value);
    public static Unity.Mathematics.float3x4 Translate(Unity.Mathematics.float3 vector);
    public static Unity.Mathematics.float3x4 TRS(Unity.Mathematics.float3 translation, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 scale);
}
```


## Fields

- `private static Unity.Mathematics.float3x4 m_Identity`  

```csharp
private static Unity.Mathematics.float3x4 m_Identity;
```


## Properties

- `public static Unity.Mathematics.float3x4 identity { get }`  

```csharp
public static Unity.Mathematics.float3x4 identity { get; }
```


## Methods

- `public static Convert(Unity.Mathematics.float4x4 Value) : Unity.Mathematics.float3x4`  

```csharp
public static Unity.Mathematics.float3x4 Convert(Unity.Mathematics.float4x4 Value);
```

- `public static Convert(Unity.Mathematics.float3x4 Value) : Unity.Mathematics.float4x4`  

```csharp
public static Unity.Mathematics.float4x4 Convert(Unity.Mathematics.float3x4 Value);
```

- `public static Translate(Unity.Mathematics.float3 vector) : Unity.Mathematics.float3x4`  

```csharp
public static Unity.Mathematics.float3x4 Translate(Unity.Mathematics.float3 vector);
```

- `public static TRS(Unity.Mathematics.float3 translation, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 scale) : Unity.Mathematics.float3x4`  

```csharp
public static Unity.Mathematics.float3x4 TRS(Unity.Mathematics.float3 translation, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 scale);
```


