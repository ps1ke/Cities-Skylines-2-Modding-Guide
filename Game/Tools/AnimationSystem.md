# Game.Tools.AnimationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AnimationSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_AnimatedQuery;
    private Game.Tools.AnimationSystem+TypeHandle __TypeHandle;

    public AnimationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_AnimatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_AnimatedQuery;
```

- `private Game.Tools.AnimationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.AnimationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AnimationSystem()`  

```csharp
public AnimationSystem();
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

- `Game.Tools.AnimationSystem+AnimateJob`  
- `Game.Tools.AnimationSystem+TypeHandle`  

