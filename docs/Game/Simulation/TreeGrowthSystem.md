# Game.Simulation.TreeGrowthSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_TreeQuery`  
- `private Game.Simulation.TreeGrowthSystem+TypeHandle __TypeHandle`  
- `public static const System.Int32 UPDATES_PER_DAY`  
- `public static const System.Int32 TICK_SPEED_CHILD`  
- `public static const System.Int32 TICK_SPEED_TEEN`  
- `public static const System.Int32 TICK_SPEED_ADULT`  
- `public static const System.Int32 TICK_SPEED_ELDERLY`  
- `public static const System.Int32 TICK_SPEED_DEAD`  

## Constructors

- `public TreeGrowthSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TreeGrowthSystem+TreeGrowthJob`  
- `Game.Simulation.TreeGrowthSystem+TypeHandle`  

