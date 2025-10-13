# Colossal.OdinSerializer.LayerMaskFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.LayerMask>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.LayerMask>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class LayerMaskFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.LayerMask>, Colossal.OdinSerializer.IFormatter<UnityEngine.LayerMask>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<System.Int32> IntSerializer;

    public LayerMaskFormatter();

    protected virtual System.Void Read(UnityEngine.LayerMask& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.LayerMask& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<System.Int32> IntSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Int32> IntSerializer;
```


## Constructors

- `public LayerMaskFormatter()`  

```csharp
public LayerMaskFormatter();
```


## Methods

- `protected virtual Read(UnityEngine.LayerMask& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.LayerMask& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.LayerMask& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.LayerMask& value, Colossal.OdinSerializer.IDataWriter writer);
```


