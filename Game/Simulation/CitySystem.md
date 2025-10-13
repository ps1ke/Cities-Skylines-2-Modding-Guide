# Game.Simulation.CitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ICitySystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CitySystem : Game.GameSystemBase, Game.Simulation.ICitySystem, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Unity.Entities.EntityQuery m_ServiceFeeParameterQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.Entity m_City;
    private System.Int32 m_Money;
    private System.Int32 m_XP;

    public Unity.Entities.Entity City { get; }
    public System.Int32 moneyAmount { get; }
    public System.Int32 XP { get; }

    public CitySystem();

    public System.Void Deserialize<TReader>(TReader reader);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ServiceFeeParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceFeeParameterQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.Entity m_City`  

```csharp
private Unity.Entities.Entity m_City;
```

- `private System.Int32 m_Money`  

```csharp
private System.Int32 m_Money;
```

- `private System.Int32 m_XP`  

```csharp
private System.Int32 m_XP;
```


## Properties

- `public Unity.Entities.Entity City { get }`  

```csharp
public Unity.Entities.Entity City { get; }
```

- `public System.Int32 moneyAmount { get }`  

```csharp
public System.Int32 moneyAmount { get; }
```

- `public System.Int32 XP { get }`  

```csharp
public System.Int32 XP { get; }
```


## Constructors

- `public CitySystem()`  

```csharp
[Preserve]
	public CitySystem()
	{
	}
```


## Methods

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
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_ServiceFeeParameterQuery = GetEntityQuery(ComponentType.ReadOnly<ServiceFeeParameterData>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_City != Entity.Null)
		{
			m_Money = base.EntityManager.GetComponentData<PlayerMoney>(m_City).money;
			m_XP = base.EntityManager.GetComponentData<XP>(m_City).m_XP;
		}
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		EconomyParameterData singleton = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>();
		if (context.purpose == Purpose.NewGame)
		{
			if (m_City == Entity.Null)
			{
				m_City = base.EntityManager.CreateEntity(typeof(Game.City.City));
				base.EntityManager.AddComponentData(m_City, new MilestoneLevel
				{
					m_AchievedMilestone = 0
				});
				base.EntityManager.AddComponentData(m_City, new XP
				{
					m_XP = 0
				});
				base.EntityManager.AddComponentData(m_City, new DevTreePoints
				{
					m_Points = 0
				});
				base.EntityManager.AddBuffer<Policy>(m_City);
				base.EntityManager.AddBuffer<CityModifier>(m_City);
				base.EntityManager.AddComponentData(m_City, default(Loan));
				base.EntityManager.AddComponentData(m_City, default(Creditworthiness));
				base.EntityManager.AddComponentData(m_City, default(DangerLevel));
				base.EntityManager.AddBuffer<TradeCost>(m_City);
				ServiceFeeParameterData singleton2 = m_ServiceFeeParameterQuery.GetSingleton<ServiceFeeParameterData>();
				DynamicBuffer<ServiceFee> dynamicBuffer = base.EntityManager.AddBuffer<ServiceFee>(m_City);
				foreach (ServiceFee defaultFee in singleton2.GetDefaultFees())
				{
					dynamicBuffer.Add(defaultFee);
				}
				base.EntityManager.AddComponentData(m_City, new PlayerMoney(singleton.m_PlayerStartMoney));
				base.EntityManager.AddBuffer<SpecializationBonus>(m_City);
				Population componentData = default(Population);
				componentData.SetDefaults(context);
				base.EntityManager.AddComponentData(m_City, componentData);
				Tourism componentData2 = default(Tourism);
				componentData2.SetDefaults(context);
				base.EntityManager.AddComponentData(m_City, componentData2);
			}
			else
			{
				base.EntityManager.SetComponentData(m_City, new PlayerMoney(singleton.m_PlayerStartMoney));
			}
		}
		if (context.purpose == Purpose.LoadGame && context.version < Version.loanComponent)
		{
			base.EntityManager.AddComponentData(m_City, default(Loan));
			base.EntityManager.AddComponentData(m_City, default(Creditworthiness));
		}
		if (context.purpose == Purpose.NewGame || context.purpose == Purpose.LoadGame)
		{
			PlayerMoney componentData3 = base.EntityManager.GetComponentData<PlayerMoney>(m_City);
			componentData3.m_Unlimited = m_CityConfigurationSystem.unlimitedMoney;
			base.EntityManager.SetComponentData(m_City, componentData3);
			if (base.EntityManager.HasComponent<Resources>(m_City))
			{
				base.EntityManager.RemoveComponent<Resources>(m_City);
			}
		}
		if (context.purpose == Purpose.LoadGame && context.version < Version.dangerLevel)
		{
			base.EntityManager.AddComponentData(m_City, default(DangerLevel));
		}
		if (context.version < Version.cityTradeCost && (context.purpose == Purpose.NewGame || context.purpose == Purpose.LoadGame))
		{
			DynamicBuffer<TradeCost> costs = base.EntityManager.AddBuffer<TradeCost>(m_City);
			ResourceIterator iterator = ResourceIterator.GetIterator();
			ResourcePrefabs prefabs = base.World.GetOrCreateSystemManaged<ResourceSystem>().GetPrefabs();
			int num = 20000;
			while (iterator.Next())
			{
				float num2 = (float)EconomyUtils.GetTransportCost(10000f, iterator.resource, num, base.EntityManager.GetComponentData<ResourceData>(prefabs[iterator.resource]).m_Weight) / (float)num;
				EconomyUtils.SetTradeCost(iterator.resource, new TradeCost
				{
					m_BuyCost = num2,
					m_SellCost = num2,
					m_Resource = iterator.resource
				}, costs, keepLastTime: true);
			}
		}
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
		m_City = Entity.Null;
		m_Money = 0;
	}
```


