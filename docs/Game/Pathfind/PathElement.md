# Game.Pathfind.PathElement

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct PathElement : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Target;
    public Unity.Mathematics.float2 m_TargetDelta;
    public Game.Pathfind.PathElementFlags m_Flags;

    public PathElement(Unity.Entities.Entity target, Unity.Mathematics.float2 targetDelta, Game.Pathfind.PathElementFlags flags);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```

- `public Unity.Mathematics.float2 m_TargetDelta`  

```csharp
public Unity.Mathematics.float2 m_TargetDelta;
```

- `public Game.Pathfind.PathElementFlags m_Flags`  

```csharp
public Game.Pathfind.PathElementFlags m_Flags;
```


## Constructors

- `public PathElement(Unity.Entities.Entity target, Unity.Mathematics.float2 targetDelta, Game.Pathfind.PathElementFlags flags = 0)`  

```csharp
public PathElement(Unity.Entities.Entity target, Unity.Mathematics.float2 targetDelta, Game.Pathfind.PathElementFlags flags);
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


