# Game.Tools.LoanSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Tools.ILoanSystem`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Unity.Collections.NativeQueue<Game.Tools.LoanAction> m_ActionQueue`  
- `private Unity.Jobs.JobHandle m_ActionQueueWriters`  
- `private Unity.Entities.EntityQuery m_EconomyParametersQuery`  
- `private Game.Tools.LoanSystem+TypeHandle __TypeHandle`  

## Properties

- `public Game.Tools.LoanInfo CurrentLoan { get }`  
- `public System.Int32 Creditworthiness { get }`  

## Constructors

- `public LoanSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public CalculateLoan(System.Int32 amount) : Game.Tools.LoanInfo`  
- `public static CalculateLoan(System.Int32 amount, System.Int32 creditworthiness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Unity.Mathematics.float2 interestRange) : Game.Tools.LoanInfo`  
- `public ChangeLoan(System.Int32 amount) : System.Void`  
- `private ClampLoanAmount(System.Int32 amount) : System.Int32`  
- `public static GetTargetInterest(System.Int32 loanAmount, System.Int32 creditworthiness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects, Unity.Mathematics.float2 interestRange) : System.Single`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public RequestLoanOffer(System.Int32 amount) : Game.Tools.LoanInfo`  

## Nested types

- `Game.Tools.LoanSystem+LoanActionJob`  
- `Game.Tools.LoanSystem+TypeHandle`  

