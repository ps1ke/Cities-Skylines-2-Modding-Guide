# Colossal.OdinSerializer.TypeFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<System.Type>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<System.Type>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public sealed class TypeFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<System.Type>, Colossal.OdinSerializer.IFormatter<System.Type>, Colossal.OdinSerializer.IFormatter
{
    public TypeFormatter();

    protected virtual System.Type GetUninitializedObject();
    protected virtual System.Void Read(System.Type& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(System.Type& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public TypeFormatter()`  

```csharp
public TypeFormatter();
```


## Methods

- `protected virtual GetUninitializedObject() : System.Type`  

```csharp
protected virtual System.Type GetUninitializedObject();
```

- `protected virtual Read(System.Type& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(System.Type& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(System.Type& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(System.Type& value, Colossal.OdinSerializer.IDataWriter writer);
```


