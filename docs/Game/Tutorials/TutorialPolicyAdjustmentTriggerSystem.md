# Game.Tutorials.TutorialPolicyAdjustmentTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_AdjustmentQuery`  
- `private Unity.Entities.EntityQuery m_PolicyQuery`  
- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

## Constructors

- `public TutorialPolicyAdjustmentTriggerSystem()`  

## Methods

- `private AnyActive(Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Boolean`  
- `private Check(Game.Tutorials.PolicyAdjustmentTriggerData data, Unity.Collections.NativeArray<Game.Policies.Modify> adjustments) : System.Boolean`  
- `private FirstTimeCheck(Game.Tutorials.PolicyAdjustmentTriggerData data, Unity.Collections.NativeArray<Unity.Entities.Entity> policyEntities) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

