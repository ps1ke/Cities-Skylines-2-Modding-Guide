# Colossal.OdinSerializer.StringSerializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.String>`  

## Code

```csharp
public sealed class StringSerializer : Colossal.OdinSerializer.Serializer<System.String>
{
    public StringSerializer();

    public virtual System.String ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.String value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public StringSerializer()`  

```csharp
public StringSerializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.String`  

```csharp
public virtual System.String ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.String value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.String value, Colossal.OdinSerializer.IDataWriter writer);
```


