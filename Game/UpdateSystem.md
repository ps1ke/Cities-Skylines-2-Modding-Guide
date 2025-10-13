# Game.UpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class UpdateSystem : Game.GameSystemBase
{
    private System.Collections.Generic.List<Game.IGPUSystem> m_GPUSystems;
    private System.Collections.Generic.List<Game.UpdateSystem+SystemData> m_Systems;
    private System.Collections.Generic.List<Game.UpdateSystem+SystemData> m_Updates;
    private System.Collections.Generic.List<Unity.Mathematics.int2> m_UpdateRanges;
    private System.Collections.Generic.Dictionary<Unity.Entities.ComponentSystemBase, System.Collections.Generic.List<Game.UpdateSystem+SystemData>> m_RefMap;
    private System.Int32 m_AddIndex;
    private System.Boolean m_IsDirty;
    private Game.SystemUpdatePhase <currentPhase>k__BackingField;

    public Game.SystemUpdatePhase currentPhase { get; private set; }

    public UpdateSystem();

    private System.Void AddSystemUpdate(System.Collections.Generic.List<Game.UpdateSystem+IntervalData> intervalList, Game.UpdateSystem+SystemData systemData, System.Boolean inheritOffset, System.Int32 safety);
    public static System.Void GetInterval(Unity.Entities.ComponentSystemBase system, Game.SystemUpdatePhase phase, System.Int32& interval, System.Int32& offset);
    protected virtual System.Void OnBeginFrame(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Camera[] cameras);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void PatchSystemOffset(System.Int32& updateIndex, Game.UpdateSystem+SystemData systemData, System.Boolean inheritOffset, System.Int32 safety);
    private System.Void Refresh();
    private System.Void Register(System.Int32 addIndex, Unity.Entities.ComponentSystemBase system, Game.SystemUpdatePhase phase);
    private System.Void Register(System.Int32 addIndex, Unity.Entities.ComponentSystemBase system, Unity.Entities.ComponentSystemBase other, Game.SystemUpdatePhase phase);
    public System.Void RegisterGPUSystem<SystemType>();
    public System.Void RegisterGPUSystem(Game.IGPUSystem system);
    public System.Void Update(Game.SystemUpdatePhase phase);
    public System.Void Update(Game.SystemUpdatePhase phase, System.UInt32 updateIndex, System.Int32 iterationIndex);
    public System.Void UpdateAfter<SystemType>(Game.SystemUpdatePhase phase);
    public System.Void UpdateAfter<SystemType, OtherType>(Game.SystemUpdatePhase phase);
    public System.Void UpdateAt<SystemType>(Game.SystemUpdatePhase phase);
    public System.Void UpdateBefore<SystemType>(Game.SystemUpdatePhase phase);
    public System.Void UpdateBefore<SystemType, OtherType>(Game.SystemUpdatePhase phase);
}
```


## Fields

- `private System.Collections.Generic.List<Game.IGPUSystem> m_GPUSystems`  

```csharp
private System.Collections.Generic.List<Game.IGPUSystem> m_GPUSystems;
```

- `private System.Collections.Generic.List<Game.UpdateSystem+SystemData> m_Systems`  

```csharp
private System.Collections.Generic.List<Game.UpdateSystem+SystemData> m_Systems;
```

- `private System.Collections.Generic.List<Game.UpdateSystem+SystemData> m_Updates`  

```csharp
private System.Collections.Generic.List<Game.UpdateSystem+SystemData> m_Updates;
```

- `private System.Collections.Generic.List<Unity.Mathematics.int2> m_UpdateRanges`  

```csharp
private System.Collections.Generic.List<Unity.Mathematics.int2> m_UpdateRanges;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.ComponentSystemBase, System.Collections.Generic.List<Game.UpdateSystem+SystemData>> m_RefMap`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.ComponentSystemBase, System.Collections.Generic.List<Game.UpdateSystem+SystemData>> m_RefMap;
```

- `private System.Int32 m_AddIndex`  

```csharp
private System.Int32 m_AddIndex;
```

- `private System.Boolean m_IsDirty`  

```csharp
private System.Boolean m_IsDirty;
```

- `private Game.SystemUpdatePhase <currentPhase>k__BackingField`  

```csharp
private Game.SystemUpdatePhase <currentPhase>k__BackingField;
```


## Properties

- `public Game.SystemUpdatePhase currentPhase { get; private set }`  

```csharp
public Game.SystemUpdatePhase currentPhase { get; private set; }
```


## Constructors

- `public UpdateSystem()`  

```csharp
public UpdateSystem();
```


## Methods

- `private AddSystemUpdate(System.Collections.Generic.List<Game.UpdateSystem+IntervalData> intervalList, Game.UpdateSystem+SystemData systemData, System.Boolean inheritOffset, System.Int32 safety) : System.Void`  

```csharp
private System.Void AddSystemUpdate(System.Collections.Generic.List<Game.UpdateSystem+IntervalData> intervalList, Game.UpdateSystem+SystemData systemData, System.Boolean inheritOffset, System.Int32 safety);
```

- `public static GetInterval(Unity.Entities.ComponentSystemBase system, Game.SystemUpdatePhase phase, System.Int32& interval, System.Int32& offset) : System.Void`  

```csharp
public static System.Void GetInterval(Unity.Entities.ComponentSystemBase system, Game.SystemUpdatePhase phase, System.Int32& interval, System.Int32& offset);
```

- `protected virtual OnBeginFrame(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Camera[] cameras) : System.Void`  

```csharp
protected virtual System.Void OnBeginFrame(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Camera[] cameras);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private PatchSystemOffset(System.Int32& updateIndex, Game.UpdateSystem+SystemData systemData, System.Boolean inheritOffset, System.Int32 safety) : System.Void`  

```csharp
private System.Void PatchSystemOffset(System.Int32& updateIndex, Game.UpdateSystem+SystemData systemData, System.Boolean inheritOffset, System.Int32 safety);
```

- `private Refresh() : System.Void`  

```csharp
private System.Void Refresh();
```

- `private Register(System.Int32 addIndex, Unity.Entities.ComponentSystemBase system, Game.SystemUpdatePhase phase) : System.Void`  

```csharp
private System.Void Register(System.Int32 addIndex, Unity.Entities.ComponentSystemBase system, Game.SystemUpdatePhase phase);
```

- `private Register(System.Int32 addIndex, Unity.Entities.ComponentSystemBase system, Unity.Entities.ComponentSystemBase other, Game.SystemUpdatePhase phase) : System.Void`  

```csharp
private System.Void Register(System.Int32 addIndex, Unity.Entities.ComponentSystemBase system, Unity.Entities.ComponentSystemBase other, Game.SystemUpdatePhase phase);
```

- `public RegisterGPUSystem<SystemType>() : System.Void`  

```csharp
public System.Void RegisterGPUSystem<SystemType>();
```

- `public RegisterGPUSystem(Game.IGPUSystem system) : System.Void`  

```csharp
public System.Void RegisterGPUSystem(Game.IGPUSystem system);
```

- `public Update(Game.SystemUpdatePhase phase) : System.Void`  

```csharp
public System.Void Update(Game.SystemUpdatePhase phase);
```

- `public Update(Game.SystemUpdatePhase phase, System.UInt32 updateIndex, System.Int32 iterationIndex) : System.Void`  

```csharp
public System.Void Update(Game.SystemUpdatePhase phase, System.UInt32 updateIndex, System.Int32 iterationIndex);
```

- `public UpdateAfter<SystemType>(Game.SystemUpdatePhase phase) : System.Void`  

```csharp
public System.Void UpdateAfter<SystemType>(Game.SystemUpdatePhase phase);
```

- `public UpdateAfter<SystemType, OtherType>(Game.SystemUpdatePhase phase) : System.Void`  

```csharp
public System.Void UpdateAfter<SystemType, OtherType>(Game.SystemUpdatePhase phase);
```

- `public UpdateAt<SystemType>(Game.SystemUpdatePhase phase) : System.Void`  

```csharp
public System.Void UpdateAt<SystemType>(Game.SystemUpdatePhase phase);
```

- `public UpdateBefore<SystemType>(Game.SystemUpdatePhase phase) : System.Void`  

```csharp
public System.Void UpdateBefore<SystemType>(Game.SystemUpdatePhase phase);
```

- `public UpdateBefore<SystemType, OtherType>(Game.SystemUpdatePhase phase) : System.Void`  

```csharp
public System.Void UpdateBefore<SystemType, OtherType>(Game.SystemUpdatePhase phase);
```


## Nested types

- `Game.UpdateSystem+SystemData`  
- `Game.UpdateSystem+IntervalData`  

