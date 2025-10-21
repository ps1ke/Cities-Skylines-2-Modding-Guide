# Game.Rendering.InitializeAnimatedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeAnimatedSystem : Game.GameSystemBase
{
    private Game.Rendering.AnimatedSystem m_AnimatedSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Rendering.InitializeAnimatedSystem+TypeHandle __TypeHandle;

    public InitializeAnimatedSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.AnimatedSystem m_AnimatedSystem`  

```csharp
private Game.Rendering.AnimatedSystem m_AnimatedSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Rendering.InitializeAnimatedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.InitializeAnimatedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeAnimatedSystem()`  

```csharp
public InitializeAnimatedSystem();
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

- `Game.Rendering.InitializeAnimatedSystem+InitializeAnimatedJob`  
- `Game.Rendering.InitializeAnimatedSystem+OverlayIndex`  
- `Game.Rendering.InitializeAnimatedSystem+TypeHandle`  

