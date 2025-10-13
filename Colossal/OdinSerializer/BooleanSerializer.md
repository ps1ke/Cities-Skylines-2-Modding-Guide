# Colossal.OdinSerializer.BooleanSerializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.Boolean>`  

## Code

```csharp
public sealed class BooleanSerializer : Colossal.OdinSerializer.Serializer<System.Boolean>
{
    public BooleanSerializer();

    public virtual System.Boolean ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.Boolean value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public BooleanSerializer()`  

```csharp
public BooleanSerializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.Boolean`  

```csharp
public virtual System.Boolean ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.Boolean value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.Boolean value, Colossal.OdinSerializer.IDataWriter writer);
```


