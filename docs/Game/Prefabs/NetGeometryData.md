# Game.Prefabs.NetGeometryData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct NetGeometryData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.EntityArchetype m_NodeCompositionArchetype;
    public Unity.Entities.EntityArchetype m_EdgeCompositionArchetype;
    public Unity.Entities.Entity m_AggregateType;
    public Unity.Entities.Entity m_StyleType;
    public Colossal.Mathematics.Bounds1 m_DefaultHeightRange;
    public Colossal.Mathematics.Bounds1 m_ElevatedHeightRange;
    public Colossal.Mathematics.Bounds1 m_DefaultSurfaceHeight;
    public Colossal.Mathematics.Bounds1 m_EdgeLengthRange;
    public Game.Net.Layer m_MergeLayers;
    public Game.Net.Layer m_IntersectLayers;
    public Game.Net.GeometryFlags m_Flags;
    public System.Single m_DefaultWidth;
    public System.Single m_ElevatedWidth;
    public System.Single m_ElevatedLength;
    public System.Single m_MinNodeOffset;
    public System.Single m_ElevationLimit;
    public System.Single m_MaxSlopeSteepness;
    public System.Single m_Hanging;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.EntityArchetype m_NodeCompositionArchetype`  

```csharp
public Unity.Entities.EntityArchetype m_NodeCompositionArchetype;
```

- `public Unity.Entities.EntityArchetype m_EdgeCompositionArchetype`  

```csharp
public Unity.Entities.EntityArchetype m_EdgeCompositionArchetype;
```

- `public Unity.Entities.Entity m_AggregateType`  

```csharp
public Unity.Entities.Entity m_AggregateType;
```

- `public Unity.Entities.Entity m_StyleType`  

```csharp
public Unity.Entities.Entity m_StyleType;
```

- `public Colossal.Mathematics.Bounds1 m_DefaultHeightRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_DefaultHeightRange;
```

- `public Colossal.Mathematics.Bounds1 m_ElevatedHeightRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_ElevatedHeightRange;
```

- `public Colossal.Mathematics.Bounds1 m_DefaultSurfaceHeight`  

```csharp
public Colossal.Mathematics.Bounds1 m_DefaultSurfaceHeight;
```

- `public Colossal.Mathematics.Bounds1 m_EdgeLengthRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_EdgeLengthRange;
```

- `public Game.Net.Layer m_MergeLayers`  

```csharp
public Game.Net.Layer m_MergeLayers;
```

- `public Game.Net.Layer m_IntersectLayers`  

```csharp
public Game.Net.Layer m_IntersectLayers;
```

- `public Game.Net.GeometryFlags m_Flags`  

```csharp
public Game.Net.GeometryFlags m_Flags;
```

- `public System.Single m_DefaultWidth`  

```csharp
public System.Single m_DefaultWidth;
```

- `public System.Single m_ElevatedWidth`  

```csharp
public System.Single m_ElevatedWidth;
```

- `public System.Single m_ElevatedLength`  

```csharp
public System.Single m_ElevatedLength;
```

- `public System.Single m_MinNodeOffset`  

```csharp
public System.Single m_MinNodeOffset;
```

- `public System.Single m_ElevationLimit`  

```csharp
public System.Single m_ElevationLimit;
```

- `public System.Single m_MaxSlopeSteepness`  

```csharp
public System.Single m_MaxSlopeSteepness;
```

- `public System.Single m_Hanging`  

```csharp
public System.Single m_Hanging;
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


