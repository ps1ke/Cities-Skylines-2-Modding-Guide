# Colossal.OdinSerializer.DeserializationContext

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver`  

## Code

```csharp
public sealed class DeserializationContext : Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver
{
    private Colossal.OdinSerializer.SerializationConfig config;
    private System.Collections.Generic.Dictionary<System.Int32, System.Object> internalIdReferenceMap;
    private System.Runtime.Serialization.StreamingContext streamingContext;
    private System.Runtime.Serialization.IFormatterConverter formatterConverter;
    private Colossal.OdinSerializer.TwoWaySerializationBinder binder;
    private Colossal.OdinSerializer.IExternalStringReferenceResolver <StringReferenceResolver>k__BackingField;
    private Colossal.OdinSerializer.IExternalGuidReferenceResolver <GuidReferenceResolver>k__BackingField;
    private Colossal.OdinSerializer.IExternalIndexReferenceResolver <IndexReferenceResolver>k__BackingField;

    public Colossal.OdinSerializer.TwoWaySerializationBinder Binder { get; set; }
    public Colossal.OdinSerializer.IExternalStringReferenceResolver StringReferenceResolver { get; set; }
    public Colossal.OdinSerializer.IExternalGuidReferenceResolver GuidReferenceResolver { get; set; }
    public Colossal.OdinSerializer.IExternalIndexReferenceResolver IndexReferenceResolver { get; set; }
    public System.Runtime.Serialization.StreamingContext StreamingContext { get; }
    public System.Runtime.Serialization.IFormatterConverter FormatterConverter { get; }
    public Colossal.OdinSerializer.SerializationConfig Config { get; set; }

    public DeserializationContext();
    public DeserializationContext(System.Runtime.Serialization.StreamingContext context);
    public DeserializationContext(System.Runtime.Serialization.FormatterConverter formatterConverter);
    public DeserializationContext(System.Runtime.Serialization.StreamingContext context, System.Runtime.Serialization.FormatterConverter formatterConverter);

    private System.Void Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnClaimed();
    private System.Void Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnFreed();
    public System.Object GetExternalObject(System.Int32 index);
    public System.Object GetExternalObject(System.Guid guid);
    public System.Object GetExternalObject(System.String id, System.Type serializedType);
    public System.Object GetInternalReference(System.Int32 id);
    public System.Void RegisterInternalReference(System.Int32 id, System.Object reference);
    public System.Void Reset();
}
```


## Fields

- `private Colossal.OdinSerializer.SerializationConfig config`  

```csharp
private Colossal.OdinSerializer.SerializationConfig config;
```

- `private System.Collections.Generic.Dictionary<System.Int32, System.Object> internalIdReferenceMap`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, System.Object> internalIdReferenceMap;
```

- `private System.Runtime.Serialization.StreamingContext streamingContext`  

```csharp
private System.Runtime.Serialization.StreamingContext streamingContext;
```

- `private System.Runtime.Serialization.IFormatterConverter formatterConverter`  

```csharp
private System.Runtime.Serialization.IFormatterConverter formatterConverter;
```

- `private Colossal.OdinSerializer.TwoWaySerializationBinder binder`  

```csharp
private Colossal.OdinSerializer.TwoWaySerializationBinder binder;
```

- `private Colossal.OdinSerializer.IExternalStringReferenceResolver <StringReferenceResolver>k__BackingField`  

```csharp
private Colossal.OdinSerializer.IExternalStringReferenceResolver <StringReferenceResolver>k__BackingField;
```

- `private Colossal.OdinSerializer.IExternalGuidReferenceResolver <GuidReferenceResolver>k__BackingField`  

```csharp
private Colossal.OdinSerializer.IExternalGuidReferenceResolver <GuidReferenceResolver>k__BackingField;
```

- `private Colossal.OdinSerializer.IExternalIndexReferenceResolver <IndexReferenceResolver>k__BackingField`  

```csharp
private Colossal.OdinSerializer.IExternalIndexReferenceResolver <IndexReferenceResolver>k__BackingField;
```


## Properties

- `public Colossal.OdinSerializer.TwoWaySerializationBinder Binder { get; set }`  

```csharp
public Colossal.OdinSerializer.TwoWaySerializationBinder Binder { get; set; }
```

- `public Colossal.OdinSerializer.IExternalStringReferenceResolver StringReferenceResolver { get; set }`  

```csharp
public Colossal.OdinSerializer.IExternalStringReferenceResolver StringReferenceResolver { get; set; }
```

- `public Colossal.OdinSerializer.IExternalGuidReferenceResolver GuidReferenceResolver { get; set }`  

```csharp
public Colossal.OdinSerializer.IExternalGuidReferenceResolver GuidReferenceResolver { get; set; }
```

- `public Colossal.OdinSerializer.IExternalIndexReferenceResolver IndexReferenceResolver { get; set }`  

```csharp
public Colossal.OdinSerializer.IExternalIndexReferenceResolver IndexReferenceResolver { get; set; }
```

- `public System.Runtime.Serialization.StreamingContext StreamingContext { get }`  

```csharp
public System.Runtime.Serialization.StreamingContext StreamingContext { get; }
```

- `public System.Runtime.Serialization.IFormatterConverter FormatterConverter { get }`  

```csharp
public System.Runtime.Serialization.IFormatterConverter FormatterConverter { get; }
```

- `public Colossal.OdinSerializer.SerializationConfig Config { get; set }`  

```csharp
public Colossal.OdinSerializer.SerializationConfig Config { get; set; }
```


## Constructors

- `public DeserializationContext()`  

```csharp
public DeserializationContext();
```

- `public DeserializationContext(System.Runtime.Serialization.StreamingContext context)`  

```csharp
public DeserializationContext(System.Runtime.Serialization.StreamingContext context);
```

- `public DeserializationContext(System.Runtime.Serialization.FormatterConverter formatterConverter)`  

```csharp
public DeserializationContext(System.Runtime.Serialization.FormatterConverter formatterConverter);
```

- `public DeserializationContext(System.Runtime.Serialization.StreamingContext context, System.Runtime.Serialization.FormatterConverter formatterConverter)`  

```csharp
public DeserializationContext(System.Runtime.Serialization.StreamingContext context, System.Runtime.Serialization.FormatterConverter formatterConverter);
```


## Methods

- `private Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnClaimed() : System.Void`  

```csharp
private System.Void Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnClaimed();
```

- `private Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnFreed() : System.Void`  

```csharp
private System.Void Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnFreed();
```

- `public GetExternalObject(System.Int32 index) : System.Object`  

```csharp
public System.Object GetExternalObject(System.Int32 index);
```

- `public GetExternalObject(System.Guid guid) : System.Object`  

```csharp
public System.Object GetExternalObject(System.Guid guid);
```

- `public GetExternalObject(System.String id, System.Type serializedType = null) : System.Object`  

```csharp
public System.Object GetExternalObject(System.String id, System.Type serializedType);
```

- `public GetInternalReference(System.Int32 id) : System.Object`  

```csharp
public System.Object GetInternalReference(System.Int32 id);
```

- `public RegisterInternalReference(System.Int32 id, System.Object reference) : System.Void`  

```csharp
public System.Void RegisterInternalReference(System.Int32 id, System.Object reference);
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```


