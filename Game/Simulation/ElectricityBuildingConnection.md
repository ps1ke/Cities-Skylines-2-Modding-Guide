# Game.Simulation.ElectricityBuildingConnection

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ElectricityBuildingConnection : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_TransformerNode;
    public Unity.Entities.Entity m_ProducerEdge;
    public Unity.Entities.Entity m_ConsumerEdge;
    public Unity.Entities.Entity m_ChargeEdge;
    public Unity.Entities.Entity m_DischargeEdge;

    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Entities.Entity GetChargeNode(Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges);
    public Unity.Entities.Entity GetConsumerNode(Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges);
    public Unity.Entities.Entity GetDischargeNode(Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges);
    public Unity.Entities.Entity GetProducerNode(Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TransformerNode`  

```csharp
public Unity.Entities.Entity m_TransformerNode;
```

- `public Unity.Entities.Entity m_ProducerEdge`  

```csharp
public Unity.Entities.Entity m_ProducerEdge;
```

- `public Unity.Entities.Entity m_ConsumerEdge`  

```csharp
public Unity.Entities.Entity m_ConsumerEdge;
```

- `public Unity.Entities.Entity m_ChargeEdge`  

```csharp
public Unity.Entities.Entity m_ChargeEdge;
```

- `public Unity.Entities.Entity m_DischargeEdge`  

```csharp
public Unity.Entities.Entity m_DischargeEdge;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetChargeNode(Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : Unity.Entities.Entity`  

```csharp
public Entity GetChargeNode(ref ComponentLookup<ElectricityFlowEdge> flowEdges)
	{
		return flowEdges[m_ChargeEdge].m_Start;
	}
```

- `public GetConsumerNode(Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : Unity.Entities.Entity`  

```csharp
public Entity GetConsumerNode(ref ComponentLookup<ElectricityFlowEdge> flowEdges)
	{
		return flowEdges[m_ConsumerEdge].m_Start;
	}
```

- `public GetDischargeNode(Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : Unity.Entities.Entity`  

```csharp
public Entity GetDischargeNode(ref ComponentLookup<ElectricityFlowEdge> flowEdges)
	{
		return flowEdges[m_DischargeEdge].m_End;
	}
```

- `public GetProducerNode(Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : Unity.Entities.Entity`  

```csharp
public Entity GetProducerNode(ref ComponentLookup<ElectricityFlowEdge> flowEdges)
	{
		return flowEdges[m_ProducerEdge].m_End;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


