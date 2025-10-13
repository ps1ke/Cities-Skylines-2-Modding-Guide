# Colossal.OdinSerializer.AnySerializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer`  

## Code

```csharp
public sealed class AnySerializer : Colossal.OdinSerializer.Serializer
{
    private readonly System.Type SerializedType;
    private readonly System.Boolean IsEnum;
    private readonly System.Boolean IsValueType;
    private readonly System.Boolean MayBeBoxedValueType;
    private readonly System.Boolean IsAbstract;
    private readonly System.Boolean IsNullable;
    private readonly System.Boolean AllowDeserializeInvalidData;
    private Colossal.OdinSerializer.IFormatter UnityPolicyFormatter;
    private Colossal.OdinSerializer.IFormatter StrictPolicyFormatter;
    private Colossal.OdinSerializer.IFormatter EverythingPolicyFormatter;
    private readonly System.Collections.Generic.Dictionary<Colossal.OdinSerializer.ISerializationPolicy, Colossal.OdinSerializer.IFormatter> FormattersByPolicy;
    private readonly System.Object FormattersByPolicy_LOCK;
    private static readonly Colossal.OdinSerializer.ISerializationPolicy UnityPolicy;
    private static readonly Colossal.OdinSerializer.ISerializationPolicy StrictPolicy;
    private static readonly Colossal.OdinSerializer.ISerializationPolicy EverythingPolicy;

    public AnySerializer(System.Type serializedType);

    private Colossal.OdinSerializer.IFormatter GetBaseFormatter(Colossal.OdinSerializer.ISerializationPolicy serializationPolicy);
    public virtual System.Object ReadValueWeak(Colossal.OdinSerializer.IDataReader reader);
    public virtual System.Void WriteValueWeak(System.String name, System.Object value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private readonly System.Type SerializedType`  

```csharp
private readonly System.Type SerializedType;
```

- `private readonly System.Boolean IsEnum`  

```csharp
private readonly System.Boolean IsEnum;
```

- `private readonly System.Boolean IsValueType`  

```csharp
private readonly System.Boolean IsValueType;
```

- `private readonly System.Boolean MayBeBoxedValueType`  

```csharp
private readonly System.Boolean MayBeBoxedValueType;
```

- `private readonly System.Boolean IsAbstract`  

```csharp
private readonly System.Boolean IsAbstract;
```

- `private readonly System.Boolean IsNullable`  

```csharp
private readonly System.Boolean IsNullable;
```

- `private readonly System.Boolean AllowDeserializeInvalidData`  

```csharp
private readonly System.Boolean AllowDeserializeInvalidData;
```

- `private Colossal.OdinSerializer.IFormatter UnityPolicyFormatter`  

```csharp
private Colossal.OdinSerializer.IFormatter UnityPolicyFormatter;
```

- `private Colossal.OdinSerializer.IFormatter StrictPolicyFormatter`  

```csharp
private Colossal.OdinSerializer.IFormatter StrictPolicyFormatter;
```

- `private Colossal.OdinSerializer.IFormatter EverythingPolicyFormatter`  

```csharp
private Colossal.OdinSerializer.IFormatter EverythingPolicyFormatter;
```

- `private readonly System.Collections.Generic.Dictionary<Colossal.OdinSerializer.ISerializationPolicy, Colossal.OdinSerializer.IFormatter> FormattersByPolicy`  

```csharp
private readonly System.Collections.Generic.Dictionary<Colossal.OdinSerializer.ISerializationPolicy, Colossal.OdinSerializer.IFormatter> FormattersByPolicy;
```

- `private readonly System.Object FormattersByPolicy_LOCK`  

```csharp
private readonly System.Object FormattersByPolicy_LOCK;
```

- `private static readonly Colossal.OdinSerializer.ISerializationPolicy UnityPolicy`  

```csharp
private static readonly Colossal.OdinSerializer.ISerializationPolicy UnityPolicy;
```

- `private static readonly Colossal.OdinSerializer.ISerializationPolicy StrictPolicy`  

```csharp
private static readonly Colossal.OdinSerializer.ISerializationPolicy StrictPolicy;
```

- `private static readonly Colossal.OdinSerializer.ISerializationPolicy EverythingPolicy`  

```csharp
private static readonly Colossal.OdinSerializer.ISerializationPolicy EverythingPolicy;
```


## Constructors

- `public AnySerializer(System.Type serializedType)`  

```csharp
public AnySerializer(System.Type serializedType);
```


## Methods

- `private GetBaseFormatter(Colossal.OdinSerializer.ISerializationPolicy serializationPolicy) : Colossal.OdinSerializer.IFormatter`  

```csharp
private Colossal.OdinSerializer.IFormatter GetBaseFormatter(Colossal.OdinSerializer.ISerializationPolicy serializationPolicy);
```

- `public virtual ReadValueWeak(Colossal.OdinSerializer.IDataReader reader) : System.Object`  

```csharp
public virtual System.Object ReadValueWeak(Colossal.OdinSerializer.IDataReader reader);
```

- `public virtual WriteValueWeak(System.String name, System.Object value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public virtual System.Void WriteValueWeak(System.String name, System.Object value, Colossal.OdinSerializer.IDataWriter writer);
```


