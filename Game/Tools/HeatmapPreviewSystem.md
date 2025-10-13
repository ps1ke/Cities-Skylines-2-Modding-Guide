# Game.Tools.HeatmapPreviewSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class HeatmapPreviewSystem : Game.GameSystemBase
{
    private Game.Tools.TelecomPreviewSystem m_TelecomPreviewSystem;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Unity.Entities.ComponentSystemBase m_LastPreviewSystem;

    public HeatmapPreviewSystem();

    private Unity.Entities.ComponentSystemBase GetPreviewSystem();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.TelecomPreviewSystem m_TelecomPreviewSystem`  

```csharp
private Game.Tools.TelecomPreviewSystem m_TelecomPreviewSystem;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Unity.Entities.ComponentSystemBase m_LastPreviewSystem`  

```csharp
private Unity.Entities.ComponentSystemBase m_LastPreviewSystem;
```


## Constructors

- `public HeatmapPreviewSystem()`  

```csharp
public HeatmapPreviewSystem();
```


## Methods

- `private GetPreviewSystem() : Unity.Entities.ComponentSystemBase`  

```csharp
private Unity.Entities.ComponentSystemBase GetPreviewSystem();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


