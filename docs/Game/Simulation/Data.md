# Game.Simulation.WaterPipeFlowJob+Data

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Fields

- `public Unity.Collections.NativeReference<Game.Simulation.WaterPipeFlowJob+State> m_State`  
- `public Unity.Collections.NativeList<Game.Simulation.Flow.Node> m_Nodes`  
- `public Unity.Collections.NativeList<Game.Simulation.Flow.Edge> m_Edges`  
- `public Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> m_MaxFlowState`  
- `public Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> m_LayerStates`  
- `public Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> m_LayerElements`  
- `public Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> m_LayerElementRefs`  
- `public Unity.Collections.NativeReference<Game.Simulation.Flow.FluidFlowSolverState> m_FluidFlowState`  

## Constructors

- `public Data(System.Int32 lastTotalSteps, Unity.Collections.Allocator allocator)`  

## Methods

- `public Dispose() : System.Void`  

