# Colossal.OdinSerializer.SerializationConfig

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class SerializationConfig
{
    private readonly System.Object LOCK;
    private Colossal.OdinSerializer.ISerializationPolicy serializationPolicy;
    private Colossal.OdinSerializer.DebugContext debugContext;
    public System.Boolean AllowDeserializeInvalidData;

    public Colossal.OdinSerializer.ISerializationPolicy SerializationPolicy { get; set; }
    public Colossal.OdinSerializer.DebugContext DebugContext { get; set; }

    public SerializationConfig();

    public System.Void ResetToDefault();
}
```


## Fields

- `private readonly System.Object LOCK`  

```csharp
private readonly System.Object LOCK;
```

- `private Colossal.OdinSerializer.ISerializationPolicy serializationPolicy`  

```csharp
private Colossal.OdinSerializer.ISerializationPolicy serializationPolicy;
```

- `private Colossal.OdinSerializer.DebugContext debugContext`  

```csharp
private Colossal.OdinSerializer.DebugContext debugContext;
```

- `public System.Boolean AllowDeserializeInvalidData`  

```csharp
public System.Boolean AllowDeserializeInvalidData;
```


## Properties

- `public Colossal.OdinSerializer.ISerializationPolicy SerializationPolicy { get; set }`  

```csharp
public Colossal.OdinSerializer.ISerializationPolicy SerializationPolicy { get; set; }
```

- `public Colossal.OdinSerializer.DebugContext DebugContext { get; set }`  

```csharp
public Colossal.OdinSerializer.DebugContext DebugContext { get; set; }
```


## Constructors

- `public SerializationConfig()`  

```csharp
public SerializationConfig();
```


## Methods

- `public ResetToDefault() : System.Void`  

```csharp
public System.Void ResetToDefault();
```


