# Game.Citizens.HouseholdAndCitizenRemoveSystem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdAndCitizenRemoveSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_DeletedQuery;
    private Unity.Entities.EntityArchetype m_RentEventArchetype;
    private Game.Common.ModificationBarrier2 m_ModificationBarrier;
    private Game.Citizens.HouseholdAndCitizenRemoveSystem+TypeHandle __TypeHandle;

    public HouseholdAndCitizenRemoveSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_DeletedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedQuery;
```

- `private Unity.Entities.EntityArchetype m_RentEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_RentEventArchetype;
```

- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2 m_ModificationBarrier;
```

- `private Game.Citizens.HouseholdAndCitizenRemoveSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Citizens.HouseholdAndCitizenRemoveSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HouseholdAndCitizenRemoveSystem()`  

```csharp
public HouseholdAndCitizenRemoveSystem();
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

- `Game.Citizens.HouseholdAndCitizenRemoveSystem+HouseholdAndCitizenRemoveJob`  
- `Game.Citizens.HouseholdAndCitizenRemoveSystem+TypeHandle`  

