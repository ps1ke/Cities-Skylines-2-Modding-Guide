# Colossal.OdinSerializer.AnimationCurveFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.AnimationCurve>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.AnimationCurve>`, `Colossal.OdinSerializer.IFormatter`  

## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.Keyframe[]> KeyframeSerializer`  
- `private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.WrapMode> WrapModeSerializer`  

## Constructors

- `public AnimationCurveFormatter()`  

## Methods

- `protected virtual GetUninitializedObject() : UnityEngine.AnimationCurve`  
- `protected virtual Read(UnityEngine.AnimationCurve& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  
- `protected virtual Write(UnityEngine.AnimationCurve& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

