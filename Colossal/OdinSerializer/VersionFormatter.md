# Colossal.OdinSerializer.VersionFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<System.Version>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<System.Version>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public sealed class VersionFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<System.Version>, Colossal.OdinSerializer.IFormatter<System.Version>, Colossal.OdinSerializer.IFormatter
{
    public VersionFormatter();

    protected virtual System.Version GetUninitializedObject();
    protected virtual System.Void Read(System.Version& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(System.Version& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Constructors

- `public VersionFormatter()`  

```csharp
public VersionFormatter();
```


## Methods

- `protected virtual GetUninitializedObject() : System.Version`  

```csharp
protected virtual System.Version GetUninitializedObject();
```

- `protected virtual Read(System.Version& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(System.Version& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(System.Version& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(System.Version& value, Colossal.OdinSerializer.IDataWriter writer);
```


