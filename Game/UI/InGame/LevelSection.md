# Game.UI.InGame.LevelSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LevelSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.EntityQuery m_SpawnableBuildingQuery;
    private Unity.Entities.EntityQuery m_CityQuery;
    private System.Int32 <level>k__BackingField;
    private System.Int32 <maxLevel>k__BackingField;
    private System.Boolean <isUnderConstruction>k__BackingField;
    private System.Single <progress>k__BackingField;
    private Unity.Entities.Entity <zone>k__BackingField;
    private Unity.Collections.NativeArray<System.Int32> m_Result;
    private Game.UI.InGame.LevelSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    private System.Int32 level { private get; private set; }
    private System.Int32 maxLevel { private get; private set; }
    private System.Boolean isUnderConstruction { private get; private set; }
    private System.Single progress { private get; private set; }
    private Unity.Entities.Entity zone { private get; private set; }
    protected System.Boolean displayForUnderConstruction { protected get; }

    public LevelSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_SpawnableBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_SpawnableBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_CityQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityQuery;
```

- `private System.Int32 <level>k__BackingField`  

```csharp
private System.Int32 <level>k__BackingField;
```

- `private System.Int32 <maxLevel>k__BackingField`  

```csharp
private System.Int32 <maxLevel>k__BackingField;
```

- `private System.Boolean <isUnderConstruction>k__BackingField`  

```csharp
private System.Boolean <isUnderConstruction>k__BackingField;
```

- `private System.Single <progress>k__BackingField`  

```csharp
private System.Single <progress>k__BackingField;
```

- `private Unity.Entities.Entity <zone>k__BackingField`  

```csharp
private Unity.Entities.Entity <zone>k__BackingField;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Result`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Result;
```

- `private Game.UI.InGame.LevelSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.LevelSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 level { private get; private set }`  

```csharp
private System.Int32 level { private get; private set; }
```

- `private System.Int32 maxLevel { private get; private set }`  

```csharp
private System.Int32 maxLevel { private get; private set; }
```

- `private System.Boolean isUnderConstruction { private get; private set }`  

```csharp
private System.Boolean isUnderConstruction { private get; private set; }
```

- `private System.Single progress { private get; private set }`  

```csharp
private System.Single progress { private get; private set; }
```

- `private Unity.Entities.Entity zone { private get; private set }`  

```csharp
private Unity.Entities.Entity zone { private get; private set; }
```

- `protected System.Boolean displayForUnderConstruction { protected get }`  

```csharp
protected System.Boolean displayForUnderConstruction { protected get; }
```


## Constructors

- `public LevelSection()`  

```csharp
[Preserve]
	public LevelSection()
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
		m_SpawnableBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingData>(), ComponentType.ReadOnly<SpawnableBuildingData>());
		m_CityQuery = GetEntityQuery(ComponentType.ReadOnly<CityModifier>());
		m_Result = new NativeArray<int>(1, Allocator.Persistent);
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		m_Result.Dispose();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		SpawnableBuildingData componentData = base.EntityManager.GetComponentData<SpawnableBuildingData>(selectedPrefab);
		zone = componentData.m_ZonePrefab;
		ZoneData componentData2 = base.EntityManager.GetComponentData<ZoneData>(zone);
		if (isUnderConstruction)
		{
			base.tooltipKeys.Add("UnderConstruction");
			m_InfoUISystem.tooltipTags.Add(TooltipTags.UnderConstruction);
			return;
		}
		switch (componentData2.m_AreaType)
		{
		case AreaType.Residential:
			base.tooltipKeys.Add("Residential");
			break;
		case AreaType.Commercial:
			base.tooltipKeys.Add("Commercial");
			break;
		case AreaType.Industrial:
			base.tooltipKeys.Add(((componentData2.m_ZoneFlags & ZoneFlags.Office) != 0) ? "Office" : "Industrial");
			break;
		}
		BuildingPropertyData componentData3 = base.EntityManager.GetComponentData<BuildingPropertyData>(selectedPrefab);
		level = componentData.m_Level;
		maxLevel = math.max(m_Result[0], level);
		progress = 0f;
		if (componentData.m_Level < maxLevel)
		{
			int condition = base.EntityManager.GetComponentData<BuildingCondition>(selectedEntity).m_Condition;
			int levelingCost = BuildingUtils.GetLevelingCost(componentData2.m_AreaType, componentData3, level, base.EntityManager.GetBuffer<CityModifier>(m_CityQuery.GetSingletonEntity(), isReadOnly: true));
			progress = ((levelingCost > 0) ? ((float)condition / (float)levelingCost * 100f) : 100f);
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = Visible();
		if (base.visible)
		{
			if (base.EntityManager.TryGetComponent<UnderConstruction>(selectedEntity, out var component) && component.m_NewPrefab == Entity.Null)
			{
				isUnderConstruction = true;
				progress = Math.Min((int)component.m_Progress, 100);
				return;
			}
			BuildingData componentData = base.EntityManager.GetComponentData<BuildingData>(selectedPrefab);
			SpawnableBuildingData componentData2 = base.EntityManager.GetComponentData<SpawnableBuildingData>(selectedPrefab);
			JobChunkExtensions.Schedule(new CalculateMaxLevelJob
			{
				m_LotSize = componentData.m_LotSize,
				m_ZonePrefabEntity = componentData2.m_ZonePrefab,
				m_BuildingDataTypeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SpawnableBuildingDataTypeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Result = m_Result
			}, m_SpawnableBuildingQuery, base.Dependency).Complete();
		}
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("zone");
		writer.Write(m_PrefabSystem.GetPrefabName(zone));
		writer.PropertyName("level");
		writer.Write(level);
		writer.PropertyName("maxLevel");
		writer.Write(maxLevel);
		writer.PropertyName("isUnderConstruction");
		writer.Write(isUnderConstruction);
		writer.PropertyName("progress");
		writer.Write(progress);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		level = 0;
		maxLevel = 0;
		isUnderConstruction = false;
		progress = 0f;
		zone = Entity.Null;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (!base.EntityManager.HasComponent<SignatureBuildingData>(selectedPrefab) && !base.EntityManager.HasComponent<Abandoned>(selectedEntity) && base.EntityManager.HasComponent<Renter>(selectedEntity) && base.EntityManager.HasComponent<BuildingData>(selectedPrefab))
		{
			return base.EntityManager.HasComponent<SpawnableBuildingData>(selectedPrefab);
		}
		return false;
	}
```


## Nested types

- `Game.UI.InGame.LevelSection+CalculateMaxLevelJob`  
- `Game.UI.InGame.LevelSection+TypeHandle`  

