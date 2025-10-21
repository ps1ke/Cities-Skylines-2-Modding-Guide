# Game.Rendering.InitializeBonesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeBonesSystem : Game.GameSystemBase
{
    private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Rendering.InitializeBonesSystem+TypeHandle __TypeHandle;

    public InitializeBonesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem`  

```csharp
private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Rendering.InitializeBonesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.InitializeBonesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeBonesSystem()`  

```csharp
public InitializeBonesSystem();
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

- `Game.Rendering.InitializeBonesSystem+InitializeBonesJob`  
- `Game.Rendering.InitializeBonesSystem+TypeHandle`  

