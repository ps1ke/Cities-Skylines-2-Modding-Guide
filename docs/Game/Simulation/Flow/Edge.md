# Game.Simulation.Flow.Edge

**Assembly:** `Game`  
**Namespace:** `Game.Simulation.Flow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public System.Int32 m_Capacity`  
- `public Game.Net.FlowDirection m_Direction`  
- `public System.Int32 m_FinalFlow`  
- `public System.Int32 m_TempFlow`  
- `public Game.Simulation.Flow.Identifier m_CutElementId`  

## Properties

- `public System.Int32 flow { get }`  

## Constructors

- `public Edge(System.Int32 capacity, Game.Net.FlowDirection direction = Both)`  

## Methods

- `public FinalizeTempFlow() : System.Void`  
- `public GetCapacity(System.Boolean backwards) : System.Int32`  
- `public GetFinalFlow(System.Boolean backwards) : System.Int32`  
- `public GetResidualCapacity(System.Boolean backwards) : System.Int32`  

