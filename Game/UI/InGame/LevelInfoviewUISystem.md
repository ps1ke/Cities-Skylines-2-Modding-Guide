# Game.UI.InGame.LevelInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LevelInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Colossal.UI.Binding.RawValueBinding m_ResidentialLevels;
    private Colossal.UI.Binding.RawValueBinding m_CommercialLevels;
    private Colossal.UI.Binding.RawValueBinding m_IndustrialLevels;
    private Colossal.UI.Binding.RawValueBinding m_OfficeLevels;
    private Unity.Entities.EntityQuery m_SpawnableQuery;
    private Unity.Collections.NativeArray<Game.UI.InGame.LevelInfoviewUISystem+Levels> m_Results;
    private Game.UI.InGame.LevelInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }

    public LevelInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void PerformUpdate();
    private System.Void UpdateBindings();
    private System.Void UpdateCommercialLevels(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void UpdateIndustrialLevels(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void UpdateOfficeLevels(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void UpdateResidentialLevels(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteLevels(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.LevelInfoviewUISystem+Levels levels);
}
```


## Fields

- `private Colossal.UI.Binding.RawValueBinding m_ResidentialLevels`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ResidentialLevels;
```

- `private Colossal.UI.Binding.RawValueBinding m_CommercialLevels`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_CommercialLevels;
```

- `private Colossal.UI.Binding.RawValueBinding m_IndustrialLevels`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_IndustrialLevels;
```

- `private Colossal.UI.Binding.RawValueBinding m_OfficeLevels`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_OfficeLevels;
```

- `private Unity.Entities.EntityQuery m_SpawnableQuery`  

```csharp
private Unity.Entities.EntityQuery m_SpawnableQuery;
```

- `private Unity.Collections.NativeArray<Game.UI.InGame.LevelInfoviewUISystem+Levels> m_Results`  

```csharp
private Unity.Collections.NativeArray<Game.UI.InGame.LevelInfoviewUISystem+Levels> m_Results;
```

- `private Game.UI.InGame.LevelInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.LevelInfoviewUISystem+TypeHandle __TypeHandle;
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

- `public LevelInfoviewUISystem()`  

```csharp
[Preserve]
	public LevelInfoviewUISystem()
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
		m_SpawnableQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<ResidentialProperty>(),
				ComponentType.ReadOnly<CommercialProperty>(),
				ComponentType.ReadOnly<IndustrialProperty>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		AddBinding(m_ResidentialLevels = new RawValueBinding("levelInfo", "residential", UpdateResidentialLevels));
		AddBinding(m_CommercialLevels = new RawValueBinding("levelInfo", "commercial", UpdateCommercialLevels));
		AddBinding(m_IndustrialLevels = new RawValueBinding("levelInfo", "industrial", UpdateIndustrialLevels));
		AddBinding(m_OfficeLevels = new RawValueBinding("levelInfo", "office", UpdateOfficeLevels));
		m_Results = new NativeArray<Levels>(4, Allocator.Persistent);
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
		m_Results.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		UpdateBindings();
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		UpdateBindings();
	}
```

- `private UpdateBindings() : System.Void`  

```csharp
private void UpdateBindings()
	{
		ResetResults(m_Results);
		JobChunkExtensions.Schedule(new UpdateLevelsJob
		{
			m_PrefabRefHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResidentialPropertyHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ResidentialProperty_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CommercialPropertyHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_CommercialProperty_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_IndustrialPropertyHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_IndustrialProperty_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OfficeBuildingFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OfficeBuilding_RW_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableBuildingFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SignatureBuildingFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SignatureBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Results = m_Results
		}, m_SpawnableQuery, base.Dependency).Complete();
		m_ResidentialLevels.Update();
		m_CommercialLevels.Update();
		m_IndustrialLevels.Update();
		m_OfficeLevels.Update();
	}
```

- `private UpdateCommercialLevels(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void UpdateCommercialLevels(IJsonWriter writer)
	{
		Levels levels = m_Results[1];
		WriteLevels(writer, levels);
	}
```

- `private UpdateIndustrialLevels(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void UpdateIndustrialLevels(IJsonWriter writer)
	{
		Levels levels = m_Results[2];
		WriteLevels(writer, levels);
	}
```

- `private UpdateOfficeLevels(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void UpdateOfficeLevels(IJsonWriter writer)
	{
		Levels levels = m_Results[3];
		WriteLevels(writer, levels);
	}
```

- `private UpdateResidentialLevels(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void UpdateResidentialLevels(IJsonWriter writer)
	{
		Levels levels = m_Results[0];
		WriteLevels(writer, levels);
	}
```

- `private WriteLevels(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.LevelInfoviewUISystem+Levels levels) : System.Void`  

```csharp
private void WriteLevels(IJsonWriter writer, Levels levels)
	{
		InfoviewsUIUtils.UpdateFiveSlicePieChartData(writer, levels.Level1, levels.Level2, levels.Level3, levels.Level4, levels.Level5);
	}
```


## Nested types

- `Game.UI.InGame.LevelInfoviewUISystem+Result`  
- `Game.UI.InGame.LevelInfoviewUISystem+UpdateLevelsJob`  
- `Game.UI.InGame.LevelInfoviewUISystem+Levels`  
- `Game.UI.InGame.LevelInfoviewUISystem+TypeHandle`  

