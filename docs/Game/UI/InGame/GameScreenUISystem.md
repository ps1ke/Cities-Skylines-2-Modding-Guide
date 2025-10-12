# Game.UI.InGame.GameScreenUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Fields

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.GameScreenUISystem+GameScreen> m_ActiveScreenBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_CanUseSaveSystem`  
- `private static const System.String kSavingGameNotificationTitle`  
- `private static const System.String kGroup`  

## Properties

- `public Game.UI.InGame.GameScreenUISystem+GameScreen activeScreen { get; set }`  
- `public System.Boolean isMenuActive { get }`  

## Constructors

- `public GameScreenUISystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private SaveLoadInProgress(System.String name, System.Boolean start) : System.Void`  
- `public SetScreen(Game.UI.InGame.GameScreenUISystem+GameScreen screen) : System.Void`  

## Nested types

- `Game.UI.InGame.GameScreenUISystem+GameScreen`  

