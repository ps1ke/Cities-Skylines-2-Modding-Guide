# Game.Notifications.IconAnimationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class IconAnimationSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_AnimationQuery;
    private Game.Notifications.IconAnimationSystem+TypeHandle __TypeHandle;

    public IconAnimationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_AnimationQuery`  

```csharp
private Unity.Entities.EntityQuery m_AnimationQuery;
```

- `private Game.Notifications.IconAnimationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Notifications.IconAnimationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public IconAnimationSystem()`  

```csharp
public IconAnimationSystem();
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

- `Game.Notifications.IconAnimationSystem+IconAnimationJob`  
- `Game.Notifications.IconAnimationSystem+TypeHandle`  

