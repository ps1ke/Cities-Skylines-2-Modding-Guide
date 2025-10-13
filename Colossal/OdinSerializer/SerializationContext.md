# Colossal.OdinSerializer.SerializationContext

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver`  

## Code

```csharp
public sealed class SerializationContext : Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver
{
    private Colossal.OdinSerializer.SerializationConfig config;
    private System.Collections.Generic.Dictionary<System.Object, System.Int32> internalReferenceIdMap;
    private System.Runtime.Serialization.StreamingContext streamingContext;
    private System.Runtime.Serialization.IFormatterConverter formatterConverter;
    private Colossal.OdinSerializer.TwoWaySerializationBinder binder;
    private Colossal.OdinSerializer.IExternalIndexReferenceResolver <IndexReferenceResolver>k__BackingField;
    private Colossal.OdinSerializer.IExternalStringReferenceResolver <StringReferenceResolver>k__BackingField;
    private Colossal.OdinSerializer.IExternalGuidReferenceResolver <GuidReferenceResolver>k__BackingField;

    public Colossal.OdinSerializer.TwoWaySerializationBinder Binder { get; set; }
    public System.Runtime.Serialization.StreamingContext StreamingContext { get; }
    public System.Runtime.Serialization.IFormatterConverter FormatterConverter { get; }
    public Colossal.OdinSerializer.IExternalIndexReferenceResolver IndexReferenceResolver { get; set; }
    public Colossal.OdinSerializer.IExternalStringReferenceResolver StringReferenceResolver { get; set; }
    public Colossal.OdinSerializer.IExternalGuidReferenceResolver GuidReferenceResolver { get; set; }
    public Colossal.OdinSerializer.SerializationConfig Config { get; set; }

    public SerializationContext();
    public SerializationContext(System.Runtime.Serialization.StreamingContext context);
    public SerializationContext(System.Runtime.Serialization.FormatterConverter formatterConverter);
    public SerializationContext(System.Runtime.Serialization.StreamingContext context, System.Runtime.Serialization.FormatterConverter formatterConverter);

    private System.Void Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnClaimed();
    private System.Void Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnFreed();
    public System.Void ResetInternalReferences();
    public System.Void ResetToDefault();
    public System.Boolean TryGetInternalReferenceId(System.Object reference, System.Int32& id);
    public System.Boolean TryRegisterExternalReference(System.Object obj, System.Int32& index);
    public System.Boolean TryRegisterExternalReference(System.Object obj, System.Guid& guid);
    public System.Boolean TryRegisterExternalReference(System.Object obj, System.String& id);
    public System.Boolean TryRegisterInternalReference(System.Object reference, System.Int32& id);
}
```


## Fields

- `private Colossal.OdinSerializer.SerializationConfig config`  

```csharp
private Colossal.OdinSerializer.SerializationConfig config;
```

- `private System.Collections.Generic.Dictionary<System.Object, System.Int32> internalReferenceIdMap`  

```csharp
private System.Collections.Generic.Dictionary<System.Object, System.Int32> internalReferenceIdMap;
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

- `private Colossal.OdinSerializer.IExternalIndexReferenceResolver <IndexReferenceResolver>k__BackingField`  

```csharp
private Colossal.OdinSerializer.IExternalIndexReferenceResolver <IndexReferenceResolver>k__BackingField;
```

- `private Colossal.OdinSerializer.IExternalStringReferenceResolver <StringReferenceResolver>k__BackingField`  

```csharp
private Colossal.OdinSerializer.IExternalStringReferenceResolver <StringReferenceResolver>k__BackingField;
```

- `private Colossal.OdinSerializer.IExternalGuidReferenceResolver <GuidReferenceResolver>k__BackingField`  

```csharp
private Colossal.OdinSerializer.IExternalGuidReferenceResolver <GuidReferenceResolver>k__BackingField;
```


## Properties

- `public Colossal.OdinSerializer.TwoWaySerializationBinder Binder { get; set }`  

```csharp
public Colossal.OdinSerializer.TwoWaySerializationBinder Binder { get; set; }
```

- `public System.Runtime.Serialization.StreamingContext StreamingContext { get }`  

```csharp
public System.Runtime.Serialization.StreamingContext StreamingContext { get; }
```

- `public System.Runtime.Serialization.IFormatterConverter FormatterConverter { get }`  

```csharp
public System.Runtime.Serialization.IFormatterConverter FormatterConverter { get; }
```

- `public Colossal.OdinSerializer.IExternalIndexReferenceResolver IndexReferenceResolver { get; set }`  

```csharp
public Colossal.OdinSerializer.IExternalIndexReferenceResolver IndexReferenceResolver { get; set; }
```

- `public Colossal.OdinSerializer.IExternalStringReferenceResolver StringReferenceResolver { get; set }`  

```csharp
public Colossal.OdinSerializer.IExternalStringReferenceResolver StringReferenceResolver { get; set; }
```

- `public Colossal.OdinSerializer.IExternalGuidReferenceResolver GuidReferenceResolver { get; set }`  

```csharp
public Colossal.OdinSerializer.IExternalGuidReferenceResolver GuidReferenceResolver { get; set; }
```

- `public Colossal.OdinSerializer.SerializationConfig Config { get; set }`  

```csharp
public Colossal.OdinSerializer.SerializationConfig Config { get; set; }
```


## Constructors

- `public SerializationContext()`  

```csharp
public SerializationContext();
```

- `public SerializationContext(System.Runtime.Serialization.StreamingContext context)`  

```csharp
public SerializationContext(System.Runtime.Serialization.StreamingContext context);
```

- `public SerializationContext(System.Runtime.Serialization.FormatterConverter formatterConverter)`  

```csharp
public SerializationContext(System.Runtime.Serialization.FormatterConverter formatterConverter);
```

- `public SerializationContext(System.Runtime.Serialization.StreamingContext context, System.Runtime.Serialization.FormatterConverter formatterConverter)`  

```csharp
public SerializationContext(System.Runtime.Serialization.StreamingContext context, System.Runtime.Serialization.FormatterConverter formatterConverter);
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

- `public ResetInternalReferences() : System.Void`  

```csharp
public System.Void ResetInternalReferences();
```

- `public ResetToDefault() : System.Void`  

```csharp
public System.Void ResetToDefault();
```

- `public TryGetInternalReferenceId(System.Object reference, System.Int32& id) : System.Boolean`  

```csharp
public System.Boolean TryGetInternalReferenceId(System.Object reference, System.Int32& id);
```

- `public TryRegisterExternalReference(System.Object obj, System.Int32& index) : System.Boolean`  

```csharp
public System.Boolean TryRegisterExternalReference(System.Object obj, System.Int32& index);
```

- `public TryRegisterExternalReference(System.Object obj, System.Guid& guid) : System.Boolean`  

```csharp
public System.Boolean TryRegisterExternalReference(System.Object obj, System.Guid& guid);
```

- `public TryRegisterExternalReference(System.Object obj, System.String& id) : System.Boolean`  

```csharp
public System.Boolean TryRegisterExternalReference(System.Object obj, System.String& id);
```

- `public TryRegisterInternalReference(System.Object reference, System.Int32& id) : System.Boolean`  

```csharp
public System.Boolean TryRegisterInternalReference(System.Object reference, System.Int32& id);
```


