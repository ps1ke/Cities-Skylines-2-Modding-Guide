# Colossal.OdinSerializer.IntPtrSerializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.IntPtr>`  

## Code

```csharp
public sealed class IntPtrSerializer : Colossal.OdinSerializer.Serializer<System.IntPtr>
{
    public IntPtrSerializer();

    public virtual System.IntPtr ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.IntPtr value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public IntPtrSerializer()`  

```csharp
public IntPtrSerializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.IntPtr`  

```csharp
public virtual System.IntPtr ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.IntPtr value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.IntPtr value, Colossal.OdinSerializer.IDataWriter writer);
```


