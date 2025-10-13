# Colossal.Collections.AnimationCurve3

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct AnimationCurve3
{
    private Unity.Collections.FixedList512Bytes<Unity.Mathematics.float3> m_Buffer;
    private System.Single m_MinTime;
    private System.Single m_LengthFactor;
    private System.Single <length>k__BackingField;

    public System.Single length { get; private set; }

    public AnimationCurve3(UnityEngine.AnimationCurve animationCurveX, UnityEngine.AnimationCurve animationCurveY, UnityEngine.AnimationCurve animationCurveZ);

    public Unity.Mathematics.float3 Evaluate(System.Single time);
}
```


## Fields

- `private Unity.Collections.FixedList512Bytes<Unity.Mathematics.float3> m_Buffer`  

```csharp
private Unity.Collections.FixedList512Bytes<Unity.Mathematics.float3> m_Buffer;
```

- `private System.Single m_MinTime`  

```csharp
private System.Single m_MinTime;
```

- `private System.Single m_LengthFactor`  

```csharp
private System.Single m_LengthFactor;
```

- `private System.Single <length>k__BackingField`  

```csharp
private System.Single <length>k__BackingField;
```


## Properties

- `public System.Single length { get; private set }`  

```csharp
public System.Single length { get; private set; }
```


## Constructors

- `public AnimationCurve3(UnityEngine.AnimationCurve animationCurveX, UnityEngine.AnimationCurve animationCurveY, UnityEngine.AnimationCurve animationCurveZ)`  

```csharp
public AnimationCurve3(UnityEngine.AnimationCurve animationCurveX, UnityEngine.AnimationCurve animationCurveY, UnityEngine.AnimationCurve animationCurveZ);
```


## Methods

- `public Evaluate(System.Single time) : Unity.Mathematics.float3`  

```csharp
public Unity.Mathematics.float3 Evaluate(System.Single time);
```


