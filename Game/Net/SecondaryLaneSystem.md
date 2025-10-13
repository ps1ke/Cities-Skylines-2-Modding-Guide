# Game.Net.SecondaryLaneSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SecondaryLaneSystem : Game.GameSystemBase
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_OwnerQuery;
    private Unity.Entities.ComponentTypeSet m_AppliedTypes;
    private Unity.Entities.ComponentTypeSet m_DeletedTempTypes;
    private Unity.Entities.ComponentTypeSet m_HideLaneTypes;
    private Game.Net.SecondaryLaneSystem+TypeHandle __TypeHandle;

    public SecondaryLaneSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_OwnerQuery`  

```csharp
private Unity.Entities.EntityQuery m_OwnerQuery;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedTypes;
```

- `private Unity.Entities.ComponentTypeSet m_DeletedTempTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_DeletedTempTypes;
```

- `private Unity.Entities.ComponentTypeSet m_HideLaneTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_HideLaneTypes;
```

- `private Game.Net.SecondaryLaneSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.SecondaryLaneSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SecondaryLaneSystem()`  

```csharp
public SecondaryLaneSystem();
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

- `Game.Net.SecondaryLaneSystem+LaneKey`  
- `Game.Net.SecondaryLaneSystem+LaneBuffer`  
- `Game.Net.SecondaryLaneSystem+LaneCorner`  
- `Game.Net.SecondaryLaneSystem+CutRange`  
- `Game.Net.SecondaryLaneSystem+CrossingLane`  
- `Game.Net.SecondaryLaneSystem+UpdateLanesJob`  
- `Game.Net.SecondaryLaneSystem+TypeHandle`  

