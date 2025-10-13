# Colossal.OdinSerializer.Int32Serializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.Int32>`  

## Code

```csharp
public sealed class Int32Serializer : Colossal.OdinSerializer.Serializer<System.Int32>
{
    public Int32Serializer();

    public virtual System.Int32 ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.Int32 value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public Int32Serializer()`  

```csharp
public Int32Serializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.Int32`  

```csharp
public virtual System.Int32 ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.Int32 value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.Int32 value, Colossal.OdinSerializer.IDataWriter writer);
```


