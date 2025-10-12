# Game.UI.UISystemBase

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class abstract public  

**Base:** `Game.GameSystemBase`  

## Fields

- `private System.Collections.Generic.List<Colossal.UI.Binding.IBinding> m_Bindings`  
- `private System.Collections.Generic.List<Colossal.UI.Binding.IUpdateBinding> m_UpdateBindings`  
- `protected static Colossal.Logging.ILog log`  

## Properties

- `public Game.GameMode gameMode { get }`  

## Constructors

- `protected UISystemBase()`  

## Methods

- `protected AddBinding(Colossal.UI.Binding.IBinding binding) : System.Void`  
- `protected AddUpdateBinding(Colossal.UI.Binding.IUpdateBinding binding) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

