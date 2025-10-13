# Colossal.OdinSerializer.DateTimeOffsetFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<System.DateTimeOffset>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<System.DateTimeOffset>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public sealed class DateTimeOffsetFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<System.DateTimeOffset>, Colossal.OdinSerializer.IFormatter<System.DateTimeOffset>, Colossal.OdinSerializer.IFormatter
{
    public DateTimeOffsetFormatter();

    protected virtual System.Void Read(System.DateTimeOffset& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(System.DateTimeOffset& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public DateTimeOffsetFormatter()`  

```csharp
public DateTimeOffsetFormatter();
```


## Methods

- `protected virtual Read(System.DateTimeOffset& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(System.DateTimeOffset& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(System.DateTimeOffset& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(System.DateTimeOffset& value, Colossal.OdinSerializer.IDataWriter writer);
```


