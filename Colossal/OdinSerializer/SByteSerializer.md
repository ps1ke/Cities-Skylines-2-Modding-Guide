# Colossal.OdinSerializer.SByteSerializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.SByte>`  

## Code

```csharp
public sealed class SByteSerializer : Colossal.OdinSerializer.Serializer<System.SByte>
{
    public SByteSerializer();

    public virtual System.SByte ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.SByte value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public SByteSerializer()`  

```csharp
public SByteSerializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.SByte`  

```csharp
public virtual System.SByte ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.SByte value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.SByte value, Colossal.OdinSerializer.IDataWriter writer);
```


