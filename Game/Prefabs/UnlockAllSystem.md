# Game.Prefabs.UnlockAllSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UnlockAllSystem : Game.GameSystemBase
{
    private Game.Simulation.MilestoneSystem m_MilestoneSystem;
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Game.UI.InGame.UIHighlightSystem m_UIHighlightSystem;
    private Game.UI.InGame.SignatureBuildingUISystem m_SignatureBuildingUISystem;
    private Unity.Entities.EntityQuery m_LockedQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;

    public UnlockAllSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    private System.Void UnlockAllImpl();
}
```


## Fields

- `private Game.Simulation.MilestoneSystem m_MilestoneSystem`  

```csharp
private Game.Simulation.MilestoneSystem m_MilestoneSystem;
```

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Game.UI.InGame.UIHighlightSystem m_UIHighlightSystem`  

```csharp
private Game.UI.InGame.UIHighlightSystem m_UIHighlightSystem;
```

- `private Game.UI.InGame.SignatureBuildingUISystem m_SignatureBuildingUISystem`  

```csharp
private Game.UI.InGame.SignatureBuildingUISystem m_SignatureBuildingUISystem;
```

- `private Unity.Entities.EntityQuery m_LockedQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```


## Constructors

- `public UnlockAllSystem()`  

```csharp
public UnlockAllSystem();
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

- `private UnlockAllImpl() : System.Void`  

```csharp
private System.Void UnlockAllImpl();
```


