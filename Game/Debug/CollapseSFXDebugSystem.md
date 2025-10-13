# Game.Debug.CollapseSFXDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CollapseSFXDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_BuildingEffectGroup;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Colossal.GizmosSystem m_GizmosSystem;

    public CollapseSFXDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BuildingEffectGroup`  

```csharp
private Unity.Entities.EntityQuery m_BuildingEffectGroup;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```


## Constructors

- `public CollapseSFXDebugSystem()`  

```csharp
public CollapseSFXDebugSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Debug.CollapseSFXDebugSystem+CollapseSfxCoverageGizmoJob`  

