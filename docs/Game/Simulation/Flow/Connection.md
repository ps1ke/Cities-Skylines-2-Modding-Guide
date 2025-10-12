# Game.Simulation.Flow.Connection

**Assembly:** `Game`  
**Namespace:** `Game.Simulation.Flow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public System.Int32 m_StartNode`  
- `public System.Int32 m_EndNode`  
- `public System.Int32 m_Edge`  
- `public System.Boolean m_Backwards`  

## Methods

- `public GetIncomingCapacity(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges) : System.Int32`  
- `public GetIncomingFinalFlow(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges) : System.Int32`  
- `public GetIncomingResidualCapacity(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges) : System.Int32`  
- `public GetOutgoingCapacity(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges) : System.Int32`  
- `public GetOutgoingFinalFlow(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges) : System.Int32`  
- `public GetOutgoingResidualCapacity(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges) : System.Int32`  
- `public Reverse() : Game.Simulation.Flow.Connection`  

