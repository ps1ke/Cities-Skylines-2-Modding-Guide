# Colossal.OdinSerializer.QuaternionFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Quaternion>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.Quaternion>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class QuaternionFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Quaternion>, Colossal.OdinSerializer.IFormatter<UnityEngine.Quaternion>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;

    public QuaternionFormatter();

    protected virtual System.Void Read(UnityEngine.Quaternion& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.Quaternion& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;
```


## Constructors

- `public QuaternionFormatter()`  

```csharp
public QuaternionFormatter();
```


## Methods

- `protected virtual Read(UnityEngine.Quaternion& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.Quaternion& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.Quaternion& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.Quaternion& value, Colossal.OdinSerializer.IDataWriter writer);
```


