# Colossal.OdinSerializer.BaseDataReaderWriter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Fields

- `private Colossal.OdinSerializer.NodeInfo[] nodes`  
- `private System.Int32 nodesLength`  

## Properties

- `public Colossal.OdinSerializer.TwoWaySerializationBinder Binder { get; set }`  
- `public System.Boolean IsInArrayNode { get }`  
- `protected System.Int32 NodeDepth { protected get }`  
- `protected Colossal.OdinSerializer.NodeInfo[] NodesArray { protected get }`  
- `protected Colossal.OdinSerializer.NodeInfo CurrentNode { protected get }`  

## Constructors

- `protected BaseDataReaderWriter()`  

## Methods

- `protected ClearNodes() : System.Void`  
- `private ExpandNodes() : System.Void`  
- `protected PopArray() : System.Void`  
- `protected PopNode(System.String name) : System.Void`  
- `protected PushArray() : System.Void`  
- `protected PushNode(Colossal.OdinSerializer.NodeInfo node) : System.Void`  
- `protected PushNode(System.String name, System.Int32 id, System.Type type) : System.Void`  

