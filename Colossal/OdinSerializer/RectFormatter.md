# Colossal.OdinSerializer.RectFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Rect>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.Rect>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class RectFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Rect>, Colossal.OdinSerializer.IFormatter<UnityEngine.Rect>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;

    public RectFormatter();

    protected virtual System.Void Read(UnityEngine.Rect& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.Rect& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;
```


## Constructors

- `public RectFormatter()`  

```csharp
public RectFormatter();
```


## Methods

- `protected virtual Read(UnityEngine.Rect& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.Rect& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.Rect& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.Rect& value, Colossal.OdinSerializer.IDataWriter writer);
```


