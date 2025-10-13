# Colossal.OdinSerializer.SingleSerializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.Single>`  

## Code

```csharp
public sealed class SingleSerializer : Colossal.OdinSerializer.Serializer<System.Single>
{
    public SingleSerializer();

    public virtual System.Single ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.Single value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public SingleSerializer()`  

```csharp
public SingleSerializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.Single`  

```csharp
public virtual System.Single ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.Single value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.Single value, Colossal.OdinSerializer.IDataWriter writer);
```


