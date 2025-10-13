# Game.Tools.AnimationUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AnimationUpdateSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_AnimatedQuery;
    private Game.Tools.AnimationUpdateSystem+TypeHandle __TypeHandle;

    public AnimationUpdateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_AnimatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_AnimatedQuery;
```

- `private Game.Tools.AnimationUpdateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.AnimationUpdateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AnimationUpdateSystem()`  

```csharp
public AnimationUpdateSystem();
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

- `Game.Tools.AnimationUpdateSystem+AnimationMapJob`  
- `Game.Tools.AnimationUpdateSystem+AnimationUpdateJob`  
- `Game.Tools.AnimationUpdateSystem+TypeHandle`  

