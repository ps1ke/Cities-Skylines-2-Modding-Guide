# Colossal.OdinSerializer.CharSerializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer<System.Char>`  

## Code

```csharp
public sealed class CharSerializer : Colossal.OdinSerializer.Serializer<System.Char>
{
    public CharSerializer();

    public virtual System.Char ReadValue(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValue(System.String name, System.Char value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public CharSerializer()`  

```csharp
public CharSerializer();
```


## Methods

- `public virtual ReadValue(Colossal.OdinSerializer.IDataReader reader) : System.Char`  

```csharp
public virtual System.Char ReadValue(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValue(System.String name, System.Char value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValue(System.String name, System.Char value, Colossal.OdinSerializer.IDataWriter writer);
```


