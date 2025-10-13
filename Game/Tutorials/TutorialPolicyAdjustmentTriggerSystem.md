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
[Preserve]
	public TutorialPolicyAdjustmentTriggerSystem()
	{
	}
```


## Methods

- `private AnyActive(Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Boolean`  

```csharp
private bool AnyActive(DynamicBuffer<Policy> policies)
	{
		for (int i = 0; i < policies.Length; i++)
		{
			if ((policies[i].m_Flags & PolicyFlags.Active) != 0)
			{
				return true;
			}
		}
		return false;
	}
```

- `private Check(Game.Tutorials.PolicyAdjustmentTriggerData data, Unity.Collections.NativeArray<Game.Policies.Modify> adjustments) : System.Boolean`  

```csharp
private bool Check(PolicyAdjustmentTriggerData data, NativeArray<Modify> adjustments)
	{
		for (int i = 0; i < adjustments.Length; i++)
		{
			if ((data.m_TargetFlags & PolicyAdjustmentTriggerTargetFlags.District) != 0 && base.EntityManager.HasComponent<District>(adjustments[i].m_Entity) && (adjustments[i].m_Flags & PolicyFlags.Active) != 0 && (data.m_Flags & PolicyAdjustmentTriggerFlags.Activated) != 0)
			{
				return true;
			}
		}
		return false;
	}
```

- `private FirstTimeCheck(Game.Tutorials.PolicyAdjustmentTriggerData data, Unity.Collections.NativeArray<Unity.Entities.Entity> policyEntities) : System.Boolean`  

```csharp
private bool FirstTimeCheck(PolicyAdjustmentTriggerData data, NativeArray<Entity> policyEntities)
	{
		for (int i = 0; i < policyEntities.Length; i++)
		{
			DynamicBuffer<Policy> buffer = base.EntityManager.GetBuffer<Policy>(policyEntities[i], isReadOnly: true);
			if ((data.m_TargetFlags & PolicyAdjustmentTriggerTargetFlags.District) != 0 && base.EntityManager.HasComponent<District>(policyEntities[i]) && AnyActive(buffer) && (data.m_Flags & PolicyAdjustmentTriggerFlags.Activated) != 0)
			{
				return true;
			}
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ActiveTriggerQuery = GetEntityQuery(ComponentType.ReadOnly<PolicyAdjustmentTriggerData>(), ComponentType.ReadOnly<TriggerActive>(), ComponentType.Exclude<TriggerCompleted>());
		m_PolicyQuery = GetEntityQuery(ComponentType.ReadOnly<Policy>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_AdjustmentQuery = GetEntityQuery(ComponentType.ReadOnly<Event>(), ComponentType.ReadOnly<Modify>());
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<Unlock>());
		RequireForUpdate(m_ActiveTriggerQuery);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		if (base.triggersChanged && !m_PolicyQuery.IsEmptyIgnoreFilter)
		{
			EntityCommandBuffer commandBuffer = m_BarrierSystem.CreateCommandBuffer();
			NativeArray<Entity> policyEntities = m_PolicyQuery.ToEntityArray(Allocator.TempJob);
			NativeArray<PolicyAdjustmentTriggerData> nativeArray = m_ActiveTriggerQuery.ToComponentDataArray<PolicyAdjustmentTriggerData>(Allocator.TempJob);
			NativeArray<Entity> nativeArray2 = m_ActiveTriggerQuery.ToEntityArray(Allocator.TempJob);
			for (int i = 0; i < nativeArray2.Length; i++)
			{
				if (FirstTimeCheck(nativeArray[i], policyEntities))
				{
					commandBuffer.AddComponent<TriggerPreCompleted>(nativeArray2[i]);
					TutorialSystem.ManualUnlock(nativeArray2[i], m_UnlockEventArchetype, base.EntityManager, commandBuffer);
				}
			}
			nativeArray.Dispose();
			nativeArray2.Dispose();
			policyEntities.Dispose();
		}
		if (m_AdjustmentQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		EntityCommandBuffer commandBuffer2 = m_BarrierSystem.CreateCommandBuffer();
		NativeArray<PolicyAdjustmentTriggerData> nativeArray3 = m_ActiveTriggerQuery.ToComponentDataArray<PolicyAdjustmentTriggerData>(Allocator.TempJob);
		NativeArray<Entity> nativeArray4 = m_ActiveTriggerQuery.ToEntityArray(Allocator.TempJob);
		NativeArray<Modify> adjustments = m_AdjustmentQuery.ToComponentDataArray<Modify>(Allocator.TempJob);
		for (int j = 0; j < nativeArray3.Length; j++)
		{
			if (Check(nativeArray3[j], adjustments))
			{
				commandBuffer2.AddComponent<TriggerCompleted>(nativeArray4[j]);
				TutorialSystem.ManualUnlock(nativeArray4[j], m_UnlockEventArchetype, base.EntityManager, commandBuffer2);
			}
		}
		nativeArray3.Dispose();
		nativeArray4.Dispose();
		adjustments.Dispose();
	}
```


