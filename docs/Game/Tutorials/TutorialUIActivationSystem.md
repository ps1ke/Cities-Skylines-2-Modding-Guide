# Game.Tutorials.TutorialUIActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Tutorials.ITutorialUIActivationSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialUIActivationSystem : Game.GameSystemBase, Game.Tutorials.ITutorialUIActivationSystem
{
    protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
    private readonly System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Unity.Entities.Entity>> m_TutorialMap;
    private readonly System.Collections.Generic.List<System.String> m_ActiveTags;
    private Unity.Entities.EntityQuery m_TutorialQuery;

    public TutorialUIActivationSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void RebuildTutorialMap();
    public System.Void SetTag(System.String tag, System.Boolean active);
}
```


## Fields

- `protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem`  

```csharp
protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Unity.Entities.Entity>> m_TutorialMap`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Unity.Entities.Entity>> m_TutorialMap;
```

- `private readonly System.Collections.Generic.List<System.String> m_ActiveTags`  

```csharp
private readonly System.Collections.Generic.List<System.String> m_ActiveTags;
```

- `private Unity.Entities.EntityQuery m_TutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_TutorialQuery;
```


## Constructors

- `public TutorialUIActivationSystem()`  

```csharp
public TutorialUIActivationSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private RebuildTutorialMap() : System.Void`  

```csharp
private System.Void RebuildTutorialMap();
```

- `public SetTag(System.String tag, System.Boolean active) : System.Void`  

```csharp
public System.Void SetTag(System.String tag, System.Boolean active);
```


