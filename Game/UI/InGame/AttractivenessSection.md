# Game.UI.InGame.AttractivenessSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AttractivenessSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Single <baseAttractiveness>k__BackingField;
    private System.Single <attractiveness>k__BackingField;
    private System.Collections.Generic.List<Game.UI.InGame.AttractivenessSection+AttractivenessFactor> <factors>k__BackingField;
    private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_SettingsQuery;

    protected System.String group { protected get; }
    private System.Single baseAttractiveness { private get; private set; }
    private System.Single attractiveness { private get; private set; }
    private System.Collections.Generic.List<Game.UI.InGame.AttractivenessSection+AttractivenessFactor> factors { private get; private set; }

    public AttractivenessSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Single <baseAttractiveness>k__BackingField`  

```csharp
private System.Single <baseAttractiveness>k__BackingField;
```

- `private System.Single <attractiveness>k__BackingField`  

```csharp
private System.Single <attractiveness>k__BackingField;
```

- `private System.Collections.Generic.List<Game.UI.InGame.AttractivenessSection+AttractivenessFactor> <factors>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.AttractivenessSection+AttractivenessFactor> <factors>k__BackingField;
```

- `private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem`  

```csharp
private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_SettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_SettingsQuery;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Single baseAttractiveness { private get; private set }`  

```csharp
private System.Single baseAttractiveness { private get; private set; }
```

- `private System.Single attractiveness { private get; private set }`  

```csharp
private System.Single attractiveness { private get; private set; }
```

- `private System.Collections.Generic.List<Game.UI.InGame.AttractivenessSection+AttractivenessFactor> factors { private get; private set }`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.AttractivenessSection+AttractivenessFactor> factors { private get; private set; }
```


## Constructors

- `public AttractivenessSection()`  

```csharp
[Preserve]
	public AttractivenessSection()
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
		factors = new List<AttractivenessFactor>(5);
		m_TerrainAttractivenessSystem = base.World.GetOrCreateSystemManaged<TerrainAttractivenessSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_SettingsQuery = GetEntityQuery(ComponentType.ReadOnly<AttractivenessParameterData>());
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		NativeArray<int> nativeArray = new NativeArray<int>(5, Allocator.TempJob);
		if (TryGetComponentWithUpgrades<AttractionData>(selectedEntity, selectedPrefab, out var data))
		{
			baseAttractiveness = data.m_Attractiveness;
		}
		attractiveness = baseAttractiveness;
		if (!base.EntityManager.HasComponent<Signature>(selectedEntity) && base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Efficiency> buffer))
		{
			float efficiency = BuildingUtils.GetEfficiency(buffer);
			attractiveness *= efficiency;
			AttractionSystem.SetFactor(nativeArray, AttractionSystem.AttractivenessFactor.Efficiency, (efficiency - 1f) * 100f);
		}
		if (base.EntityManager.TryGetComponent<Game.Buildings.Park>(selectedEntity, out var component) && TryGetComponentWithUpgrades<ParkData>(selectedEntity, selectedPrefab, out var data2))
		{
			float num = ((data2.m_MaintenancePool > 0) ? ((float)component.m_Maintenance / (float)data2.m_MaintenancePool) : 0f);
			float num2 = Mathf.Min(1f, 0.25f + 0.25f * (float)Mathf.FloorToInt(num / 0.3f));
			attractiveness *= num2;
			AttractionSystem.SetFactor(nativeArray, AttractionSystem.AttractivenessFactor.Maintenance, (num2 - 1f) * 100f);
		}
		if (base.EntityManager.TryGetComponent<Game.Objects.Transform>(selectedEntity, out var component2))
		{
			JobHandle dependencies;
			CellMapData<TerrainAttractiveness> data3 = m_TerrainAttractivenessSystem.GetData(readOnly: true, out dependencies);
			base.Dependency = JobHandle.CombineDependencies(base.Dependency, dependencies);
			base.Dependency.Complete();
			TerrainHeightData heightData = m_TerrainSystem.GetHeightData();
			AttractivenessParameterData singleton = m_SettingsQuery.GetSingleton<AttractivenessParameterData>();
			attractiveness *= 1f + 0.01f * TerrainAttractivenessSystem.EvaluateAttractiveness(component2.m_Position, data3, heightData, singleton, nativeArray);
		}
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (nativeArray[i] != 0)
			{
				factors.Add(new AttractivenessFactor(i, nativeArray[i]));
			}
		}
		nativeArray.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = Visible();
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("attractiveness");
		writer.Write(attractiveness);
		writer.PropertyName("baseAttractiveness");
		writer.Write(baseAttractiveness);
		writer.PropertyName("factors");
		writer.ArrayBegin(factors.Count);
		for (int i = 0; i < factors.Count; i++)
		{
			writer.Write(factors[i]);
		}
		writer.ArrayEnd();
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		baseAttractiveness = 0f;
		factors.Clear();
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (!base.EntityManager.HasComponent<AttractionData>(selectedPrefab))
		{
			return base.EntityManager.HasComponent<AttractivenessProvider>(selectedEntity);
		}
		return true;
	}
```


## Nested types

- `Game.UI.InGame.AttractivenessSection+AttractivenessFactor`  

