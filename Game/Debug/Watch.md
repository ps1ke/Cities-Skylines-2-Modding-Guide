# Game.Debug.DebugWatchSystem+Watch

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public abstract class Watch : Colossal.UI.Binding.IJsonWritable
{
    public Unity.Entities.ComponentSystemBase m_System;
    public System.String m_DisplayName;
    public System.String m_Color;

    protected Watch();

    public abstract System.Boolean Advance(System.UInt32 frameIndex);
    public abstract System.Void Disable();
    public abstract System.Void Enable();
    public static Game.Debug.DebugWatchSystem+Watch TryCreate(Game.Reflection.IValueAccessor accessor, System.Int32 historyLength, System.Int32 updateInterval);
    public abstract System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public Unity.Entities.ComponentSystemBase m_System`  

```csharp
public Unity.Entities.ComponentSystemBase m_System;
```

- `public System.String m_DisplayName`  

```csharp
public System.String m_DisplayName;
```

- `public System.String m_Color`  

```csharp
public System.String m_Color;
```


## Constructors

- `protected Watch()`  

```csharp
protected Watch();
```


## Methods

- `public abstract Advance(System.UInt32 frameIndex) : System.Boolean`  

```csharp
public abstract System.Boolean Advance(System.UInt32 frameIndex);
```

- `public abstract Disable() : System.Void`  

```csharp
public abstract System.Void Disable();
```

- `public abstract Enable() : System.Void`  

```csharp
public abstract System.Void Enable();
```

- `public static TryCreate(Game.Reflection.IValueAccessor accessor, System.Int32 historyLength, System.Int32 updateInterval) : Game.Debug.DebugWatchSystem+Watch`  

```csharp
public static Game.Debug.DebugWatchSystem+Watch TryCreate(Game.Reflection.IValueAccessor accessor, System.Int32 historyLength, System.Int32 updateInterval);
```

- `public abstract Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public abstract System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


