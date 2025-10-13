# Colossal.OdinSerializer.Vector3Formatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Vector3>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.Vector3>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class Vector3Formatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Vector3>, Colossal.OdinSerializer.IFormatter<UnityEngine.Vector3>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;

    public Vector3Formatter();

    protected virtual System.Void Read(UnityEngine.Vector3& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.Vector3& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;
```


## Constructors

- `public Vector3Formatter()`  

```csharp
public Vector3Formatter();
```


## Methods

- `protected virtual Read(UnityEngine.Vector3& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.Vector3& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.Vector3& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.Vector3& value, Colossal.OdinSerializer.IDataWriter writer);
```


