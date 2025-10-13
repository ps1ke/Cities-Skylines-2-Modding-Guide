# Colossal.OdinSerializer.DoubleSerializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.Double>`  

## Code

```csharp
public sealed class DoubleSerializer : Colossal.OdinSerializer.Serializer<System.Double>
{
    public DoubleSerializer();

    public virtual System.Double ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.Double value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public DoubleSerializer()`  

```csharp
public DoubleSerializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.Double`  

```csharp
public virtual System.Double ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.Double value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.Double value, Colossal.OdinSerializer.IDataWriter writer);
```


