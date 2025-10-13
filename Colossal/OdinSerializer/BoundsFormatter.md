# Colossal.OdinSerializer.BoundsFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Bounds>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.Bounds>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class BoundsFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Bounds>, Colossal.OdinSerializer.IFormatter<UnityEngine.Bounds>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.Vector3> Vector3Serializer;

    public BoundsFormatter();

    protected virtual System.Void Read(UnityEngine.Bounds& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.Bounds& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.Vector3> Vector3Serializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.Vector3> Vector3Serializer;
```


## Constructors

- `public BoundsFormatter()`  

```csharp
public BoundsFormatter();
```


## Methods

- `protected virtual Read(UnityEngine.Bounds& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.Bounds& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.Bounds& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.Bounds& value, Colossal.OdinSerializer.IDataWriter writer);
```


