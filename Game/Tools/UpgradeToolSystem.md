# Game.Tools.UpgradeToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ObjectToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpgradeToolSystem : Game.Tools.ObjectToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Audio.AudioManager m_AudioManager;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Unity.Entities.EntityQuery m_ContainerQuery;
    private Unity.Entities.Entity m_UpgradingObject;
    private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
    private Game.Common.RandomSeed m_RandomSeed;
    private System.Boolean m_AlreadyCreated;
    private Game.Prefabs.ObjectPrefab m_Prefab;
    private Game.Input.IProxyAction m_PlaceUpgrade;
    private Game.Input.IProxyAction m_Rebuild;
    private Game.Tools.UpgradeToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public Game.Prefabs.ObjectPrefab prefab { get; set; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }

    public UpgradeToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle CreateTempObject(Unity.Jobs.JobHandle inputDeps);
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Unity.Entities.EntityQuery m_ContainerQuery`  

```csharp
private Unity.Entities.EntityQuery m_ContainerQuery;
```

- `private Unity.Entities.Entity m_UpgradingObject`  

```csharp
private Unity.Entities.Entity m_UpgradingObject;
```

- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  

```csharp
private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
```

- `private Game.Common.RandomSeed m_RandomSeed`  

```csharp
private Game.Common.RandomSeed m_RandomSeed;
```

- `private System.Boolean m_AlreadyCreated`  

```csharp
private System.Boolean m_AlreadyCreated;
```

- `private Game.Prefabs.ObjectPrefab m_Prefab`  

```csharp
private Game.Prefabs.ObjectPrefab m_Prefab;
```

- `private Game.Input.IProxyAction m_PlaceUpgrade`  

```csharp
private Game.Input.IProxyAction m_PlaceUpgrade;
```

- `private Game.Input.IProxyAction m_Rebuild`  

```csharp
private Game.Input.IProxyAction m_Rebuild;
```

- `private Game.Tools.UpgradeToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.UpgradeToolSystem+TypeHandle __TypeHandle;
```

- `public static const System.String kToolID`  

```csharp
public static const System.String kToolID;
```


## Properties

- `public System.String toolID { get }`  

```csharp
public System.String toolID { get; }
```

- `public Game.Prefabs.ObjectPrefab prefab { get; set }`  

```csharp
public Game.Prefabs.ObjectPrefab prefab { get; set; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```


## Constructors

- `public UpgradeToolSystem()`  

```csharp
public UpgradeToolSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private Apply(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps);
```

- `private Cancel(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps);
```

- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
```

- `private CreateTempObject(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle CreateTempObject(Unity.Jobs.JobHandle inputDeps);
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public virtual Game.Prefabs.PrefabBase GetPrefab();
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public virtual System.Void InitializeRaycast();
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

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```

- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
```

- `private Update(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps);
```

- `private virtual UpdateActions() : System.Void`  

```csharp
private virtual System.Void UpdateActions();
```

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Tools.UpgradeToolSystem+TypeHandle`  
- `Game.Tools.UpgradeToolSystem+<get_toolActions>d__19`  

