# Game.Prefabs.ObjectGeometryData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ObjectGeometryData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Colossal.Mathematics.Bounds3 m_Bounds;
    public Unity.Mathematics.float3 m_Size;
    public Unity.Mathematics.float3 m_Pivot;
    public Unity.Mathematics.float3 m_LegSize;
    public Unity.Mathematics.float2 m_LegOffset;
    public Game.Objects.GeometryFlags m_Flags;
    public System.Int32 m_MinLod;
    public Game.Prefabs.MeshLayer m_Layers;
    public Game.Prefabs.ObjectRequirementFlags m_SubObjectMask;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Colossal.Mathematics.Bounds3 m_Bounds`  

```csharp
public Colossal.Mathematics.Bounds3 m_Bounds;
```

- `public Unity.Mathematics.float3 m_Size`  

```csharp
public Unity.Mathematics.float3 m_Size;
```

- `public Unity.Mathematics.float3 m_Pivot`  

```csharp
public Unity.Mathematics.float3 m_Pivot;
```

- `public Unity.Mathematics.float3 m_LegSize`  

```csharp
public Unity.Mathematics.float3 m_LegSize;
```

- `public Unity.Mathematics.float2 m_LegOffset`  

```csharp
public Unity.Mathematics.float2 m_LegOffset;
```

- `public Game.Objects.GeometryFlags m_Flags`  

```csharp
public Game.Objects.GeometryFlags m_Flags;
```

- `public System.Int32 m_MinLod`  

```csharp
public System.Int32 m_MinLod;
```

- `public Game.Prefabs.MeshLayer m_Layers`  

```csharp
public Game.Prefabs.MeshLayer m_Layers;
```

- `public Game.Prefabs.ObjectRequirementFlags m_SubObjectMask`  

```csharp
public Game.Prefabs.ObjectRequirementFlags m_SubObjectMask;
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


