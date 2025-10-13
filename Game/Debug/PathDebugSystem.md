# Game.Debug.PathDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PathDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_PathGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Debug.BaseDebugSystem+Option m_PersonalCarOption;
    private Game.Debug.BaseDebugSystem+Option m_DeliveryTruckOption;
    private Game.Debug.BaseDebugSystem+Option m_ServiceVehicleOption;
    private Game.Debug.BaseDebugSystem+Option m_ResidentOption;
    private Game.Debug.BaseDebugSystem+Option m_CitizenOption;
    private Game.Debug.BaseDebugSystem+Option m_CompanyOption;
    private Game.Debug.BaseDebugSystem+Option m_RouteOption;
    private Game.Debug.BaseDebugSystem+Option m_DeliveryRequestOption;
    private Game.Debug.BaseDebugSystem+Option m_ServiceRequestOption;
    private Game.Debug.PathDebugSystem+TypeHandle __TypeHandle;

    public PathDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle DrawPathGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PathGroup`  

```csharp
private Unity.Entities.EntityQuery m_PathGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_PersonalCarOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_PersonalCarOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_DeliveryTruckOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_DeliveryTruckOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ServiceVehicleOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ServiceVehicleOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ResidentOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ResidentOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_CitizenOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_CitizenOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_CompanyOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_CompanyOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_RouteOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_RouteOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_DeliveryRequestOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_DeliveryRequestOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ServiceRequestOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ServiceRequestOption;
```

- `private Game.Debug.PathDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.PathDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PathDebugSystem()`  

```csharp
public PathDebugSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private DrawPathGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle DrawPathGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps);
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

- `Game.Debug.PathDebugSystem+PathGizmoJob`  
- `Game.Debug.PathDebugSystem+TypeHandle`  

