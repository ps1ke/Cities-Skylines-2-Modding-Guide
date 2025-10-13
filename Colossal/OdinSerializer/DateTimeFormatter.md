# Colossal.OdinSerializer.DateTimeFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<System.DateTime>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<System.DateTime>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public sealed class DateTimeFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<System.DateTime>, Colossal.OdinSerializer.IFormatter<System.DateTime>, Colossal.OdinSerializer.IFormatter
{
    public DateTimeFormatter();

    protected virtual System.Void Read(System.DateTime& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(System.DateTime& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public DateTimeFormatter()`  

```csharp
public DateTimeFormatter();
```


## Methods

- `protected virtual Read(System.DateTime& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(System.DateTime& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(System.DateTime& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(System.DateTime& value, Colossal.OdinSerializer.IDataWriter writer);
```


