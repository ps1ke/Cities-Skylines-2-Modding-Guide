# Game.UI.InGame.LevelInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LevelInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Colossal.UI.Binding.RawValueBinding m_ResidentialLevels;
    private Colossal.UI.Binding.RawValueBinding m_CommercialLevels;
    private Colossal.UI.Binding.RawValueBinding m_IndustrialLevels;
    private Colossal.UI.Binding.RawValueBinding m_OfficeLevels;
    private Unity.Entities.EntityQuery m_SpawnableQuery;
    private Unity.Collections.NativeArray<Game.UI.InGame.LevelInfoviewUISystem+Levels> m_Results;
    private Game.UI.InGame.LevelInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }

    public LevelInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void PerformUpdate();
    private System.Void UpdateBindings();
    private System.Void UpdateCommercialLevels(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void UpdateIndustrialLevels(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void UpdateOfficeLevels(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void UpdateResidentialLevels(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteLevels(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.LevelInfoviewUISystem+Levels levels);
}
```


## Fields

- `private Colossal.UI.Binding.RawValueBinding m_ResidentialLevels`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ResidentialLevels;
```

- `private Colossal.UI.Binding.RawValueBinding m_CommercialLevels`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_CommercialLevels;
```

- `private Colossal.UI.Binding.RawValueBinding m_IndustrialLevels`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_IndustrialLevels;
```

- `private Colossal.UI.Binding.RawValueBinding m_OfficeLevels`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_OfficeLevels;
```

- `private Unity.Entities.EntityQuery m_SpawnableQuery`  

```csharp
private Unity.Entities.EntityQuery m_SpawnableQuery;
```

- `private Unity.Collections.NativeArray<Game.UI.InGame.LevelInfoviewUISystem+Levels> m_Results`  

```csharp
private Unity.Collections.NativeArray<Game.UI.InGame.LevelInfoviewUISystem+Levels> m_Results;
```

- `private Game.UI.InGame.LevelInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.LevelInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```


## Constructors

- `public LevelInfoviewUISystem()`  

```csharp
public LevelInfoviewUISystem();
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected virtual System.Void PerformUpdate();
```

- `private UpdateBindings() : System.Void`  

```csharp
private System.Void UpdateBindings();
```

- `private UpdateCommercialLevels(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void UpdateCommercialLevels(Colossal.UI.Binding.IJsonWriter writer);
```

- `private UpdateIndustrialLevels(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void UpdateIndustrialLevels(Colossal.UI.Binding.IJsonWriter writer);
```

- `private UpdateOfficeLevels(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void UpdateOfficeLevels(Colossal.UI.Binding.IJsonWriter writer);
```

- `private UpdateResidentialLevels(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void UpdateResidentialLevels(Colossal.UI.Binding.IJsonWriter writer);
```

- `private WriteLevels(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.LevelInfoviewUISystem+Levels levels) : System.Void`  

```csharp
private System.Void WriteLevels(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.LevelInfoviewUISystem+Levels levels);
```


## Nested types

- `Game.UI.InGame.LevelInfoviewUISystem+Result`  
- `Game.UI.InGame.LevelInfoviewUISystem+UpdateLevelsJob`  
- `Game.UI.InGame.LevelInfoviewUISystem+Levels`  
- `Game.UI.InGame.LevelInfoviewUISystem+TypeHandle`  

