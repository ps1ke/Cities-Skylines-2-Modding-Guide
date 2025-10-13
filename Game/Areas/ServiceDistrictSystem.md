# Game.Areas.ServiceDistrictSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ServiceDistrictSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_DeletedDistrictQuery;
    private Unity.Entities.EntityQuery m_ServiceDistrictQuery;
    private Game.Areas.ServiceDistrictSystem+TypeHandle __TypeHandle;

    public ServiceDistrictSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_DeletedDistrictQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedDistrictQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceDistrictQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceDistrictQuery;
```

- `private Game.Areas.ServiceDistrictSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.ServiceDistrictSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ServiceDistrictSystem()`  

```csharp
public ServiceDistrictSystem();
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

- `Game.Areas.ServiceDistrictSystem+RemoveServiceDistrictsJob`  
- `Game.Areas.ServiceDistrictSystem+TypeHandle`  

