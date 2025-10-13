# Game.Prefabs.CompanyInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompanyInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_CompanyQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.CompanyInitializeSystem+TypeHandle __TypeHandle;

    public CompanyInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Entities.EntityQuery m_CompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.CompanyInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.CompanyInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CompanyInitializeSystem()`  

```csharp
[Preserve]
	public CompanyInitializeSystem()
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
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadWrite<BrandData>(),
				ComponentType.ReadOnly<PrefabData>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_CompanyQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<CompanyBrandElement>(), ComponentType.Exclude<Deleted>());
		RequireForUpdate(m_PrefabQuery);
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
		NativeArray<ArchetypeChunk> nativeArray = m_PrefabQuery.ToArchetypeChunkArray(Allocator.TempJob);
		EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<Deleted> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<PrefabData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<BrandData> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BrandData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		CompleteDependency();
		for (int i = 0; i < nativeArray.Length; i++)
		{
			ArchetypeChunk archetypeChunk = nativeArray[i];
			if (archetypeChunk.Has(ref typeHandle))
			{
				continue;
			}
			NativeArray<PrefabData> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle2);
			if (!archetypeChunk.Has(ref typeHandle3))
			{
				continue;
			}
			NativeArray<Entity> nativeArray3 = archetypeChunk.GetNativeArray(entityTypeHandle);
			for (int j = 0; j < nativeArray3.Length; j++)
			{
				Entity brand = nativeArray3[j];
				BrandPrefab prefab = m_PrefabSystem.GetPrefab<BrandPrefab>(nativeArray2[j]);
				for (int k = 0; k < prefab.m_Companies.Length; k++)
				{
					CompanyPrefab prefab2 = prefab.m_Companies[k];
					m_PrefabSystem.GetBuffer<CompanyBrandElement>(prefab2, isReadOnly: false).Add(new CompanyBrandElement(brand));
				}
			}
		}
		nativeArray.Dispose();
		JobHandle outJobHandle;
		InitializeAffiliatedBrandsJob jobData = new InitializeAffiliatedBrandsJob
		{
			m_Chunks = m_CompanyQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle),
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CommercialCompanyDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CommercialCompanyData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StorageCompanyDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_StorageCompanyData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_IndustrialProcessDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CompanyBrandElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_CompanyBrandElement_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_AffiliatedBrandElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_AffiliatedBrandElement_RW_BufferTypeHandle, ref base.CheckedStateRef)
		};
		base.Dependency = IJobExtensions.Schedule(jobData, outJobHandle);
		jobData.m_Chunks.Dispose(base.Dependency);
	}
```


## Nested types

- `Game.Prefabs.CompanyInitializeSystem+InitializeAffiliatedBrandsJob`  
- `Game.Prefabs.CompanyInitializeSystem+TypeHandle`  

