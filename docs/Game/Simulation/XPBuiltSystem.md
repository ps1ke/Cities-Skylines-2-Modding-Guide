# Game.Simulation.XPBuiltSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_BuiltGroup`  
- `private Unity.Entities.EntityQuery m_ElectricityGroup`  
- `private Game.Simulation.XPSystem m_XPSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Common.ModificationEndBarrier m_ModificationEndBarrier`  
- `private Game.Simulation.XPBuiltSystem+TypeHandle __TypeHandle`  
- `private static readonly System.Int32 kElectricityGridXPBonus`  

## Constructors

- `public XPBuiltSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.XPBuiltSystem+XPBuiltJob`  
- `Game.Simulation.XPBuiltSystem+XPElectricityJob`  
- `Game.Simulation.XPBuiltSystem+TypeHandle`  

