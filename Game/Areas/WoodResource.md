# Game.Areas.WoodResource

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct WoodResource : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Tree;

    public WoodResource(Unity.Entities.Entity tree);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Tree`  

```csharp
public Unity.Entities.Entity m_Tree;
```


## Constructors

- `public WoodResource(Unity.Entities.Entity tree)`  

```csharp
public WoodResource(Unity.Entities.Entity tree);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


