# Game.Prefabs.NetLaneGeometryData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct NetLaneGeometryData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float3 m_Size;
    public System.Int32 m_MinLod;
    public Game.Prefabs.MeshLayer m_GameLayers;
    public Game.Prefabs.MeshLayer m_EditorLayers;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float3 m_Size`  

```csharp
public Unity.Mathematics.float3 m_Size;
```

- `public System.Int32 m_MinLod`  

```csharp
public System.Int32 m_MinLod;
```

- `public Game.Prefabs.MeshLayer m_GameLayers`  

```csharp
public Game.Prefabs.MeshLayer m_GameLayers;
```

- `public Game.Prefabs.MeshLayer m_EditorLayers`  

```csharp
public Game.Prefabs.MeshLayer m_EditorLayers;
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


