# Colossal.OdinSerializer.GradientColorKeyFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.GradientColorKey>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.GradientColorKey>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class GradientColorKeyFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.GradientColorKey>, Colossal.OdinSerializer.IFormatter<UnityEngine.GradientColorKey>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.Color> ColorSerializer;
    private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;

    public GradientColorKeyFormatter();

    protected virtual System.Void Read(UnityEngine.GradientColorKey& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.GradientColorKey& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.Color> ColorSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.Color> ColorSerializer;
```

- `private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;
```


## Constructors

- `public GradientColorKeyFormatter()`  

```csharp
public GradientColorKeyFormatter();
```


## Methods

- `protected virtual Read(UnityEngine.GradientColorKey& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.GradientColorKey& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.GradientColorKey& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.GradientColorKey& value, Colossal.OdinSerializer.IDataWriter writer);
```


