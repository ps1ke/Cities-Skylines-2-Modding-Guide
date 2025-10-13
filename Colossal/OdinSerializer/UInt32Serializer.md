# Colossal.OdinSerializer.UInt32Serializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.UInt32>`  

## Code

```csharp
public sealed class UInt32Serializer : Colossal.OdinSerializer.Serializer<System.UInt32>
{
    public UInt32Serializer();

    public virtual System.UInt32 ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.UInt32 value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public UInt32Serializer()`  

```csharp
public UInt32Serializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.UInt32`  

```csharp
public virtual System.UInt32 ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.UInt32 value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.UInt32 value, Colossal.OdinSerializer.IDataWriter writer);
```


