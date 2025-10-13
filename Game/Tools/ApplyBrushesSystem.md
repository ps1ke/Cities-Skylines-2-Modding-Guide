# Game.Tools.ApplyBrushesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ApplyBrushesSystem : Game.GameSystemBase
{
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.ComponentTypeSet m_AppliedDeletedTypes;
    private Game.Tools.ApplyBrushesSystem+TypeHandle __TypeHandle;

    public ApplyBrushesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle ApplyCellMapBrush<TCell, TModifier>(Game.Simulation.CellMapSystem<TCell> cellMapSystem, TModifier modifier, Game.Tools.Brush brush, Unity.Entities.Entity prefab, Game.Prefabs.TerraformingType terraformingType, Game.Tools.ApplyBrushesSystem+ApplyCellMapBrushJob<TCell, TModifier> applyCellMapBrushJob);
    private System.Void ApplyHeight(Game.Tools.Brush brush, Unity.Entities.Entity prefab, Game.Prefabs.TerraformingType terraformingType);
    private System.Void ApplyMaterial(Game.Tools.Brush brush, Unity.Entities.Entity prefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem`  

```csharp
private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedDeletedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedDeletedTypes;
```

- `private Game.Tools.ApplyBrushesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ApplyBrushesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ApplyBrushesSystem()`  

```csharp
[Preserve]
	public ApplyBrushesSystem()
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

- `private ApplyCellMapBrush<TCell, TModifier>(Game.Simulation.CellMapSystem<TCell> cellMapSystem, TModifier modifier, Game.Tools.Brush brush, Unity.Entities.Entity prefab, Game.Prefabs.TerraformingType terraformingType, Game.Tools.ApplyBrushesSystem+ApplyCellMapBrushJob<TCell, TModifier> applyCellMapBrushJob) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle ApplyCellMapBrush<TCell, TModifier>(Game.Simulation.CellMapSystem<TCell> cellMapSystem, TModifier modifier, Game.Tools.Brush brush, Unity.Entities.Entity prefab, Game.Prefabs.TerraformingType terraformingType, Game.Tools.ApplyBrushesSystem+ApplyCellMapBrushJob<TCell, TModifier> applyCellMapBrushJob);
```

- `private ApplyHeight(Game.Tools.Brush brush, Unity.Entities.Entity prefab, Game.Prefabs.TerraformingType terraformingType) : System.Void`  

```csharp
private void ApplyHeight(Brush brush, Entity prefab, TerraformingType terraformingType)
	{
		Bounds2 bounds = ToolUtils.GetBounds(brush);
		BrushPrefab prefab2 = m_PrefabSystem.GetPrefab<BrushPrefab>(prefab);
		if ((terraformingType != TerraformingType.Level && terraformingType != TerraformingType.Slope) || !(brush.m_Strength < 0f))
		{
			if (terraformingType == TerraformingType.Soften && brush.m_Strength < 0f)
			{
				brush.m_Strength = math.abs(brush.m_Strength) * 2f;
			}
			m_TerrainSystem.ApplyBrush(terraformingType, bounds, brush, prefab2.m_Texture);
		}
	}
```

- `private ApplyMaterial(Game.Tools.Brush brush, Unity.Entities.Entity prefab) : System.Void`  

```csharp
private void ApplyMaterial(Brush brush, Entity prefab)
	{
		m_TerrainMaterialSystem.GetOrAddMaterialIndex(brush.m_Tool);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolOutputBarrier = base.World.GetOrCreateSystemManaged<ToolOutputBarrier>();
		m_NaturalResourceSystem = base.World.GetOrCreateSystemManaged<NaturalResourceSystem>();
		m_GroundWaterSystem = base.World.GetOrCreateSystemManaged<GroundWaterSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_TerrainMaterialSystem = base.World.GetOrCreateSystemManaged<TerrainMaterialSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_TempQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<Brush>());
		m_AppliedDeletedTypes = new ComponentTypeSet(ComponentType.ReadWrite<Applied>(), ComponentType.ReadWrite<Deleted>());
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
		EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<Brush> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Brush_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<PrefabRef> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		EntityCommandBuffer entityCommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer();
		JobHandle jobHandle = default(JobHandle);
		NativeArray<ArchetypeChunk> nativeArray = m_TempQuery.ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			CompleteDependency();
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
				NativeArray<Brush> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle);
				NativeArray<PrefabRef> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle2);
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					Entity e = nativeArray2[j];
					Brush brush = nativeArray3[j];
					PrefabRef prefabRef = nativeArray4[j];
					if (base.EntityManager.TryGetComponent<TerraformingData>(brush.m_Tool, out var component))
					{
						switch (component.m_Target)
						{
						case TerraformingTarget.Ore:
							jobHandle = JobHandle.CombineDependencies(jobHandle, ApplyCellMapBrush(m_NaturalResourceSystem, new NaturalResourcesModifier(MapFeature.Ore), brush, prefabRef.m_Prefab, component.m_Type, default(ApplyCellMapBrushJob<NaturalResourceCell, NaturalResourcesModifier>)));
							break;
						case TerraformingTarget.Oil:
							jobHandle = JobHandle.CombineDependencies(jobHandle, ApplyCellMapBrush(m_NaturalResourceSystem, new NaturalResourcesModifier(MapFeature.Oil), brush, prefabRef.m_Prefab, component.m_Type, default(ApplyCellMapBrushJob<NaturalResourceCell, NaturalResourcesModifier>)));
							break;
						case TerraformingTarget.FertileLand:
							jobHandle = JobHandle.CombineDependencies(jobHandle, ApplyCellMapBrush(m_NaturalResourceSystem, new NaturalResourcesModifier(MapFeature.FertileLand), brush, prefabRef.m_Prefab, component.m_Type, default(ApplyCellMapBrushJob<NaturalResourceCell, NaturalResourcesModifier>)));
							break;
						case TerraformingTarget.GroundWater:
							jobHandle = JobHandle.CombineDependencies(jobHandle, ApplyCellMapBrush(m_GroundWaterSystem, default(GroundWaterModifier), brush, prefabRef.m_Prefab, component.m_Type, default(ApplyCellMapBrushJob<GroundWater, GroundWaterModifier>)));
							break;
						case TerraformingTarget.Height:
							ApplyHeight(brush, prefabRef.m_Prefab, component.m_Type);
							break;
						case TerraformingTarget.Material:
							ApplyMaterial(brush, prefabRef.m_Prefab);
							break;
						}
					}
					entityCommandBuffer.AddComponent(e, in m_AppliedDeletedTypes);
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Tools.ApplyBrushesSystem+ICellModifier<TCell>`  
- `Game.Tools.ApplyBrushesSystem+NaturalResourcesModifier`  
- `Game.Tools.ApplyBrushesSystem+GroundWaterModifier`  
- `Game.Tools.ApplyBrushesSystem+ApplyCellMapBrushJob<TCell, TModifier>`  
- `Game.Tools.ApplyBrushesSystem+TypeHandle`  

