# Game.Tutorials.TutorialHealthProblemActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialHealthProblemActivationSystem : Game.GameSystemBase
{
    protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
    private Unity.Entities.EntityQuery m_TutorialQuery;
    private Unity.Entities.EntityQuery m_HealthProblemQuery;
    private Unity.Entities.EntityQuery m_MedicalClinicQuery;
    private Unity.Entities.EntityQuery m_MedicalClinicUnlockedQuery;
    private Unity.Entities.EntityQuery m_CemeteryQuery;
    private Unity.Entities.EntityQuery m_CemeteryUnlockedQuery;
    private Game.Tutorials.TutorialHealthProblemActivationSystem+TypeHandle __TypeHandle;

    public TutorialHealthProblemActivationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem`  

```csharp
protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
```

- `private Unity.Entities.EntityQuery m_TutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_TutorialQuery;
```

- `private Unity.Entities.EntityQuery m_HealthProblemQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthProblemQuery;
```

- `private Unity.Entities.EntityQuery m_MedicalClinicQuery`  

```csharp
private Unity.Entities.EntityQuery m_MedicalClinicQuery;
```

- `private Unity.Entities.EntityQuery m_MedicalClinicUnlockedQuery`  

```csharp
private Unity.Entities.EntityQuery m_MedicalClinicUnlockedQuery;
```

- `private Unity.Entities.EntityQuery m_CemeteryQuery`  

```csharp
private Unity.Entities.EntityQuery m_CemeteryQuery;
```

- `private Unity.Entities.EntityQuery m_CemeteryUnlockedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CemeteryUnlockedQuery;
```

- `private Game.Tutorials.TutorialHealthProblemActivationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialHealthProblemActivationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialHealthProblemActivationSystem()`  

```csharp
public TutorialHealthProblemActivationSystem();
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

- `Game.Tutorials.TutorialHealthProblemActivationSystem+CheckProblemsJob`  
- `Game.Tutorials.TutorialHealthProblemActivationSystem+TypeHandle`  

