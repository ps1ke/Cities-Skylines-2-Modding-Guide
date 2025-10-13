# Colossal.OdinSerializer.BaseDataReaderWriter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Code

```csharp
public abstract class BaseDataReaderWriter
{
    private Colossal.OdinSerializer.NodeInfo[] nodes;
    private System.Int32 nodesLength;

    public Colossal.OdinSerializer.TwoWaySerializationBinder Binder { get; set; }
    public System.Boolean IsInArrayNode { get; }
    protected System.Int32 NodeDepth { protected get; }
    protected Colossal.OdinSerializer.NodeInfo[] NodesArray { protected get; }
    protected Colossal.OdinSerializer.NodeInfo CurrentNode { protected get; }

    protected BaseDataReaderWriter();

    protected System.Void ClearNodes();
    private System.Void ExpandNodes();
    protected System.Void PopArray();
    protected System.Void PopNode(System.String name);
    protected System.Void PushArray();
    protected System.Void PushNode(Colossal.OdinSerializer.NodeInfo node);
    protected System.Void PushNode(System.String name, System.Int32 id, System.Type type);
}
```


## Fields

- `private Colossal.OdinSerializer.NodeInfo[] nodes`  

```csharp
private Colossal.OdinSerializer.NodeInfo[] nodes;
```

- `private System.Int32 nodesLength`  

```csharp
private System.Int32 nodesLength;
```


## Properties

- `public Colossal.OdinSerializer.TwoWaySerializationBinder Binder { get; set }`  

```csharp
public Colossal.OdinSerializer.TwoWaySerializationBinder Binder { get; set; }
```

- `public System.Boolean IsInArrayNode { get }`  

```csharp
public System.Boolean IsInArrayNode { get; }
```

- `protected System.Int32 NodeDepth { protected get }`  

```csharp
protected System.Int32 NodeDepth { protected get; }
```

- `protected Colossal.OdinSerializer.NodeInfo[] NodesArray { protected get }`  

```csharp
protected Colossal.OdinSerializer.NodeInfo[] NodesArray { protected get; }
```

- `protected Colossal.OdinSerializer.NodeInfo CurrentNode { protected get }`  

```csharp
protected Colossal.OdinSerializer.NodeInfo CurrentNode { protected get; }
```


## Constructors

- `protected BaseDataReaderWriter()`  

```csharp
protected BaseDataReaderWriter();
```


## Methods

- `protected ClearNodes() : System.Void`  

```csharp
protected System.Void ClearNodes();
```

- `private ExpandNodes() : System.Void`  

```csharp
private System.Void ExpandNodes();
```

- `protected PopArray() : System.Void`  

```csharp
protected System.Void PopArray();
```

- `protected PopNode(System.String name) : System.Void`  

```csharp
protected System.Void PopNode(System.String name);
```

- `protected PushArray() : System.Void`  

```csharp
protected System.Void PushArray();
```

- `protected PushNode(Colossal.OdinSerializer.NodeInfo node) : System.Void`  

```csharp
protected System.Void PushNode(Colossal.OdinSerializer.NodeInfo node);
```

- `protected PushNode(System.String name, System.Int32 id, System.Type type) : System.Void`  

```csharp
protected System.Void PushNode(System.String name, System.Int32 id, System.Type type);
```


