# Game.Audio.SFXCullingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Audio`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SFXCullingSystem : Game.GameSystemBase
{
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Effects.EffectControlSystem m_EffectControlSystem;
    private Unity.Entities.EntityQuery m_CullingAudioSettingsQuery;
    private Game.Audio.SFXCullingSystem+TypeHandle __TypeHandle;

    public SFXCullingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.Effects.EffectControlSystem m_EffectControlSystem`  

```csharp
private Game.Effects.EffectControlSystem m_EffectControlSystem;
```

- `private Unity.Entities.EntityQuery m_CullingAudioSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_CullingAudioSettingsQuery;
```

- `private Game.Audio.SFXCullingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Audio.SFXCullingSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SFXCullingSystem()`  

```csharp
public SFXCullingSystem();
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

- `Game.Audio.SFXCullingSystem+SFXCullingJob`  
- `Game.Audio.SFXCullingSystem+CullingGroupItem`  
- `Game.Audio.SFXCullingSystem+SFXGroupCullingJob`  
- `Game.Audio.SFXCullingSystem+TypeHandle`  

