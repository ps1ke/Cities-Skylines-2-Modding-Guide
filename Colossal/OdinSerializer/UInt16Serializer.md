# Colossal.OdinSerializer.UInt16Serializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.UInt16>`  

## Code

```csharp
public sealed class UInt16Serializer : Colossal.OdinSerializer.Serializer<System.UInt16>
{
    public UInt16Serializer();

    public virtual System.UInt16 ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.UInt16 value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public UInt16Serializer()`  

```csharp
public UInt16Serializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.UInt16`  

```csharp
public virtual System.UInt16 ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.UInt16 value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.UInt16 value, Colossal.OdinSerializer.IDataWriter writer);
```


