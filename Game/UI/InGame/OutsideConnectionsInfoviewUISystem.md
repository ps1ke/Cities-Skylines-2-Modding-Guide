# Game.UI.InGame.OutsideConnectionsInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Code

```csharp
public class OutsideConnectionsInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_ResourceQuery;
    private Colossal.UI.Binding.RawValueBinding m_TopImportNames;
    private Colossal.UI.Binding.RawValueBinding m_TopExportNames;
    private Colossal.UI.Binding.RawValueBinding m_TopImportColors;
    private Colossal.UI.Binding.RawValueBinding m_TopExportColors;
    private Colossal.UI.Binding.RawValueBinding m_TopImportData;
    private Colossal.UI.Binding.RawValueBinding m_TopExportData;
    private System.Collections.Generic.List<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource> m_TopImports;
    private System.Collections.Generic.List<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource> m_TopExports;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }

    public OutsideConnectionsInfoviewUISystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void PerformUpdate();
    private System.Void UpdateCache();
    private System.Void UpdateExportColors(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void UpdateExportData(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void UpdateExportNames(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void UpdateImportColors(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void UpdateImportData(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void UpdateImportNames(Colossal.UI.Binding.IJsonWriter binder);
}
```


## Fields

- `private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem`  

```csharp
private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  

```csharp
private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_ResourceQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResourceQuery;
```

- `private Colossal.UI.Binding.RawValueBinding m_TopImportNames`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TopImportNames;
```

- `private Colossal.UI.Binding.RawValueBinding m_TopExportNames`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TopExportNames;
```

- `private Colossal.UI.Binding.RawValueBinding m_TopImportColors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TopImportColors;
```

- `private Colossal.UI.Binding.RawValueBinding m_TopExportColors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TopExportColors;
```

- `private Colossal.UI.Binding.RawValueBinding m_TopImportData`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TopImportData;
```

- `private Colossal.UI.Binding.RawValueBinding m_TopExportData`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TopExportData;
```

- `private System.Collections.Generic.List<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource> m_TopImports`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource> m_TopImports;
```

- `private System.Collections.Generic.List<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource> m_TopExports`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource> m_TopExports;
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


## Constructors

- `public OutsideConnectionsInfoviewUISystem()`  

```csharp
[Preserve]
	public OutsideConnectionsInfoviewUISystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CommercialDemandSystem = base.World.GetOrCreateSystemManaged<CommercialDemandSystem>();
		m_IndustrialDemandSystem = base.World.GetOrCreateSystemManaged<IndustrialDemandSystem>();
		m_CountCompanyDataSystem = base.World.GetOrCreateSystemManaged<CountCompanyDataSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ResourceQuery = GetEntityQuery(ComponentType.ReadOnly<ResourceData>(), ComponentType.ReadOnly<TaxableResourceData>(), ComponentType.ReadOnly<PrefabData>());
		m_TopImports = new List<TopResource>(42);
		m_TopExports = new List<TopResource>(42);
		UpdateCache();
		AddBinding(m_TopImportNames = new RawValueBinding("outsideInfo", "topImportNames", UpdateImportNames));
		AddBinding(m_TopImportColors = new RawValueBinding("outsideInfo", "topImportColors", UpdateImportColors));
		AddBinding(m_TopImportData = new RawValueBinding("outsideInfo", "topImportData", UpdateImportData));
		AddBinding(m_TopExportNames = new RawValueBinding("outsideInfo", "topExportNames", UpdateExportNames));
		AddBinding(m_TopExportColors = new RawValueBinding("outsideInfo", "topExportColors", UpdateExportColors));
		AddBinding(m_TopExportData = new RawValueBinding("outsideInfo", "topExportData", UpdateExportData));
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		UpdateCache();
		m_TopImportNames.Update();
		m_TopImportColors.Update();
		m_TopImportData.Update();
		m_TopExportNames.Update();
		m_TopExportColors.Update();
		m_TopExportData.Update();
	}
```

- `private UpdateCache() : System.Void`  

```csharp
private void UpdateCache()
	{
		NativeArray<Entity> nativeArray = m_ResourceQuery.ToEntityArray(Allocator.TempJob);
		NativeArray<PrefabData> nativeArray2 = m_ResourceQuery.ToComponentDataArray<PrefabData>(Allocator.TempJob);
		JobHandle deps;
		NativeArray<int> production = m_CountCompanyDataSystem.GetProduction(out deps);
		JobHandle deps2;
		NativeArray<int> consumption = m_IndustrialDemandSystem.GetConsumption(out deps2);
		JobHandle deps3;
		NativeArray<int> consumption2 = m_CommercialDemandSystem.GetConsumption(out deps3);
		JobHandle.CompleteAll(ref deps, ref deps2, ref deps3);
		m_TopImports.Clear();
		m_TopExports.Clear();
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ResourcePrefab prefab = m_PrefabSystem.GetPrefab<ResourcePrefab>(nativeArray2[i]);
				int resourceIndex = EconomyUtils.GetResourceIndex(EconomyUtils.GetResource(prefab.m_Resource));
				int num = production[resourceIndex];
				int num2 = consumption[resourceIndex];
				int num3 = consumption2[resourceIndex];
				int num4 = math.min(num2 + num3, num);
				int num5 = math.min(num2, num4);
				int num6 = num2 - num5;
				int num7 = math.min(num3, num4 - num5);
				int amount = num3 - num7 + num6;
				int amount2 = num - num4;
				m_TopImports.Add(new TopResource(prefab.name, amount, prefab.m_Color));
				m_TopExports.Add(new TopResource(prefab.name, amount2, prefab.m_Color));
			}
			m_TopImports.Sort();
			m_TopExports.Sort();
		}
		finally
		{
			nativeArray.Dispose();
			nativeArray2.Dispose();
		}
	}
```

- `private UpdateExportColors(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void UpdateExportColors(IJsonWriter binder)
	{
		int num = 10;
		if (m_TopExports.Count < num)
		{
			num = m_TopExports.Count;
		}
		binder.ArrayBegin(num);
		for (int i = 0; i < num; i++)
		{
			binder.Write(m_TopExports[i].color.ToHexCode());
		}
		binder.ArrayEnd();
	}
```

- `private UpdateExportData(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void UpdateExportData(IJsonWriter binder)
	{
		int num = 0;
		int num2 = 10;
		if (m_TopExports.Count < num2)
		{
			num2 = m_TopExports.Count;
		}
		binder.TypeBegin("infoviews.ChartData");
		binder.PropertyName("values");
		binder.ArrayBegin(num2);
		for (int i = 0; i < num2; i++)
		{
			binder.Write(m_TopExports[i].amount);
			num += m_TopExports[i].amount;
		}
		binder.ArrayEnd();
		binder.PropertyName("total");
		binder.Write(num);
		binder.TypeEnd();
	}
```

- `private UpdateExportNames(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void UpdateExportNames(IJsonWriter binder)
	{
		int num = 10;
		if (m_TopExports.Count < num)
		{
			num = m_TopExports.Count;
		}
		binder.ArrayBegin(num);
		for (int i = 0; i < num; i++)
		{
			binder.Write(m_TopExports[i].id);
		}
		binder.ArrayEnd();
	}
```

- `private UpdateImportColors(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void UpdateImportColors(IJsonWriter binder)
	{
		int num = 10;
		if (m_TopImports.Count < num)
		{
			num = m_TopImports.Count;
		}
		binder.ArrayBegin(num);
		for (int i = 0; i < num; i++)
		{
			binder.Write(m_TopImports[i].color.ToHexCode());
		}
		binder.ArrayEnd();
	}
```

- `private UpdateImportData(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void UpdateImportData(IJsonWriter binder)
	{
		int num = 0;
		int num2 = 10;
		if (m_TopImports.Count < num2)
		{
			num2 = m_TopImports.Count;
		}
		binder.TypeBegin("infoviews.ChartData");
		binder.PropertyName("values");
		binder.ArrayBegin(num2);
		for (int i = 0; i < num2; i++)
		{
			binder.Write(m_TopImports[i].amount);
			num += m_TopImports[i].amount;
		}
		binder.ArrayEnd();
		binder.PropertyName("total");
		binder.Write(num);
		binder.TypeEnd();
	}
```

- `private UpdateImportNames(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void UpdateImportNames(IJsonWriter binder)
	{
		int num = 10;
		if (m_TopImports.Count < num)
		{
			num = m_TopImports.Count;
		}
		binder.ArrayBegin(num);
		for (int i = 0; i < num; i++)
		{
			binder.Write(m_TopImports[i].id);
		}
		binder.ArrayEnd();
	}
```


## Nested types

- `Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource`  

