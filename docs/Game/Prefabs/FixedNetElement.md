# Game.Prefabs.FixedNetElement

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct FixedNetElement : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Colossal.Mathematics.Bounds1 m_LengthRange;
    public Unity.Mathematics.int2 m_CountRange;
    public Game.Prefabs.CompositionFlags m_SetState;
    public Game.Prefabs.CompositionFlags m_UnsetState;
    public Game.Prefabs.FixedNetFlags m_Flags;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Colossal.Mathematics.Bounds1 m_LengthRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_LengthRange;
```

- `public Unity.Mathematics.int2 m_CountRange`  

```csharp
public Unity.Mathematics.int2 m_CountRange;
```

- `public Game.Prefabs.CompositionFlags m_SetState`  

```csharp
public Game.Prefabs.CompositionFlags m_SetState;
```

- `public Game.Prefabs.CompositionFlags m_UnsetState`  

```csharp
public Game.Prefabs.CompositionFlags m_UnsetState;
```

- `public Game.Prefabs.FixedNetFlags m_Flags`  

```csharp
public Game.Prefabs.FixedNetFlags m_Flags;
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


