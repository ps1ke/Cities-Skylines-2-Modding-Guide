# Game.Effects.CompleteEnabledSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompleteEnabledSystem : Game.GameSystemBase
{
    private Game.Effects.EffectControlSystem m_EffectControlSystem;
    private Game.Effects.VFXSystem m_VFXSystem;
    private Game.Effects.CompleteEnabledSystem+TypeHandle __TypeHandle;

    public CompleteEnabledSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Effects.EffectControlSystem m_EffectControlSystem`  

```csharp
private Game.Effects.EffectControlSystem m_EffectControlSystem;
```

- `private Game.Effects.VFXSystem m_VFXSystem`  

```csharp
private Game.Effects.VFXSystem m_VFXSystem;
```

- `private Game.Effects.CompleteEnabledSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Effects.CompleteEnabledSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CompleteEnabledSystem()`  

```csharp
public CompleteEnabledSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Effects.CompleteEnabledSystem+EffectCleanupJob`  
- `Game.Effects.CompleteEnabledSystem+TypeHandle`  

