# Game.Prefabs.UnlockAllSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.MilestoneSystem m_MilestoneSystem`  
- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  
- `private Game.UI.InGame.UIHighlightSystem m_UIHighlightSystem`  
- `private Game.UI.InGame.SignatureBuildingUISystem m_SignatureBuildingUISystem`  
- `private Unity.Entities.EntityQuery m_LockedQuery`  
- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

## Constructors

- `public UnlockAllSystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private UnlockAllImpl() : System.Void`  

