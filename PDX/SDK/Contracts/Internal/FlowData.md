# PDX.SDK.Contracts.Internal.FlowData

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Internal`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class FlowData
{
    private System.String _idCache;
    private System.Collections.Generic.List<System.String> _identifiers;
    private static System.Random random;

    public System.String Id { get; }
    public System.String ChildId { get; }

    public FlowData();
    public FlowData(System.String id);
    public FlowData(PDX.SDK.Contracts.Internal.FlowData data);
    public FlowData(PDX.SDK.Contracts.Internal.FlowData data, System.String id);

    private System.String GenerateLogId(System.Int32 size);
    public System.Void PopId();
    public System.Void PushId();
    public System.Void PushId(System.String id);
    private System.Void Rebuild();
}
```


## Fields

- `private System.String _idCache`  

```csharp
private System.String _idCache;
```

- `private System.Collections.Generic.List<System.String> _identifiers`  

```csharp
private System.Collections.Generic.List<System.String> _identifiers;
```

- `private static System.Random random`  

```csharp
private static System.Random random;
```


## Properties

- `public System.String Id { get }`  

```csharp
public System.String Id { get; }
```

- `public System.String ChildId { get }`  

```csharp
public System.String ChildId { get; }
```


## Constructors

- `public FlowData()`  

```csharp
public FlowData();
```

- `public FlowData(System.String id)`  

```csharp
public FlowData(System.String id);
```

- `public FlowData(PDX.SDK.Contracts.Internal.FlowData data)`  

```csharp
public FlowData(PDX.SDK.Contracts.Internal.FlowData data);
```

- `public FlowData(PDX.SDK.Contracts.Internal.FlowData data, System.String id)`  

```csharp
public FlowData(PDX.SDK.Contracts.Internal.FlowData data, System.String id);
```


## Methods

- `private GenerateLogId(System.Int32 size = 4) : System.String`  

```csharp
private System.String GenerateLogId(System.Int32 size);
```

- `public PopId() : System.Void`  

```csharp
public System.Void PopId();
```

- `public PushId() : System.Void`  

```csharp
public System.Void PushId();
```

- `public PushId(System.String id) : System.Void`  

```csharp
public System.Void PushId(System.String id);
```

- `private Rebuild() : System.Void`  

```csharp
private System.Void Rebuild();
```


