# Colossal.OdinSerializer.Vector2IntFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Vector2Int>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.Vector2Int>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class Vector2IntFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Vector2Int>, Colossal.OdinSerializer.IFormatter<UnityEngine.Vector2Int>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<System.Int32> Serializer;

    public Vector2IntFormatter();

    protected virtual System.Void Read(UnityEngine.Vector2Int& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.Vector2Int& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<System.Int32> Serializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Int32> Serializer;
```


## Constructors

- `public Vector2IntFormatter()`  

```csharp
public Vector2IntFormatter();
```


## Methods

- `protected virtual Read(UnityEngine.Vector2Int& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.Vector2Int& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.Vector2Int& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.Vector2Int& value, Colossal.OdinSerializer.IDataWriter writer);
```


