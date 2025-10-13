# Colossal.Collections.AnimationCurve1

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct AnimationCurve1
{
    private Unity.Collections.FixedList128Bytes<System.Single> m_Buffer;
    private System.Single m_MinTime;
    private System.Single m_LengthFactor;
    private System.Single <length>k__BackingField;

    public System.Single length { get; private set; }

    public AnimationCurve1(UnityEngine.AnimationCurve animationCurve);

    public System.Single Evaluate(System.Single time);
}
```


## Fields

- `private Unity.Collections.FixedList128Bytes<System.Single> m_Buffer`  

```csharp
private Unity.Collections.FixedList128Bytes<System.Single> m_Buffer;
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

- `public AnimationCurve1(UnityEngine.AnimationCurve animationCurve)`  

```csharp
public AnimationCurve1(UnityEngine.AnimationCurve animationCurve);
```


## Methods

- `public Evaluate(System.Single time) : System.Single`  

```csharp
public System.Single Evaluate(System.Single time);
```


