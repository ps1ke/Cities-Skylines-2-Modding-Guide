# Game.Simulation.WaterPipeBuildingConnection

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WaterPipeBuildingConnection : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_ProducerEdge;
    public Unity.Entities.Entity m_ConsumerEdge;

    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Entities.Entity GetConsumerNode(Unity.Entities.ComponentLookup`1[[Game.Simulation.WaterPipeEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges);
    public Unity.Entities.Entity GetProducerNode(Unity.Entities.ComponentLookup`1[[Game.Simulation.WaterPipeEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_ProducerEdge`  

```csharp
public Unity.Entities.Entity m_ProducerEdge;
```

- `public Unity.Entities.Entity m_ConsumerEdge`  

```csharp
public Unity.Entities.Entity m_ConsumerEdge;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetConsumerNode(Unity.Entities.ComponentLookup`1[[Game.Simulation.WaterPipeEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : Unity.Entities.Entity`  

```csharp
public Entity GetConsumerNode(ref ComponentLookup<WaterPipeEdge> flowEdges)
	{
		return flowEdges[m_ConsumerEdge].m_Start;
	}
```

- `public GetProducerNode(Unity.Entities.ComponentLookup`1[[Game.Simulation.WaterPipeEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : Unity.Entities.Entity`  

```csharp
public Entity GetProducerNode(ref ComponentLookup<WaterPipeEdge> flowEdges)
	{
		return flowEdges[m_ProducerEdge].m_End;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


