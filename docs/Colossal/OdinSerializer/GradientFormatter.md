# Colossal.OdinSerializer.GradientFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Gradient>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.Gradient>`, `Colossal.OdinSerializer.IFormatter`  

## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.GradientAlphaKey[]> AlphaKeysSerializer`  
- `private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.GradientColorKey[]> ColorKeysSerializer`  
- `private static readonly System.Reflection.PropertyInfo ModeProperty`  
- `private static readonly Colossal.OdinSerializer.Serializer<System.Object> EnumSerializer`  

## Constructors

- `public GradientFormatter()`  

## Methods

- `protected virtual GetUninitializedObject() : UnityEngine.Gradient`  
- `protected virtual Read(UnityEngine.Gradient& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  
- `protected virtual Write(UnityEngine.Gradient& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

