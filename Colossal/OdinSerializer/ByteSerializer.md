# Colossal.OdinSerializer.ByteSerializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.Byte>`  

## Code

```csharp
public sealed class ByteSerializer : Colossal.OdinSerializer.Serializer<System.Byte>
{
    public ByteSerializer();

    public virtual System.Byte ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.Byte value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public ByteSerializer()`  

```csharp
public ByteSerializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.Byte`  

```csharp
public virtual System.Byte ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.Byte value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.Byte value, Colossal.OdinSerializer.IDataWriter writer);
```


