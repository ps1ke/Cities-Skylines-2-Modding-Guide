# Game.Prefabs.Modes.GameModeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `private System.String <overrideMode>k__BackingField`  
- `private System.String <currentModeName>k__BackingField`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Prefabs.Modes.ModeSetting m_ModeSetting`  
- `private Game.Prefabs.Modes.ModeSetting m_NextMode`  
- `private Unity.Entities.EntityQuery m_ModeSettingQuery`  
- `private Unity.Entities.EntityQuery m_ModeInfoQuery`  

## Properties

- `public System.String overrideMode { get; set }`  
- `public Game.Prefabs.Modes.ModeSetting modeSetting { get }`  
- `public System.String currentModeName { get; private set }`  

## Constructors

- `public GameModeSystem()`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetGameModeInfo() : System.Collections.Generic.List<Game.Prefabs.Modes.GameModeInfo>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

