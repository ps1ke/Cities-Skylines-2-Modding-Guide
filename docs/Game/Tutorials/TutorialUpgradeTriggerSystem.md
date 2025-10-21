# Game.Tutorials.TutorialUpgradeTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  

## Code

```csharp
public class TutorialUpgradeTriggerSystem : Game.Tutorials.TutorialTriggerSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedUpgradeQuery;
    private Unity.Entities.EntityQuery m_UpgradeQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;

    public TutorialUpgradeTriggerSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedUpgradeQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedUpgradeQuery;
```

- `private Unity.Entities.EntityQuery m_UpgradeQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpgradeQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```


## Constructors

- `public TutorialUpgradeTriggerSystem()`  

```csharp
public TutorialUpgradeTriggerSystem();
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


