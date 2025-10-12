# Game.Tools.UpgradeToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ObjectToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Unity.Entities.EntityQuery m_DefinitionQuery`  
- `private Unity.Entities.EntityQuery m_SoundQuery`  
- `private Unity.Entities.EntityQuery m_ContainerQuery`  
- `private Unity.Entities.Entity m_UpgradingObject`  
- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  
- `private Game.Common.RandomSeed m_RandomSeed`  
- `private System.Boolean m_AlreadyCreated`  
- `private Game.Prefabs.ObjectPrefab m_Prefab`  
- `private Game.Input.IProxyAction m_PlaceUpgrade`  
- `private Game.Input.IProxyAction m_Rebuild`  
- `private Game.Tools.UpgradeToolSystem+TypeHandle __TypeHandle`  
- `public static const System.String kToolID`  

## Properties

- `public System.String toolID { get }`  
- `public Game.Prefabs.ObjectPrefab prefab { get; set }`  
- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

## Constructors

- `public UpgradeToolSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private Apply(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private Cancel(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private CreateTempObject(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  
- `public virtual InitializeRaycast() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `private Update(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private virtual UpdateActions() : System.Void`  
- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Tools.UpgradeToolSystem+TypeHandle`  
- `Game.Tools.UpgradeToolSystem+<get_toolActions>d__19`  

