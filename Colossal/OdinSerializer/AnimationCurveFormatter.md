# Colossal.OdinSerializer.AnimationCurveFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.AnimationCurve>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.AnimationCurve>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class AnimationCurveFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.AnimationCurve>, Colossal.OdinSerializer.IFormatter<UnityEngine.AnimationCurve>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.Keyframe[]> KeyframeSerializer;
    private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.WrapMode> WrapModeSerializer;

    public AnimationCurveFormatter();

    protected virtual UnityEngine.AnimationCurve GetUninitializedObject();
    protected virtual System.Void Read(UnityEngine.AnimationCurve& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.AnimationCurve& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.Keyframe[]> KeyframeSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.Keyframe[]> KeyframeSerializer;
```

- `private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.WrapMode> WrapModeSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.WrapMode> WrapModeSerializer;
```


## Constructors

- `public AnimationCurveFormatter()`  

```csharp
public AnimationCurveFormatter();
```


## Methods

- `protected virtual GetUninitializedObject() : UnityEngine.AnimationCurve`  

```csharp
protected virtual UnityEngine.AnimationCurve GetUninitializedObject();
```

- `protected virtual Read(UnityEngine.AnimationCurve& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.AnimationCurve& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.AnimationCurve& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.AnimationCurve& value, Colossal.OdinSerializer.IDataWriter writer);
```


