# Game.Prefabs.Modes.GameModeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public class GameModeSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private System.String <overrideMode>k__BackingField;
    private System.String <currentModeName>k__BackingField;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.Modes.ModeSetting m_ModeSetting;
    private Game.Prefabs.Modes.ModeSetting m_NextMode;
    private Unity.Entities.EntityQuery m_ModeSettingQuery;
    private Unity.Entities.EntityQuery m_ModeInfoQuery;

    public System.String overrideMode { get; set; }
    public Game.Prefabs.Modes.ModeSetting modeSetting { get; }
    public System.String currentModeName { get; private set; }

    public GameModeSystem();

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Collections.Generic.List<Game.Prefabs.Modes.GameModeInfo> GetGameModeInfo();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private System.String <overrideMode>k__BackingField`  

```csharp
private System.String <overrideMode>k__BackingField;
```

- `private System.String <currentModeName>k__BackingField`  

```csharp
private System.String <currentModeName>k__BackingField;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.Modes.ModeSetting m_ModeSetting`  

```csharp
private Game.Prefabs.Modes.ModeSetting m_ModeSetting;
```

- `private Game.Prefabs.Modes.ModeSetting m_NextMode`  

```csharp
private Game.Prefabs.Modes.ModeSetting m_NextMode;
```

- `private Unity.Entities.EntityQuery m_ModeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModeSettingQuery;
```

- `private Unity.Entities.EntityQuery m_ModeInfoQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModeInfoQuery;
```


## Properties

- `public System.String overrideMode { get; set }`  

```csharp
public System.String overrideMode { get; set; }
```

- `public Game.Prefabs.Modes.ModeSetting modeSetting { get }`  

```csharp
public Game.Prefabs.Modes.ModeSetting modeSetting { get; }
```

- `public System.String currentModeName { get; private set }`  

```csharp
public System.String currentModeName { get; private set; }
```


## Constructors

- `public GameModeSystem()`  

```csharp
public GameModeSystem();
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetGameModeInfo() : System.Collections.Generic.List<Game.Prefabs.Modes.GameModeInfo>`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.Modes.GameModeInfo> GetGameModeInfo();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


