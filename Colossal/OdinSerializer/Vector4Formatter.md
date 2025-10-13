# Colossal.OdinSerializer.Vector4Formatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Vector4>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.Vector4>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class Vector4Formatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Vector4>, Colossal.OdinSerializer.IFormatter<UnityEngine.Vector4>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;

    public Vector4Formatter();

    protected virtual System.Void Read(UnityEngine.Vector4& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.Vector4& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;
```


## Constructors

- `public Vector4Formatter()`  

```csharp
public Vector4Formatter();
```


## Methods

- `protected virtual Read(UnityEngine.Vector4& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.Vector4& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.Vector4& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.Vector4& value, Colossal.OdinSerializer.IDataWriter writer);
```


