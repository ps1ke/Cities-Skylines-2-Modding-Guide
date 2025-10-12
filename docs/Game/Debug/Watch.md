# Game.Debug.DebugWatchSystem+Watch

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Fields

- `public Unity.Entities.ComponentSystemBase m_System`  
- `public System.String m_DisplayName`  
- `public System.String m_Color`  

## Constructors

- `protected Watch()`  

## Methods

- `public abstract Advance(System.UInt32 frameIndex) : System.Boolean`  
- `public abstract Disable() : System.Void`  
- `public abstract Enable() : System.Void`  
- `public static TryCreate(Game.Reflection.IValueAccessor accessor, System.Int32 historyLength, System.Int32 updateInterval) : Game.Debug.DebugWatchSystem+Watch`  
- `public abstract Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

