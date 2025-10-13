# Game.Serialization.SecondaryPrefabReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SecondaryPrefabReferencesSystem : Game.GameSystemBase
{
    private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem;
    private Unity.Entities.EntityQuery m_SpawnableBuildingQuery;
    private Unity.Entities.EntityQuery m_PlaceholderBuildingQuery;
    private Unity.Entities.EntityQuery m_ServiceObjectQuery;
    private Unity.Entities.EntityQuery m_NetLaneQuery;
    private Unity.Entities.EntityQuery m_TransportLineQuery;
    private Unity.Entities.EntityQuery m_ContentPrerequisiteQuery;
    private Game.Serialization.SecondaryPrefabReferencesSystem+TypeHandle __TypeHandle;

    public SecondaryPrefabReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem`  

```csharp
private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem;
```

- `private Unity.Entities.EntityQuery m_SpawnableBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_SpawnableBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_PlaceholderBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlaceholderBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceObjectQuery;
```

- `private Unity.Entities.EntityQuery m_NetLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetLaneQuery;
```

- `private Unity.Entities.EntityQuery m_TransportLineQuery`  

```csharp
private Unity.Entities.EntityQuery m_TransportLineQuery;
```

- `private Unity.Entities.EntityQuery m_ContentPrerequisiteQuery`  

```csharp
private Unity.Entities.EntityQuery m_ContentPrerequisiteQuery;
```

- `private Game.Serialization.SecondaryPrefabReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.SecondaryPrefabReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SecondaryPrefabReferencesSystem()`  

```csharp
public SecondaryPrefabReferencesSystem();
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

- `Game.Serialization.SecondaryPrefabReferencesSystem+FixSpawnableBuildingJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+FixPlaceholderBuildingJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+FixServiceObjectDataJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+FixNetLaneDataJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+FixTransportLineDataJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+FixContentPrerequisiteDataJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+TypeHandle`  

