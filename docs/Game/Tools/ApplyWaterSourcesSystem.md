# Game.Tools.ApplyWaterSourcesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ApplyWaterSourcesSystem : Game.GameSystemBase
{
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Game.Tools.ApplyWaterSourcesSystem+TypeHandle __TypeHandle;

    public ApplyWaterSourcesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Game.Tools.ApplyWaterSourcesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ApplyWaterSourcesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ApplyWaterSourcesSystem()`  

```csharp
public ApplyWaterSourcesSystem();
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

- `Game.Tools.ApplyWaterSourcesSystem+HandleTempEntitiesJob`  
- `Game.Tools.ApplyWaterSourcesSystem+TypeHandle`  

