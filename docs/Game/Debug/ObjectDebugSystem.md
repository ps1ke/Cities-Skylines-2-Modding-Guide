# Game.Debug.ObjectDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObjectDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_ObjectGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Debug.BaseDebugSystem+Option m_GeometryOption;
    private Game.Debug.BaseDebugSystem+Option m_MarkerOption;
    private Game.Debug.BaseDebugSystem+Option m_PivotOption;
    private Game.Debug.BaseDebugSystem+Option m_OutlineOption;
    private Game.Debug.BaseDebugSystem+Option m_InterpolatedOption;
    private Game.Debug.BaseDebugSystem+Option m_NetConnectionOption;
    private Game.Debug.BaseDebugSystem+Option m_GroupConnectionOption;
    private Game.Debug.BaseDebugSystem+Option m_DistrictOption;
    private Game.Debug.BaseDebugSystem+Option m_LotHeightOption;
    private Game.Debug.ObjectDebugSystem+TypeHandle __TypeHandle;

    public ObjectDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle DrawObjectGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ObjectGroup`  

```csharp
private Unity.Entities.EntityQuery m_ObjectGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_GeometryOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_GeometryOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_MarkerOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_MarkerOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_PivotOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_PivotOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_OutlineOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_OutlineOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_InterpolatedOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_InterpolatedOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_NetConnectionOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_NetConnectionOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_GroupConnectionOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_GroupConnectionOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_DistrictOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_DistrictOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_LotHeightOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_LotHeightOption;
```

- `private Game.Debug.ObjectDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.ObjectDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ObjectDebugSystem()`  

```csharp
public ObjectDebugSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private DrawObjectGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle DrawObjectGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps);
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

- `Game.Debug.ObjectDebugSystem+ObjectGizmoJob`  
- `Game.Debug.ObjectDebugSystem+TypeHandle`  

