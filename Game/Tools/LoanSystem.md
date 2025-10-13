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
public LoanSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public CalculateLoan(System.Int32 amount) : Game.Tools.LoanInfo`  

```csharp
public Game.Tools.LoanInfo CalculateLoan(System.Int32 amount);
```

- `public static CalculateLoan(System.Int32 amount, System.Int32 creditworthiness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Unity.Mathematics.float2 interestRange) : Game.Tools.LoanInfo`  

```csharp
public static Game.Tools.LoanInfo CalculateLoan(System.Int32 amount, System.Int32 creditworthiness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Unity.Mathematics.float2 interestRange);
```

- `public ChangeLoan(System.Int32 amount) : System.Void`  

```csharp
public System.Void ChangeLoan(System.Int32 amount);
```

- `private ClampLoanAmount(System.Int32 amount) : System.Int32`  

```csharp
private System.Int32 ClampLoanAmount(System.Int32 amount);
```

- `public static GetTargetInterest(System.Int32 loanAmount, System.Int32 creditworthiness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects, Unity.Mathematics.float2 interestRange) : System.Single`  

```csharp
public static System.Single GetTargetInterest(System.Int32 loanAmount, System.Int32 creditworthiness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects, Unity.Mathematics.float2 interestRange);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public RequestLoanOffer(System.Int32 amount) : Game.Tools.LoanInfo`  

```csharp
public Game.Tools.LoanInfo RequestLoanOffer(System.Int32 amount);
```


## Nested types

- `Game.Tools.LoanSystem+LoanActionJob`  
- `Game.Tools.LoanSystem+TypeHandle`  

