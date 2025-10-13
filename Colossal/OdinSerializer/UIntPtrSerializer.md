# Colossal.OdinSerializer.UIntPtrSerializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.UIntPtr>`  

## Code

```csharp
public sealed class UIntPtrSerializer : Colossal.OdinSerializer.Serializer<System.UIntPtr>
{
    public UIntPtrSerializer();

    public virtual System.UIntPtr ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.UIntPtr value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public UIntPtrSerializer()`  

```csharp
public UIntPtrSerializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.UIntPtr`  

```csharp
public virtual System.UIntPtr ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.UIntPtr value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.UIntPtr value, Colossal.OdinSerializer.IDataWriter writer);
```


