# Game.Tools.ValidationSystem+Components

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class Components : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Common.ModificationEndBarrier m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_ComponentQuery;
    public Unity.Collections.NativeHashMap<Unity.Entities.Entity, Game.Tools.ErrorSeverity> m_ErrorMap;
    public Unity.Jobs.JobHandle m_ErrorMapDeps;
    private Game.Tools.ValidationSystem+Components+TypeHandle __TypeHandle;

    public Components();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_ComponentQuery`  

```csharp
private Unity.Entities.EntityQuery m_ComponentQuery;
```

- `public Unity.Collections.NativeHashMap<Unity.Entities.Entity, Game.Tools.ErrorSeverity> m_ErrorMap`  

```csharp
public Unity.Collections.NativeHashMap<Unity.Entities.Entity, Game.Tools.ErrorSeverity> m_ErrorMap;
```

- `public Unity.Jobs.JobHandle m_ErrorMapDeps`  

```csharp
public Unity.Jobs.JobHandle m_ErrorMapDeps;
```

- `private Game.Tools.ValidationSystem+Components+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ValidationSystem+Components+TypeHandle __TypeHandle;
```


## Constructors

- `public Components()`  

```csharp
public Components();
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

- `Game.Tools.ValidationSystem+Components+UpdateComponentsJob`  
- `Game.Tools.ValidationSystem+Components+TypeHandle`  

