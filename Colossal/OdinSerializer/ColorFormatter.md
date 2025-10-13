# Colossal.OdinSerializer.ColorFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Color>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.Color>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class ColorFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Color>, Colossal.OdinSerializer.IFormatter<UnityEngine.Color>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;

    public ColorFormatter();

    protected virtual System.Void Read(UnityEngine.Color& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.Color& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;
```


## Constructors

- `public ColorFormatter()`  

```csharp
public ColorFormatter();
```


## Methods

- `protected virtual Read(UnityEngine.Color& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.Color& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.Color& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.Color& value, Colossal.OdinSerializer.IDataWriter writer);
```


