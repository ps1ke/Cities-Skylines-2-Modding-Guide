# Colossal.OdinSerializer.GradientFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Gradient>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.Gradient>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class GradientFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Gradient>, Colossal.OdinSerializer.IFormatter<UnityEngine.Gradient>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.GradientAlphaKey[]> AlphaKeysSerializer;
    private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.GradientColorKey[]> ColorKeysSerializer;
    private static readonly System.Reflection.PropertyInfo ModeProperty;
    private static readonly Colossal.OdinSerializer.Serializer<System.Object> EnumSerializer;

    public GradientFormatter();

    protected virtual UnityEngine.Gradient GetUninitializedObject();
    protected virtual System.Void Read(UnityEngine.Gradient& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.Gradient& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.GradientAlphaKey[]> AlphaKeysSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.GradientAlphaKey[]> AlphaKeysSerializer;
```

- `private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.GradientColorKey[]> ColorKeysSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.GradientColorKey[]> ColorKeysSerializer;
```

- `private static readonly System.Reflection.PropertyInfo ModeProperty`  

```csharp
private static readonly System.Reflection.PropertyInfo ModeProperty;
```

- `private static readonly Colossal.OdinSerializer.Serializer<System.Object> EnumSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Object> EnumSerializer;
```


## Constructors

- `public GradientFormatter()`  

```csharp
public GradientFormatter();
```


## Methods

- `protected virtual GetUninitializedObject() : UnityEngine.Gradient`  

```csharp
protected virtual UnityEngine.Gradient GetUninitializedObject();
```

- `protected virtual Read(UnityEngine.Gradient& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.Gradient& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.Gradient& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.Gradient& value, Colossal.OdinSerializer.IDataWriter writer);
```


