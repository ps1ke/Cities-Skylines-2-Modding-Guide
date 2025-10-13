# Colossal.OdinSerializer.Int16Serializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.Int16>`  

## Code

```csharp
public sealed class Int16Serializer : Colossal.OdinSerializer.Serializer<System.Int16>
{
    public Int16Serializer();

    public virtual System.Int16 ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.Int16 value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public Int16Serializer()`  

```csharp
public Int16Serializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.Int16`  

```csharp
public virtual System.Int16 ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.Int16 value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.Int16 value, Colossal.OdinSerializer.IDataWriter writer);
```


