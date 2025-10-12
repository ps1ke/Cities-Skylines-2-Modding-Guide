# Game.UI.InGame.LoanUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Fields

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_LoanLimitBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.Tools.LoanInfo> m_CurrentLoanBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.Tools.LoanInfo> m_LoanOfferBinding`  
- `private Game.Tools.ILoanSystem m_LoanSystem`  
- `private System.Int32 m_RequestedOfferDifference`  
- `private static const System.String kGroup`  

## Constructors

- `public LoanUISystem()`  

## Methods

- `private <OnCreate>b__6_0() : System.Int32`  
- `private <OnCreate>b__6_1() : Game.Tools.LoanInfo`  
- `private <OnCreate>b__6_2() : Game.Tools.LoanInfo`  
- `private AcceptLoanOffer() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private RequestLoanOffer(System.Int32 amount) : System.Void`  
- `private ResetLoanOffer() : System.Void`  

## Nested types

- `Game.UI.InGame.LoanUISystem+LoanWriter`  

