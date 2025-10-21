# Game.Policies.ModifiedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ModifiedSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_EffectProviderQuery;
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Unity.Collections.NativeQueue<Game.Policies.ModifiedSystem+PolicyEventInfo> m_PolicyEventInfos;
    private Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData m_DistrictModifierRefreshData;
    private Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData m_BuildingModifierRefreshData;
    private Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData m_RouteModifierRefreshData;
    private Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData m_CityModifierRefreshData;
    private Unity.Entities.Entity m_TicketPricePolicy;
    private Game.Policies.ModifiedSystem+TypeHandle __TypeHandle;

    public ModifiedSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_EffectProviderQuery`  

```csharp
private Unity.Entities.EntityQuery m_EffectProviderQuery;
```

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Unity.Collections.NativeQueue<Game.Policies.ModifiedSystem+PolicyEventInfo> m_PolicyEventInfos`  

```csharp
private Unity.Collections.NativeQueue<Game.Policies.ModifiedSystem+PolicyEventInfo> m_PolicyEventInfos;
```

- `private Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData m_DistrictModifierRefreshData`  

```csharp
private Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData m_DistrictModifierRefreshData;
```

- `private Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData m_BuildingModifierRefreshData`  

```csharp
private Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData m_BuildingModifierRefreshData;
```

- `private Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData m_RouteModifierRefreshData`  

```csharp
private Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData m_RouteModifierRefreshData;
```

- `private Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData m_CityModifierRefreshData`  

```csharp
private Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData m_CityModifierRefreshData;
```

- `private Unity.Entities.Entity m_TicketPricePolicy`  

```csharp
private Unity.Entities.Entity m_TicketPricePolicy;
```

- `private Game.Policies.ModifiedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Policies.ModifiedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ModifiedSystem()`  

```csharp
public ModifiedSystem();
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Policies.ModifiedSystem+PolicyRange`  
- `Game.Policies.ModifiedSystem+PolicyEventInfo`  
- `Game.Policies.ModifiedSystem+ModifyPolicyJob`  
- `Game.Policies.ModifiedSystem+TypeHandle`  

