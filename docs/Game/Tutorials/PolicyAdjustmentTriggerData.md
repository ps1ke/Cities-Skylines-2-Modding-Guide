# Game.Tutorials.PolicyAdjustmentTriggerData

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct PolicyAdjustmentTriggerData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Tutorials.PolicyAdjustmentTriggerFlags m_Flags;
    public Game.Tutorials.PolicyAdjustmentTriggerTargetFlags m_TargetFlags;

    public PolicyAdjustmentTriggerData(Game.Tutorials.PolicyAdjustmentTriggerFlags flags, Game.Tutorials.PolicyAdjustmentTriggerTargetFlags targetFlags);

}
```


## Fields

- `public Game.Tutorials.PolicyAdjustmentTriggerFlags m_Flags`  

```csharp
public Game.Tutorials.PolicyAdjustmentTriggerFlags m_Flags;
```

- `public Game.Tutorials.PolicyAdjustmentTriggerTargetFlags m_TargetFlags`  

```csharp
public Game.Tutorials.PolicyAdjustmentTriggerTargetFlags m_TargetFlags;
```


## Constructors

- `public PolicyAdjustmentTriggerData(Game.Tutorials.PolicyAdjustmentTriggerFlags flags, Game.Tutorials.PolicyAdjustmentTriggerTargetFlags targetFlags)`  

```csharp
public PolicyAdjustmentTriggerData(Game.Tutorials.PolicyAdjustmentTriggerFlags flags, Game.Tutorials.PolicyAdjustmentTriggerTargetFlags targetFlags);
```


