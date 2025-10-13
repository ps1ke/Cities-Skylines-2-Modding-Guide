# Game.Buildings.CityServiceWorkplaceInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityServiceWorkplaceInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Buildings.CityServiceWorkplaceInitializeSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1169823966_0;

    public CityServiceWorkplaceInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Buildings.CityServiceWorkplaceInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.CityServiceWorkplaceInitializeSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1169823966_0`  

```csharp
private Unity.Entities.EntityQuery __query_1169823966_0;
```


## Constructors

- `public CityServiceWorkplaceInitializeSystem()`  

```csharp
public CityServiceWorkplaceInitializeSystem();
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

- `Game.Buildings.CityServiceWorkplaceInitializeSystem+UpdateWorkplaceJob`  
- `Game.Buildings.CityServiceWorkplaceInitializeSystem+TypeHandle`  

