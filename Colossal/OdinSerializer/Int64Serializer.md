# Colossal.OdinSerializer.Int64Serializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.Int64>`  

## Code

```csharp
public sealed class Int64Serializer : Colossal.OdinSerializer.Serializer<System.Int64>
{
    public Int64Serializer();

    public virtual System.Int64 ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.Int64 value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public Int64Serializer()`  

```csharp
public Int64Serializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.Int64`  

```csharp
public virtual System.Int64 ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.Int64 value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.Int64 value, Colossal.OdinSerializer.IDataWriter writer);
```


