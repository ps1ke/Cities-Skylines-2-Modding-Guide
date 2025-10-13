# Colossal.OdinSerializer.TimeSpanFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<System.TimeSpan>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<System.TimeSpan>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public sealed class TimeSpanFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<System.TimeSpan>, Colossal.OdinSerializer.IFormatter<System.TimeSpan>, Colossal.OdinSerializer.IFormatter
{
    public TimeSpanFormatter();

    protected virtual System.Void Read(System.TimeSpan& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(System.TimeSpan& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public TimeSpanFormatter()`  

```csharp
public TimeSpanFormatter();
```


## Methods

- `protected virtual Read(System.TimeSpan& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(System.TimeSpan& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(System.TimeSpan& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(System.TimeSpan& value, Colossal.OdinSerializer.IDataWriter writer);
```


