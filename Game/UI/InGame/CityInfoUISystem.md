# Game.UI.InGame.CityInfoUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityInfoUISystem : Game.UI.UISystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem;
    private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.CitizenHappinessSystem m_CitizenHappinessSystem;
    private Colossal.UI.Binding.RawValueBinding m_ResidentialLowFactors;
    private Colossal.UI.Binding.RawValueBinding m_ResidentialMediumFactors;
    private Colossal.UI.Binding.RawValueBinding m_ResidentialHighFactors;
    private Colossal.UI.Binding.RawValueBinding m_CommercialFactors;
    private Colossal.UI.Binding.RawValueBinding m_IndustrialFactors;
    private Colossal.UI.Binding.RawValueBinding m_OfficeFactors;
    private Colossal.UI.Binding.RawValueBinding m_HappinessFactors;
    private System.Single m_ResidentialLowDemand;
    private System.Single m_ResidentialMediumDemand;
    private System.Single m_ResidentialHighDemand;
    private System.Single m_CommercialDemand;
    private System.Single m_IndustrialDemand;
    private System.Single m_OfficeDemand;
    private System.UInt32 m_LastFrameIndex;
    private System.Int32 m_AvgHappiness;
    private Game.UI.UIUpdateState m_UpdateState;
    private Game.UI.InGame.CityInfoUISystem+TypeHandle __TypeHandle;
    public static const System.String kGroup;

    private System.Single m_ResidentialLowDemandBindingValue { private get; }
    private System.Single m_ResidentialMediumDemandBindingValue { private get; }
    private System.Single m_ResidentialHighDemandBindingValue { private get; }
    private System.Single m_CommercialDemandBindingValue { private get; }
    private System.Single m_IndustrialDemandBindingValue { private get; }
    private System.Single m_OfficeDemandBindingValue { private get; }

    public CityInfoUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Single <OnCreate>b__35_0();
    private System.Single <OnCreate>b__35_1();
    private System.Single <OnCreate>b__35_2();
    private System.Single <OnCreate>b__35_3();
    private System.Single <OnCreate>b__35_4();
    private System.Single <OnCreate>b__35_5();
    private System.Int32 <OnCreate>b__35_6();
    private static System.Single AdvanceSmoothDemand(System.Single current, System.Int32 target, System.UInt32 delta);
    public System.Void Deserialize<TReader>(TReader reader);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    public System.Void RequestUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    private System.Void WriteCommercialFactors(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteDemandFactors(Colossal.UI.Binding.IJsonWriter writer, Unity.Collections.NativeArray<System.Int32> factors, Unity.Jobs.JobHandle deps);
    private System.Void WriteHappinessFactors(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteIndustrialFactors(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteOfficeFactors(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteResidentialHighFactors(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteResidentialLowFactors(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteResidentialMediumFactors(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem`  

```csharp
private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem;
```

- `private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem`  

```csharp
private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.CitizenHappinessSystem m_CitizenHappinessSystem`  

```csharp
private Game.Simulation.CitizenHappinessSystem m_CitizenHappinessSystem;
```

- `private Colossal.UI.Binding.RawValueBinding m_ResidentialLowFactors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ResidentialLowFactors;
```

- `private Colossal.UI.Binding.RawValueBinding m_ResidentialMediumFactors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ResidentialMediumFactors;
```

- `private Colossal.UI.Binding.RawValueBinding m_ResidentialHighFactors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ResidentialHighFactors;
```

- `private Colossal.UI.Binding.RawValueBinding m_CommercialFactors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_CommercialFactors;
```

- `private Colossal.UI.Binding.RawValueBinding m_IndustrialFactors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_IndustrialFactors;
```

- `private Colossal.UI.Binding.RawValueBinding m_OfficeFactors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_OfficeFactors;
```

- `private Colossal.UI.Binding.RawValueBinding m_HappinessFactors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_HappinessFactors;
```

- `private System.Single m_ResidentialLowDemand`  

```csharp
private System.Single m_ResidentialLowDemand;
```

- `private System.Single m_ResidentialMediumDemand`  

```csharp
private System.Single m_ResidentialMediumDemand;
```

- `private System.Single m_ResidentialHighDemand`  

```csharp
private System.Single m_ResidentialHighDemand;
```

- `private System.Single m_CommercialDemand`  

```csharp
private System.Single m_CommercialDemand;
```

- `private System.Single m_IndustrialDemand`  

```csharp
private System.Single m_IndustrialDemand;
```

- `private System.Single m_OfficeDemand`  

```csharp
private System.Single m_OfficeDemand;
```

- `private System.UInt32 m_LastFrameIndex`  

```csharp
private System.UInt32 m_LastFrameIndex;
```

- `private System.Int32 m_AvgHappiness`  

```csharp
private System.Int32 m_AvgHappiness;
```

- `private Game.UI.UIUpdateState m_UpdateState`  

```csharp
private Game.UI.UIUpdateState m_UpdateState;
```

- `private Game.UI.InGame.CityInfoUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.CityInfoUISystem+TypeHandle __TypeHandle;
```

- `public static const System.String kGroup`  

```csharp
public static const System.String kGroup;
```


## Properties

- `private System.Single m_ResidentialLowDemandBindingValue { private get }`  

```csharp
private System.Single m_ResidentialLowDemandBindingValue { private get; }
```

- `private System.Single m_ResidentialMediumDemandBindingValue { private get }`  

```csharp
private System.Single m_ResidentialMediumDemandBindingValue { private get; }
```

- `private System.Single m_ResidentialHighDemandBindingValue { private get }`  

```csharp
private System.Single m_ResidentialHighDemandBindingValue { private get; }
```

- `private System.Single m_CommercialDemandBindingValue { private get }`  

```csharp
private System.Single m_CommercialDemandBindingValue { private get; }
```

- `private System.Single m_IndustrialDemandBindingValue { private get }`  

```csharp
private System.Single m_IndustrialDemandBindingValue { private get; }
```

- `private System.Single m_OfficeDemandBindingValue { private get }`  

```csharp
private System.Single m_OfficeDemandBindingValue { private get; }
```


## Constructors

- `public CityInfoUISystem()`  

```csharp
[Preserve]
	public CityInfoUISystem()
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

- `private <OnCreate>b__35_0() : System.Single`  

```csharp
private System.Single <OnCreate>b__35_0();
```

- `private <OnCreate>b__35_1() : System.Single`  

```csharp
private System.Single <OnCreate>b__35_1();
```

- `private <OnCreate>b__35_2() : System.Single`  

```csharp
private System.Single <OnCreate>b__35_2();
```

- `private <OnCreate>b__35_3() : System.Single`  

```csharp
private System.Single <OnCreate>b__35_3();
```

- `private <OnCreate>b__35_4() : System.Single`  

```csharp
private System.Single <OnCreate>b__35_4();
```

- `private <OnCreate>b__35_5() : System.Single`  

```csharp
private System.Single <OnCreate>b__35_5();
```

- `private <OnCreate>b__35_6() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__35_6();
```

- `private static AdvanceSmoothDemand(System.Single current, System.Int32 target, System.UInt32 delta) : System.Single`  

```csharp
private static float AdvanceSmoothDemand(float current, int target, uint delta)
	{
		return math.clamp((float)target / 100f, current - 0.000625f * (float)delta, current + 0.000125f * (float)delta);
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ResidentialDemandSystem = base.World.GetOrCreateSystemManaged<ResidentialDemandSystem>();
		m_CommercialDemandSystem = base.World.GetOrCreateSystemManaged<CommercialDemandSystem>();
		m_IndustrialDemandSystem = base.World.GetOrCreateSystemManaged<IndustrialDemandSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_CitizenHappinessSystem = base.World.GetOrCreateSystemManaged<CitizenHappinessSystem>();
		AddUpdateBinding(new GetterValueBinding<float>("cityInfo", "residentialLowDemand", () => m_ResidentialLowDemandBindingValue));
		AddUpdateBinding(new GetterValueBinding<float>("cityInfo", "residentialMediumDemand", () => m_ResidentialMediumDemandBindingValue));
		AddUpdateBinding(new GetterValueBinding<float>("cityInfo", "residentialHighDemand", () => m_ResidentialHighDemandBindingValue));
		AddUpdateBinding(new GetterValueBinding<float>("cityInfo", "commercialDemand", () => m_CommercialDemandBindingValue));
		AddUpdateBinding(new GetterValueBinding<float>("cityInfo", "industrialDemand", () => m_IndustrialDemandBindingValue));
		AddUpdateBinding(new GetterValueBinding<float>("cityInfo", "officeDemand", () => m_OfficeDemandBindingValue));
		AddUpdateBinding(new GetterValueBinding<int>("cityInfo", "happiness", () => m_AvgHappiness));
		AddBinding(m_ResidentialLowFactors = new RawValueBinding("cityInfo", "residentialLowFactors", WriteResidentialLowFactors));
		AddBinding(m_ResidentialMediumFactors = new RawValueBinding("cityInfo", "residentialMediumFactors", WriteResidentialMediumFactors));
		AddBinding(m_ResidentialHighFactors = new RawValueBinding("cityInfo", "residentialHighFactors", WriteResidentialHighFactors));
		AddBinding(m_CommercialFactors = new RawValueBinding("cityInfo", "commercialFactors", WriteCommercialFactors));
		AddBinding(m_IndustrialFactors = new RawValueBinding("cityInfo", "industrialFactors", WriteIndustrialFactors));
		AddBinding(m_OfficeFactors = new RawValueBinding("cityInfo", "officeFactors", WriteOfficeFactors));
		AddBinding(m_HappinessFactors = new RawValueBinding("cityInfo", "happinessFactors", WriteHappinessFactors));
		m_UpdateState = UIUpdateState.Create(base.World, 256);
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_UpdateState.ForceUpdate();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		uint num = m_SimulationSystem.frameIndex - m_LastFrameIndex;
		if (num != 0)
		{
			m_LastFrameIndex = m_SimulationSystem.frameIndex;
			m_ResidentialLowDemand = AdvanceSmoothDemand(m_ResidentialLowDemand, m_ResidentialDemandSystem.buildingDemand.x, num);
			m_ResidentialMediumDemand = AdvanceSmoothDemand(m_ResidentialMediumDemand, m_ResidentialDemandSystem.buildingDemand.y, num);
			m_ResidentialHighDemand = AdvanceSmoothDemand(m_ResidentialHighDemand, m_ResidentialDemandSystem.buildingDemand.z, num);
			m_CommercialDemand = AdvanceSmoothDemand(m_CommercialDemand, m_CommercialDemandSystem.buildingDemand, num);
			int target = math.max(m_IndustrialDemandSystem.industrialBuildingDemand, m_IndustrialDemandSystem.storageBuildingDemand);
			m_IndustrialDemand = AdvanceSmoothDemand(m_IndustrialDemand, target, num);
			m_OfficeDemand = AdvanceSmoothDemand(m_OfficeDemand, m_IndustrialDemandSystem.officeBuildingDemand, num);
			if (base.EntityManager.HasComponent<Population>(m_CitySystem.City))
			{
				m_AvgHappiness = base.EntityManager.GetComponentData<Population>(m_CitySystem.City).m_AverageHappiness;
			}
			else
			{
				m_AvgHappiness = 50;
			}
		}
		if (m_UpdateState.Advance())
		{
			m_ResidentialLowFactors.Update();
			m_ResidentialMediumFactors.Update();
			m_ResidentialHighFactors.Update();
			m_CommercialFactors.Update();
			m_IndustrialFactors.Update();
			m_OfficeFactors.Update();
			m_HappinessFactors.Update();
		}
	}
```

- `public RequestUpdate() : System.Void`  

```csharp
public void RequestUpdate()
	{
		m_UpdateState.ForceUpdate();
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_ResidentialLowDemand = 0f;
		m_ResidentialMediumDemand = 0f;
		m_ResidentialHighDemand = 0f;
		m_CommercialDemand = 0f;
		m_IndustrialDemand = 0f;
		m_OfficeDemand = 0f;
		m_LastFrameIndex = 0u;
	}
```

- `private WriteCommercialFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void WriteCommercialFactors(IJsonWriter writer)
	{
		JobHandle deps;
		NativeArray<int> demandFactors = m_CommercialDemandSystem.GetDemandFactors(out deps);
		WriteDemandFactors(writer, demandFactors, deps);
	}
```

- `private WriteDemandFactors(Colossal.UI.Binding.IJsonWriter writer, Unity.Collections.NativeArray<System.Int32> factors, Unity.Jobs.JobHandle deps) : System.Void`  

```csharp
private void WriteDemandFactors(IJsonWriter writer, NativeArray<int> factors, JobHandle deps)
	{
		deps.Complete();
		NativeList<FactorInfo> list = FactorInfo.FromFactorArray(factors, Allocator.Temp);
		list.Sort();
		try
		{
			int num = math.min(5, list.Length);
			writer.ArrayBegin(num);
			for (int i = 0; i < num; i++)
			{
				list[i].WriteDemandFactor(writer);
			}
			writer.ArrayEnd();
		}
		finally
		{
			list.Dispose();
		}
	}
```

- `private WriteHappinessFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void WriteHappinessFactors(IJsonWriter writer)
	{
		NativeList<FactorInfo> list = new NativeList<FactorInfo>(25, Allocator.Temp);
		EntityQuery entityQuery = GetEntityQuery(ComponentType.ReadOnly<HappinessFactorParameterData>());
		if (!entityQuery.IsEmptyIgnoreFilter)
		{
			Entity singletonEntity = entityQuery.GetSingletonEntity();
			DynamicBuffer<HappinessFactorParameterData> buffer = base.EntityManager.GetBuffer<HappinessFactorParameterData>(singletonEntity, isReadOnly: true);
			ComponentLookup<Locked> locked = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentLookup, ref base.CheckedStateRef);
			for (int i = 0; i < 25; i++)
			{
				int num = Mathf.RoundToInt(m_CitizenHappinessSystem.GetHappinessFactor((CitizenHappinessSystem.HappinessFactor)i, buffer, ref locked).x);
				if (num != 0)
				{
					list.Add(new FactorInfo(i, num));
				}
			}
		}
		list.Sort();
		try
		{
			int num2 = math.min(10, list.Length);
			writer.ArrayBegin(num2);
			for (int j = 0; j < num2; j++)
			{
				list[j].WriteHappinessFactor(writer);
			}
			writer.ArrayEnd();
		}
		finally
		{
			list.Dispose();
		}
	}
```

- `private WriteIndustrialFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void WriteIndustrialFactors(IJsonWriter writer)
	{
		JobHandle deps;
		NativeArray<int> industrialDemandFactors = m_IndustrialDemandSystem.GetIndustrialDemandFactors(out deps);
		WriteDemandFactors(writer, industrialDemandFactors, deps);
	}
```

- `private WriteOfficeFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void WriteOfficeFactors(IJsonWriter writer)
	{
		JobHandle deps;
		NativeArray<int> officeDemandFactors = m_IndustrialDemandSystem.GetOfficeDemandFactors(out deps);
		WriteDemandFactors(writer, officeDemandFactors, deps);
	}
```

- `private WriteResidentialHighFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void WriteResidentialHighFactors(IJsonWriter writer)
	{
		JobHandle deps;
		NativeArray<int> highDensityDemandFactors = m_ResidentialDemandSystem.GetHighDensityDemandFactors(out deps);
		WriteDemandFactors(writer, highDensityDemandFactors, deps);
	}
```

- `private WriteResidentialLowFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void WriteResidentialLowFactors(IJsonWriter writer)
	{
		JobHandle deps;
		NativeArray<int> lowDensityDemandFactors = m_ResidentialDemandSystem.GetLowDensityDemandFactors(out deps);
		WriteDemandFactors(writer, lowDensityDemandFactors, deps);
	}
```

- `private WriteResidentialMediumFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void WriteResidentialMediumFactors(IJsonWriter writer)
	{
		JobHandle deps;
		NativeArray<int> mediumDensityDemandFactors = m_ResidentialDemandSystem.GetMediumDensityDemandFactors(out deps);
		WriteDemandFactors(writer, mediumDensityDemandFactors, deps);
	}
```


## Nested types

- `Game.UI.InGame.CityInfoUISystem+TypeHandle`  

