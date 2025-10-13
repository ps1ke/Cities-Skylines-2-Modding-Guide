# Game.Serialization.BeginPrefabSerializationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BeginPrefabSerializationSystem : Game.GameSystemBase
{
    private Game.Serialization.SaveGameSystem m_SaveGameSystem;
    private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem;
    private Game.UpdateSystem m_UpdateSystem;
    private Unity.Entities.EntityQuery m_EnabledPrefabsQuery;
    private Unity.Entities.EntityQuery m_LoadedPrefabsQuery;
    private Game.Serialization.BeginPrefabSerializationSystem+TypeHandle __TypeHandle;

    public BeginPrefabSerializationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.SaveGameSystem m_SaveGameSystem`  

```csharp
private Game.Serialization.SaveGameSystem m_SaveGameSystem;
```

- `private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem`  

```csharp
private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Unity.Entities.EntityQuery m_EnabledPrefabsQuery`  

```csharp
private Unity.Entities.EntityQuery m_EnabledPrefabsQuery;
```

- `private Unity.Entities.EntityQuery m_LoadedPrefabsQuery`  

```csharp
private Unity.Entities.EntityQuery m_LoadedPrefabsQuery;
```

- `private Game.Serialization.BeginPrefabSerializationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.BeginPrefabSerializationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BeginPrefabSerializationSystem()`  

```csharp
public BeginPrefabSerializationSystem();
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

- `Game.Serialization.BeginPrefabSerializationSystem+BeginPrefabSerializationJob`  
- `Game.Serialization.BeginPrefabSerializationSystem+CheckSavedPrefabsJob`  
- `Game.Serialization.BeginPrefabSerializationSystem+SetPrefabDataIndexJob`  
- `Game.Serialization.BeginPrefabSerializationSystem+TypeHandle`  

