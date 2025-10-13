# Game.UI.InGame.TransportInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Code

```csharp
public class TransportInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Prefabs.UnlockSystem m_UnlockSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Unity.Entities.EntityQuery m_LineQuery;
    private Unity.Entities.EntityQuery m_ModifiedLineQuery;
    private Colossal.UI.Binding.RawValueBinding m_Summaries;
    private Game.Prefabs.UITransportConfigurationPrefab m_Config;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public TransportInfoviewUISystem();

    private System.Void BindSummaries(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void PerformUpdate();
}
```


## Fields

- `private Game.Prefabs.UnlockSystem m_UnlockSystem`  

```csharp
private Game.Prefabs.UnlockSystem m_UnlockSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Unity.Entities.EntityQuery m_LineQuery`  

```csharp
private Unity.Entities.EntityQuery m_LineQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedLineQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedLineQuery;
```

- `private Colossal.UI.Binding.RawValueBinding m_Summaries`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_Summaries;
```

- `private Game.Prefabs.UITransportConfigurationPrefab m_Config`  

```csharp
private Game.Prefabs.UITransportConfigurationPrefab m_Config;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```

- `protected System.Boolean Modified { protected get }`  

```csharp
protected System.Boolean Modified { protected get; }
```


## Constructors

- `public TransportInfoviewUISystem()`  

```csharp
[Preserve]
	public TransportInfoviewUISystem()
	{
	}
```


## Methods

- `private BindSummaries(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindSummaries(IJsonWriter writer)
	{
		NativeArray<UITransportLineData> sortedLines = TransportUIUtils.GetSortedLines(m_LineQuery, base.EntityManager, m_PrefabSystem);
		writer.TypeBegin(GetType().FullName + "+TransportSummaries");
		writer.PropertyName("passengerSummaries");
		writer.ArrayBegin(m_Config.m_PassengerSummaryItems.Length);
		UITransportSummaryItem[] passengerSummaryItems = m_Config.m_PassengerSummaryItems;
		foreach (UITransportSummaryItem uITransportSummaryItem in passengerSummaryItems)
		{
			new PassengerSummary(m_PrefabSystem.GetEntity(uITransportSummaryItem.m_Unlockable), Enum.GetName(typeof(TransportType), uITransportSummaryItem.m_Type), uITransportSummaryItem.m_Icon, m_UnlockSystem.IsLocked(uITransportSummaryItem.m_Unlockable), uITransportSummaryItem.m_ShowLines ? TransportUIUtils.CountLines(sortedLines, uITransportSummaryItem.m_Type) : 0, m_CityStatisticsSystem.GetStatisticValue(uITransportSummaryItem.m_Statistic, 1), m_CityStatisticsSystem.GetStatisticValue(uITransportSummaryItem.m_Statistic)).Write(m_PrefabUISystem, writer);
		}
		writer.ArrayEnd();
		writer.PropertyName("cargoSummaries");
		writer.ArrayBegin(m_Config.m_CargoSummaryItems.Length);
		passengerSummaryItems = m_Config.m_CargoSummaryItems;
		foreach (UITransportSummaryItem uITransportSummaryItem2 in passengerSummaryItems)
		{
			new CargoSummary(m_PrefabSystem.GetEntity(uITransportSummaryItem2.m_Unlockable), Enum.GetName(typeof(TransportType), uITransportSummaryItem2.m_Type), uITransportSummaryItem2.m_Icon, m_UnlockSystem.IsLocked(uITransportSummaryItem2.m_Unlockable), uITransportSummaryItem2.m_ShowLines ? TransportUIUtils.CountLines(sortedLines, uITransportSummaryItem2.m_Type, cargo: true) : 0, m_CityStatisticsSystem.GetStatisticValue(uITransportSummaryItem2.m_Statistic)).Write(m_PrefabUISystem, writer);
		}
		writer.ArrayEnd();
		writer.TypeEnd();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_UnlockSystem = base.World.GetOrCreateSystemManaged<UnlockSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabUISystem = base.World.GetOrCreateSystemManaged<PrefabUISystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_ConfigQuery = GetEntityQuery(ComponentType.ReadOnly<UITransportConfigurationData>());
		m_LineQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[4]
			{
				ComponentType.ReadOnly<Route>(),
				ComponentType.ReadWrite<TransportLine>(),
				ComponentType.ReadOnly<RouteWaypoint>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_ModifiedLineQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[4]
			{
				ComponentType.ReadOnly<Route>(),
				ComponentType.ReadWrite<TransportLine>(),
				ComponentType.ReadOnly<RouteWaypoint>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		AddBinding(m_Summaries = new RawValueBinding("transportInfo", "summaries", BindSummaries));
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		if (base.Enabled)
		{
			m_Config = m_PrefabSystem.GetSingletonPrefab<UITransportConfigurationPrefab>(m_ConfigQuery);
		}
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		m_Summaries.Update();
	}
```


## Nested types

- `Game.UI.InGame.TransportInfoviewUISystem+PassengerSummary`  
- `Game.UI.InGame.TransportInfoviewUISystem+CargoSummary`  

