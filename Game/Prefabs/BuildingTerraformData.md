# Game.Prefabs.BuildingTerraformData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct BuildingTerraformData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float3 m_FlatX0;
    public Unity.Mathematics.float3 m_FlatZ0;
    public Unity.Mathematics.float3 m_FlatX1;
    public Unity.Mathematics.float3 m_FlatZ1;
    public Unity.Mathematics.float4 m_Smooth;
    public System.Single m_HeightOffset;
    public System.Boolean m_DontRaise;
    public System.Boolean m_DontLower;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float3 m_FlatX0`  

```csharp
public Unity.Mathematics.float3 m_FlatX0;
```

- `public Unity.Mathematics.float3 m_FlatZ0`  

```csharp
public Unity.Mathematics.float3 m_FlatZ0;
```

- `public Unity.Mathematics.float3 m_FlatX1`  

```csharp
public Unity.Mathematics.float3 m_FlatX1;
```

- `public Unity.Mathematics.float3 m_FlatZ1`  

```csharp
public Unity.Mathematics.float3 m_FlatZ1;
```

- `public Unity.Mathematics.float4 m_Smooth`  

```csharp
public Unity.Mathematics.float4 m_Smooth;
```

- `public System.Single m_HeightOffset`  

```csharp
public System.Single m_HeightOffset;
```

- `public System.Boolean m_DontRaise`  

```csharp
public System.Boolean m_DontRaise;
```

- `public System.Boolean m_DontLower`  

```csharp
public System.Boolean m_DontLower;
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


