# Colossal.OdinSerializer.Vector2Formatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Vector2>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.Vector2>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class Vector2Formatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Vector2>, Colossal.OdinSerializer.IFormatter<UnityEngine.Vector2>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;

    public Vector2Formatter();

    protected virtual System.Void Read(UnityEngine.Vector2& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.Vector2& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;
```


## Constructors

- `public Vector2Formatter()`  

```csharp
public Vector2Formatter();
```


## Methods

- `protected virtual Read(UnityEngine.Vector2& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.Vector2& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.Vector2& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.Vector2& value, Colossal.OdinSerializer.IDataWriter writer);
```


