# Game.Tutorials.TutorialPolicyAdjustmentTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialPolicyAdjustmentTriggerSystem : Game.Tutorials.TutorialTriggerSystemBase
{
    private Unity.Entities.EntityQuery m_AdjustmentQuery;
    private Unity.Entities.EntityQuery m_PolicyQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;

    public TutorialPolicyAdjustmentTriggerSystem();

    private System.Boolean AnyActive(Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
    private System.Boolean Check(Game.Tutorials.PolicyAdjustmentTriggerData data, Unity.Collections.NativeArray<Game.Policies.Modify> adjustments);
    private System.Boolean FirstTimeCheck(Game.Tutorials.PolicyAdjustmentTriggerData data, Unity.Collections.NativeArray<Unity.Entities.Entity> policyEntities);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_AdjustmentQuery`  

```csharp
private Unity.Entities.EntityQuery m_AdjustmentQuery;
```

- `private Unity.Entities.EntityQuery m_PolicyQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolicyQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```


## Constructors

- `public TutorialPolicyAdjustmentTriggerSystem()`  

```csharp
public TutorialPolicyAdjustmentTriggerSystem();
```


## Methods

- `private AnyActive(Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Boolean`  

```csharp
private System.Boolean AnyActive(Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
```

- `private Check(Game.Tutorials.PolicyAdjustmentTriggerData data, Unity.Collections.NativeArray<Game.Policies.Modify> adjustments) : System.Boolean`  

```csharp
private System.Boolean Check(Game.Tutorials.PolicyAdjustmentTriggerData data, Unity.Collections.NativeArray<Game.Policies.Modify> adjustments);
```

- `private FirstTimeCheck(Game.Tutorials.PolicyAdjustmentTriggerData data, Unity.Collections.NativeArray<Unity.Entities.Entity> policyEntities) : System.Boolean`  

```csharp
private System.Boolean FirstTimeCheck(Game.Tutorials.PolicyAdjustmentTriggerData data, Unity.Collections.NativeArray<Unity.Entities.Entity> policyEntities);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


