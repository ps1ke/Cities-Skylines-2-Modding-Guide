# Colossal.OdinSerializer.GradientAlphaKeyFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.GradientAlphaKey>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.GradientAlphaKey>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class GradientAlphaKeyFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.GradientAlphaKey>, Colossal.OdinSerializer.IFormatter<UnityEngine.GradientAlphaKey>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;

    public GradientAlphaKeyFormatter();

    protected virtual System.Void Read(UnityEngine.GradientAlphaKey& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.GradientAlphaKey& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;
```


## Constructors

- `public GradientAlphaKeyFormatter()`  

```csharp
public GradientAlphaKeyFormatter();
```


## Methods

- `protected virtual Read(UnityEngine.GradientAlphaKey& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.GradientAlphaKey& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.GradientAlphaKey& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.GradientAlphaKey& value, Colossal.OdinSerializer.IDataWriter writer);
```


