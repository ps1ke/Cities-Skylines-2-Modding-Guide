# Colossal.OdinSerializer.GuidSerializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.Guid>`  

## Code

```csharp
public sealed class GuidSerializer : Colossal.OdinSerializer.Serializer<System.Guid>
{
    public GuidSerializer();

    public virtual System.Guid ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.Guid value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public GuidSerializer()`  

```csharp
public GuidSerializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.Guid`  

```csharp
public virtual System.Guid ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.Guid value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.Guid value, Colossal.OdinSerializer.IDataWriter writer);
```


