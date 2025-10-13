# Game.UI.Tooltip.TempCostTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TempCostTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Game.UI.Tooltip.IntTooltip m_Cost;
    private Game.UI.Tooltip.IntTooltip m_Refund;
    private Game.UI.Tooltip.TempCostTooltipSystem+TypeHandle __TypeHandle;

    public TempCostTooltipSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Game.UI.Tooltip.IntTooltip m_Cost`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Cost;
```

- `private Game.UI.Tooltip.IntTooltip m_Refund`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Refund;
```

- `private Game.UI.Tooltip.TempCostTooltipSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Tooltip.TempCostTooltipSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TempCostTooltipSystem()`  

```csharp
[Preserve]
	public TempCostTooltipSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_TempQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.Exclude<Deleted>());
		m_Cost = new IntTooltip
		{
			path = "cost",
			icon = "Media/Game/Icons/Money.svg",
			unit = "money"
		};
		m_Refund = new IntTooltip
		{
			path = "refund",
			icon = "Media/Game/Icons/Money.svg",
			label = LocalizedString.Id("Tools.REFUND_AMOUNT_LABEL"),
			unit = "money"
		};
		RequireForUpdate(m_TempQuery);
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		CompleteDependency();
		NativeArray<ArchetypeChunk> nativeArray = m_TempQuery.ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			int num = 0;
			ComponentTypeHandle<Temp> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			foreach (ArchetypeChunk item in nativeArray)
			{
				foreach (Temp item2 in item.GetNativeArray(ref typeHandle))
				{
					if ((item2.m_Flags & (TempFlags.Create | TempFlags.Delete | TempFlags.Modify | TempFlags.Replace | TempFlags.Upgrade | TempFlags.RemoveCost)) != 0 && (item2.m_Flags & TempFlags.Cancel) == 0)
					{
						num += item2.m_Cost;
					}
				}
			}
			if (num > 0)
			{
				m_Cost.value = num;
				m_Cost.color = ((m_CitySystem.moneyAmount < num) ? TooltipColor.Error : TooltipColor.Info);
				AddMouseTooltip(m_Cost);
			}
			else if (num < 0)
			{
				m_Refund.value = -num;
				AddMouseTooltip(m_Refund);
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```


## Nested types

- `Game.UI.Tooltip.TempCostTooltipSystem+TypeHandle`  

