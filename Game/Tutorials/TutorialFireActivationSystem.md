# Game.Tutorials.TutorialFireActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class TutorialFireActivationSystem : Game.GameSystemBase
{
    protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
    private Unity.Entities.EntityQuery m_BuildingFireQuery;
    private Unity.Entities.EntityQuery m_ForestFireQuery;
    private Unity.Entities.EntityQuery m_BuildingFireTutorialQuery;
    private Unity.Entities.EntityQuery m_ForestFireTutorialQuery;

    public TutorialFireActivationSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem`  

```csharp
protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
```

- `private Unity.Entities.EntityQuery m_BuildingFireQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingFireQuery;
```

- `private Unity.Entities.EntityQuery m_ForestFireQuery`  

```csharp
private Unity.Entities.EntityQuery m_ForestFireQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingFireTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingFireTutorialQuery;
```

- `private Unity.Entities.EntityQuery m_ForestFireTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_ForestFireTutorialQuery;
```


## Constructors

- `public TutorialFireActivationSystem()`  

```csharp
public TutorialFireActivationSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


