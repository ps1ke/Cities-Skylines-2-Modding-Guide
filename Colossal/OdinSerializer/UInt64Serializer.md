# Colossal.OdinSerializer.UInt64Serializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.UInt64>`  

## Code

```csharp
public sealed class UInt64Serializer : Colossal.OdinSerializer.Serializer<System.UInt64>
{
    public UInt64Serializer();

    public virtual System.UInt64 ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.UInt64 value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public UInt64Serializer()`  

```csharp
public UInt64Serializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.UInt64`  

```csharp
public virtual System.UInt64 ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.UInt64 value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.UInt64 value, Colossal.OdinSerializer.IDataWriter writer);
```


