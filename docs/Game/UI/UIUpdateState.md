# Game.UI.UIUpdateState

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private readonly Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private readonly System.UInt32 m_UpdateInterval`  
- `private System.Boolean m_ForceUpdate`  
- `private System.UInt32 m_LastTickIndex`  

## Constructors

- `private UIUpdateState(Unity.Entities.World world, System.Int32 updateInterval)`  

## Methods

- `public Advance() : System.Boolean`  
- `public static Create(Unity.Entities.World world, System.Int32 updateInterval) : Game.UI.UIUpdateState`  
- `public ForceUpdate() : System.Void`  

