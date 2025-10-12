# Game.Simulation.MilestoneSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IMilestoneSystem`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Int32 m_LastRequired`  
- `private System.Int32 m_NextRequired`  
- `private System.Int32 m_Progress`  
- `private System.Int32 m_NextMilestone`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Common.ModificationEndBarrier m_ModificationEndBarrier`  
- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  
- `private Unity.Entities.EntityArchetype m_MilestoneReachedEventArchetype`  
- `private Unity.Entities.EntityQuery m_MilestoneLevelGroup`  
- `private Unity.Entities.EntityQuery m_XPGroup`  
- `private Unity.Entities.EntityQuery m_MilestoneGroup`  

## Properties

- `public System.Int32 currentXP { get }`  
- `public System.Int32 requiredXP { get }`  
- `public System.Int32 lastRequiredXP { get }`  
- `public System.Int32 nextRequiredXP { get }`  
- `public System.Single progress { get }`  
- `public System.Int32 nextMilestone { get }`  

## Constructors

- `public MilestoneSystem()`  

## Methods

- `private NextMilestone(System.Int32 index) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private TryGetMilestone(System.Int32 index, Unity.Entities.Entity& entity, Game.Prefabs.MilestoneData& milestone) : System.Boolean`  
- `public UnlockAllMilestones() : System.Void`  

