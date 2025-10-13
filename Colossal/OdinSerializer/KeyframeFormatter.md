# Colossal.OdinSerializer.KeyframeFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Keyframe>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.Keyframe>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class KeyframeFormatter : Colossal.OdinSerializer.MinimalBaseFormatter<UnityEngine.Keyframe>, Colossal.OdinSerializer.IFormatter<UnityEngine.Keyframe>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;
    private static readonly Colossal.OdinSerializer.Serializer<System.Int32> IntSerializer;
    private static readonly System.Boolean Is_In_2018_1_Or_Above;
    private static Colossal.OdinSerializer.IFormatter<UnityEngine.Keyframe> Formatter;

    public KeyframeFormatter();

    protected virtual System.Void Read(UnityEngine.Keyframe& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(UnityEngine.Keyframe& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;
```

- `private static readonly Colossal.OdinSerializer.Serializer<System.Int32> IntSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Int32> IntSerializer;
```

- `private static readonly System.Boolean Is_In_2018_1_Or_Above`  

```csharp
private static readonly System.Boolean Is_In_2018_1_Or_Above;
```

- `private static Colossal.OdinSerializer.IFormatter<UnityEngine.Keyframe> Formatter`  

```csharp
private static Colossal.OdinSerializer.IFormatter<UnityEngine.Keyframe> Formatter;
```


## Constructors

- `public KeyframeFormatter()`  

```csharp
public KeyframeFormatter();
```


## Methods

- `protected virtual Read(UnityEngine.Keyframe& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(UnityEngine.Keyframe& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(UnityEngine.Keyframe& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(UnityEngine.Keyframe& value, Colossal.OdinSerializer.IDataWriter writer);
```


