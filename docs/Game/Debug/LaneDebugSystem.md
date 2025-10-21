# Game.Debug.LaneDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_StandaloneOption;
    private Game.Debug.BaseDebugSystem+Option m_SlaveOption;
    private Game.Debug.BaseDebugSystem+Option m_MasterOption;
    private Game.Debug.BaseDebugSystem+Option m_ConnectionOption;
    private Game.Debug.BaseDebugSystem+Option m_OverlapOption;
    private Game.Debug.BaseDebugSystem+Option m_ReservedOption;
    private Game.Debug.BaseDebugSystem+Option m_BlockageOption;
    private Game.Debug.BaseDebugSystem+Option m_ConditionOption;
    private Game.Debug.BaseDebugSystem+Option m_SignalsOption;
    private Game.Debug.BaseDebugSystem+Option m_PriorityOption;
    private Game.Debug.LaneDebugSystem+TypeHandle __TypeHandle;

    public LaneDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_StandaloneOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_StandaloneOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_SlaveOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_SlaveOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_MasterOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_MasterOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ConnectionOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ConnectionOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_OverlapOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_OverlapOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ReservedOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ReservedOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_BlockageOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_BlockageOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ConditionOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ConditionOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_SignalsOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_SignalsOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_PriorityOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_PriorityOption;
```

- `private Game.Debug.LaneDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.LaneDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneDebugSystem()`  

```csharp
public LaneDebugSystem();
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

- `Game.Debug.LaneDebugSystem+LaneGizmoJob`  
- `Game.Debug.LaneDebugSystem+TypeHandle`  

