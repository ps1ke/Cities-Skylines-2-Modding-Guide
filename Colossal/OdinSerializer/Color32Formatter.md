# Colossal.OdinSerializer.Color32Formatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Color32>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.Color32>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class Color32Formatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Color32>, Colossal.OdinSerializer.IFormatter<UnityEngine.Color32>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<System.Byte> ByteSerializer;

    public Color32Formatter();

    protected virtual System.Void Read(UnityEngine.Color32& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.Color32& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<System.Byte> ByteSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Byte> ByteSerializer;
```


## Constructors

- `public Color32Formatter()`  

```csharp
public Color32Formatter();
```


## Methods

- `protected virtual Read(UnityEngine.Color32& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.Color32& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.Color32& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.Color32& value, Colossal.OdinSerializer.IDataWriter writer);
```


