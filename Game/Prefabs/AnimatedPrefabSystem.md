# Game.Prefabs.AnimatedPrefabSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AnimatedPrefabSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.AnimatedSystem m_AnimatedSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.Prefabs.AnimatedPrefabSystem+TypeHandle __TypeHandle;

    public AnimatedPrefabSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CleanUpRootMotion(Game.Prefabs.CharacterStyle+AnimationMotion[] source, Unity.Collections.NativeArray<Game.Prefabs.AnimationMotion> target);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.AnimatedSystem m_AnimatedSystem`  

```csharp
private Game.Rendering.AnimatedSystem m_AnimatedSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.Prefabs.AnimatedPrefabSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.AnimatedPrefabSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AnimatedPrefabSystem()`  

```csharp
public AnimatedPrefabSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private CleanUpRootMotion(Game.Prefabs.CharacterStyle+AnimationMotion[] source, Unity.Collections.NativeArray<Game.Prefabs.AnimationMotion> target) : System.Void`  

```csharp
private System.Void CleanUpRootMotion(Game.Prefabs.CharacterStyle+AnimationMotion[] source, Unity.Collections.NativeArray<Game.Prefabs.AnimationMotion> target);
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

- `Game.Prefabs.AnimatedPrefabSystem+TypeHandle`  

