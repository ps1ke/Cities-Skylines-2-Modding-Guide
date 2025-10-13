# Game.UI.InGame.CompanyInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompanyInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Entities.EntityQuery m_CommercialQuery;
    private Unity.Entities.EntityQuery m_IndustrialQuery;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CommercialProfitability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_IndustrialProfitability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_OfficeProfitability;
    private Game.UI.InGame.CompanyInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }

    public CompanyInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Game.UI.InGame.IndicatorValue GetCommercialProfitability();
    private Game.UI.InGame.IndicatorValue GetIndustrialProfitability();
    private Game.UI.InGame.IndicatorValue GetOfficeProfitability();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void PerformUpdate();
}
```


## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Entities.EntityQuery m_CommercialQuery`  

```csharp
private Unity.Entities.EntityQuery m_CommercialQuery;
```

- `private Unity.Entities.EntityQuery m_IndustrialQuery`  

```csharp
private Unity.Entities.EntityQuery m_IndustrialQuery;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CommercialProfitability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CommercialProfitability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_IndustrialProfitability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_IndustrialProfitability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_OfficeProfitability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_OfficeProfitability;
```

- `private Game.UI.InGame.CompanyInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.CompanyInfoviewUISystem+TypeHandle __TypeHandle;
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

- `public CompanyInfoviewUISystem()`  

```csharp
[Preserve]
	public CompanyInfoviewUISystem()
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

- `private GetCommercialProfitability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetCommercialProfitability()
	{
		NativeArray<Entity> nativeArray = m_CommercialQuery.ToEntityArray(Allocator.TempJob);
		float current = 0f;
		try
		{
			int num = 0;
			int num2 = 0;
			for (int i = 0; i < nativeArray.Length; i++)
			{
				if (base.EntityManager.TryGetComponent<Profitability>(nativeArray[i], out var component))
				{
					num++;
					num2 += component.m_Profitability;
				}
			}
			current = ((num == 0) ? 0f : ((float)num2 / (float)num));
		}
		finally
		{
			nativeArray.Dispose();
		}
		return new IndicatorValue(0f, 255f, current);
	}
```

- `private GetIndustrialProfitability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetIndustrialProfitability()
	{
		NativeArray<Entity> nativeArray = m_IndustrialQuery.ToEntityArray(Allocator.TempJob);
		ComponentLookup<PrefabRef> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<ResourceData> datas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<IndustrialProcessData> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef);
		float current = 0f;
		try
		{
			int num = 0;
			int num2 = 0;
			for (int i = 0; i < nativeArray.Length; i++)
			{
				if (!base.EntityManager.TryGetComponent<Profitability>(nativeArray[i], out var component) || !componentLookup.HasComponent(nativeArray[i]))
				{
					continue;
				}
				PrefabRef prefabRef = componentLookup[nativeArray[i]];
				if (componentLookup2.HasComponent(prefabRef.m_Prefab))
				{
					IndustrialProcessData industrialProcessData = componentLookup2[prefabRef.m_Prefab];
					if (!(Math.Abs(EconomyUtils.GetWeight(prefabs: m_ResourceSystem.GetPrefabs(), r: industrialProcessData.m_Output.m_Resource, datas: ref datas)) < float.Epsilon))
					{
						num++;
						num2 += component.m_Profitability;
					}
				}
			}
			current = ((num == 0) ? 0f : ((float)num2 / (float)num));
		}
		finally
		{
			nativeArray.Dispose();
		}
		return new IndicatorValue(0f, 255f, current);
	}
```

- `private GetOfficeProfitability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetOfficeProfitability()
	{
		ResourcePrefabs prefabs = m_ResourceSystem.GetPrefabs();
		NativeArray<Entity> nativeArray = m_IndustrialQuery.ToEntityArray(Allocator.TempJob);
		ComponentLookup<PrefabRef> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<ResourceData> datas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<IndustrialProcessData> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef);
		float current = 0f;
		try
		{
			int num = 0;
			int num2 = 0;
			for (int i = 0; i < nativeArray.Length; i++)
			{
				if (base.EntityManager.TryGetComponent<Profitability>(nativeArray[i], out var component) && componentLookup.HasComponent(nativeArray[i]))
				{
					PrefabRef prefabRef = componentLookup[nativeArray[i]];
					if (componentLookup2.HasComponent(prefabRef.m_Prefab) && !(Math.Abs(EconomyUtils.GetWeight(componentLookup2[prefabRef.m_Prefab].m_Output.m_Resource, prefabs, ref datas)) > float.Epsilon))
					{
						num++;
						num2 += component.m_Profitability;
					}
				}
			}
			current = ((num == 0) ? 0f : ((float)num2 / (float)num));
		}
		finally
		{
			nativeArray.Dispose();
		}
		return new IndicatorValue(0f, 255f, current);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_CommercialQuery = GetEntityQuery(ComponentType.ReadOnly<Profitability>(), ComponentType.ReadOnly<PropertyRenter>(), ComponentType.ReadOnly<CommercialCompany>());
		m_IndustrialQuery = GetEntityQuery(ComponentType.ReadOnly<Profitability>(), ComponentType.ReadOnly<PropertyRenter>(), ComponentType.ReadOnly<IndustrialCompany>());
		AddBinding(m_CommercialProfitability = new GetterValueBinding<IndicatorValue>("companyInfoview", "commercialProfitability", GetCommercialProfitability, new ValueWriter<IndicatorValue>()));
		AddBinding(m_IndustrialProfitability = new GetterValueBinding<IndicatorValue>("companyInfoview", "industrialProfitability", GetIndustrialProfitability, new ValueWriter<IndicatorValue>()));
		AddBinding(m_OfficeProfitability = new GetterValueBinding<IndicatorValue>("companyInfoview", "officeProfitability", GetOfficeProfitability, new ValueWriter<IndicatorValue>()));
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

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		m_CommercialProfitability.Update();
		m_IndustrialProfitability.Update();
		m_OfficeProfitability.Update();
	}
```


## Nested types

- `Game.UI.InGame.CompanyInfoviewUISystem+TypeHandle`  

