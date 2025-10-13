# Colossal.OdinSerializer.DecimalSerializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.Decimal>`  

## Code

```csharp
public sealed class DecimalSerializer : Colossal.OdinSerializer.Serializer<System.Decimal>
{
    public DecimalSerializer();

    public virtual System.Decimal ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.Decimal value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public DecimalSerializer()`  

```csharp
public DecimalSerializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.Decimal`  

```csharp
public virtual System.Decimal ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.Decimal value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.Decimal value, Colossal.OdinSerializer.IDataWriter writer);
```


