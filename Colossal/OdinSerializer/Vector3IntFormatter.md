# Colossal.OdinSerializer.Vector3IntFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Vector3Int>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.Vector3Int>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class Vector3IntFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Vector3Int>, Colossal.OdinSerializer.IFormatter<UnityEngine.Vector3Int>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<System.Int32> Serializer;

    public Vector3IntFormatter();

    protected virtual System.Void Read(UnityEngine.Vector3Int& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.Vector3Int& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<System.Int32> Serializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Int32> Serializer;
```


## Constructors

- `public Vector3IntFormatter()`  

```csharp
public Vector3IntFormatter();
```


## Methods

- `protected virtual Read(UnityEngine.Vector3Int& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.Vector3Int& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.Vector3Int& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.Vector3Int& value, Colossal.OdinSerializer.IDataWriter writer);
```


