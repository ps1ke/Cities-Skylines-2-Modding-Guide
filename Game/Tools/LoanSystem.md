# Game.Tools.LoanSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Tools.ILoanSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LoanSystem : Game.GameSystemBase, Game.Tools.ILoanSystem
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Collections.NativeQueue<Game.Tools.LoanAction> m_ActionQueue;
    private Unity.Jobs.JobHandle m_ActionQueueWriters;
    private Unity.Entities.EntityQuery m_EconomyParametersQuery;
    private Game.Tools.LoanSystem+TypeHandle __TypeHandle;

    public Game.Tools.LoanInfo CurrentLoan { get; }
    public System.Int32 Creditworthiness { get; }

    public LoanSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Game.Tools.LoanInfo CalculateLoan(System.Int32 amount);
    public static Game.Tools.LoanInfo CalculateLoan(System.Int32 amount, System.Int32 creditworthiness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Unity.Mathematics.float2 interestRange);
    public System.Void ChangeLoan(System.Int32 amount);
    private System.Int32 ClampLoanAmount(System.Int32 amount);
    public static System.Single GetTargetInterest(System.Int32 loanAmount, System.Int32 creditworthiness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects, Unity.Mathematics.float2 interestRange);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public Game.Tools.LoanInfo RequestLoanOffer(System.Int32 amount);
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Collections.NativeQueue<Game.Tools.LoanAction> m_ActionQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Tools.LoanAction> m_ActionQueue;
```

- `private Unity.Jobs.JobHandle m_ActionQueueWriters`  

```csharp
private Unity.Jobs.JobHandle m_ActionQueueWriters;
```

- `private Unity.Entities.EntityQuery m_EconomyParametersQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParametersQuery;
```

- `private Game.Tools.LoanSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.LoanSystem+TypeHandle __TypeHandle;
```


## Properties

- `public Game.Tools.LoanInfo CurrentLoan { get }`  

```csharp
public Game.Tools.LoanInfo CurrentLoan { get; }
```

- `public System.Int32 Creditworthiness { get }`  

```csharp
public System.Int32 Creditworthiness { get; }
```


## Constructors

- `public LoanSystem()`  

```csharp
[Preserve]
	public LoanSystem()
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

- `public CalculateLoan(System.Int32 amount) : Game.Tools.LoanInfo`  

```csharp
public static LoanInfo CalculateLoan(int amount, int creditworthiness, DynamicBuffer<CityModifier> modifiers, float2 interestRange)
	{
		if (amount > 0)
		{
			float targetInterest = GetTargetInterest(amount, creditworthiness, modifiers, interestRange);
			return new LoanInfo
			{
				m_Amount = amount,
				m_DailyInterestRate = targetInterest,
				m_DailyPayment = Mathf.RoundToInt((float)amount * targetInterest)
			};
		}
		return default(LoanInfo);
	}
```

- `public static CalculateLoan(System.Int32 amount, System.Int32 creditworthiness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Unity.Mathematics.float2 interestRange) : Game.Tools.LoanInfo`  

```csharp
public static LoanInfo CalculateLoan(int amount, int creditworthiness, DynamicBuffer<CityModifier> modifiers, float2 interestRange)
	{
		if (amount > 0)
		{
			float targetInterest = GetTargetInterest(amount, creditworthiness, modifiers, interestRange);
			return new LoanInfo
			{
				m_Amount = amount,
				m_DailyInterestRate = targetInterest,
				m_DailyPayment = Mathf.RoundToInt((float)amount * targetInterest)
			};
		}
		return default(LoanInfo);
	}
```

- `public ChangeLoan(System.Int32 amount) : System.Void`  

```csharp
public void ChangeLoan(int amount)
	{
		m_ActionQueueWriters.Complete();
		m_ActionQueue.Enqueue(new LoanAction
		{
			m_Amount = ClampLoanAmount(amount)
		});
	}
```

- `private ClampLoanAmount(System.Int32 amount) : System.Int32`  

```csharp
private int ClampLoanAmount(int amount)
	{
		PlayerMoney componentData = base.EntityManager.GetComponentData<PlayerMoney>(m_CitySystem.City);
		int lowerBound = math.max(0, CurrentLoan.m_Amount - math.max(0, componentData.money));
		return math.clamp(amount, lowerBound, Creditworthiness);
	}
```

- `public static GetTargetInterest(System.Int32 loanAmount, System.Int32 creditworthiness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects, Unity.Mathematics.float2 interestRange) : System.Single`  

```csharp
public static float GetTargetInterest(int loanAmount, int creditworthiness, DynamicBuffer<CityModifier> cityEffects, float2 interestRange)
	{
		float value = 100f * math.lerp(interestRange.x, interestRange.y, math.saturate((float)loanAmount / math.max(1f, creditworthiness)));
		CityUtils.ApplyModifier(ref value, cityEffects, CityModifierType.LoanInterest);
		return math.max(0f, 0.01f * value);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EconomyParametersQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ActionQueue = new NativeQueue<LoanAction>(Allocator.Persistent);
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
		m_ActionQueue.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_ActionQueue.IsEmpty())
		{
			LoanActionJob jobData = new LoanActionJob
			{
				m_City = m_CitySystem.City,
				m_SimulationFrameIndex = m_SimulationSystem.frameIndex,
				m_ActionQueue = m_ActionQueue,
				m_Loans = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_Loan_RW_ComponentLookup, ref base.CheckedStateRef),
				m_Money = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_PlayerMoney_RW_ComponentLookup, ref base.CheckedStateRef)
			};
			base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(m_ActionQueueWriters, base.Dependency));
			m_ActionQueueWriters = base.Dependency;
		}
	}
```

- `public RequestLoanOffer(System.Int32 amount) : Game.Tools.LoanInfo`  

```csharp
public LoanInfo RequestLoanOffer(int amount)
	{
		return CalculateLoan(ClampLoanAmount(amount));
	}
```


## Nested types

- `Game.Tools.LoanSystem+LoanActionJob`  
- `Game.Tools.LoanSystem+TypeHandle`  

