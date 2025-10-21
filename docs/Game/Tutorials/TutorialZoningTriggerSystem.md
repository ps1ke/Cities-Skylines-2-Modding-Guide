# Game.Tutorials.TutorialZoningTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialZoningTriggerSystem : Game.Tutorials.TutorialTriggerSystemBase
{
    private Game.Prefabs.ZoneSystem m_ZoneSystem;
    private Unity.Entities.EntityQuery m_CreatedZonesQuery;
    private Unity.Entities.EntityQuery m_ZonesQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Game.Tutorials.TutorialZoningTriggerSystem+TypeHandle __TypeHandle;

    public TutorialZoningTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.ZoneSystem m_ZoneSystem`  

```csharp
private Game.Prefabs.ZoneSystem m_ZoneSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedZonesQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedZonesQuery;
```

- `private Unity.Entities.EntityQuery m_ZonesQuery`  

```csharp
private Unity.Entities.EntityQuery m_ZonesQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Game.Tutorials.TutorialZoningTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialZoningTriggerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialZoningTriggerSystem()`  

```csharp
public TutorialZoningTriggerSystem();
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

- `Game.Tutorials.TutorialZoningTriggerSystem+CheckZonesJob`  
- `Game.Tutorials.TutorialZoningTriggerSystem+TypeHandle`  

