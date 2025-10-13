# Game.Prefabs.InfoviewInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InfoviewInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_NewInfoviewQuery;
    private Unity.Entities.EntityQuery m_AllInfoviewQuery;
    private Unity.Entities.EntityQuery m_AllInfomodeQuery;
    private Unity.Entities.EntityQuery m_NewPlaceableQuery;
    private Unity.Entities.EntityQuery m_AllPlaceableQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Prefabs.InfoviewInitializeSystem+TypeHandle __TypeHandle;
    private static const System.Int32 TYPE_PRIORITY;
    private static const System.Int32 PRIMARY_REQUIREMENT_PRIORITY;
    private static const System.Int32 SECONDARY_REQUIREMENT_PRIORITY;
    private static const System.Int32 PRIMARY_EFFECT_PRIORITY;
    private static const System.Int32 SECONDARY_EFFECT_PRIORITY;

    public System.Collections.Generic.IEnumerable<Game.Prefabs.InfoviewPrefab> infoviews { get; }
    public System.Collections.Generic.IEnumerable<Game.Prefabs.InfomodePrefab> infomodes { get; }

    public InfoviewInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle FindInfoviews(Unity.Jobs.JobHandle inputDeps, Unity.Entities.EntityQuery infoviewQuery, Unity.Entities.EntityQuery infomodeQuery, Unity.Entities.EntityQuery objectQuery);
    private Unity.Jobs.JobHandle InitializeInfoviews(Unity.Jobs.JobHandle inputDeps, Unity.Entities.EntityQuery infoviewGroup, Unity.Entities.EntityQuery infomodeGroup);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_NewInfoviewQuery`  

```csharp
private Unity.Entities.EntityQuery m_NewInfoviewQuery;
```

- `private Unity.Entities.EntityQuery m_AllInfoviewQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllInfoviewQuery;
```

- `private Unity.Entities.EntityQuery m_AllInfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllInfomodeQuery;
```

- `private Unity.Entities.EntityQuery m_NewPlaceableQuery`  

```csharp
private Unity.Entities.EntityQuery m_NewPlaceableQuery;
```

- `private Unity.Entities.EntityQuery m_AllPlaceableQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllPlaceableQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Prefabs.InfoviewInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.InfoviewInitializeSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 TYPE_PRIORITY`  

```csharp
private static const System.Int32 TYPE_PRIORITY;
```

- `private static const System.Int32 PRIMARY_REQUIREMENT_PRIORITY`  

```csharp
private static const System.Int32 PRIMARY_REQUIREMENT_PRIORITY;
```

- `private static const System.Int32 SECONDARY_REQUIREMENT_PRIORITY`  

```csharp
private static const System.Int32 SECONDARY_REQUIREMENT_PRIORITY;
```

- `private static const System.Int32 PRIMARY_EFFECT_PRIORITY`  

```csharp
private static const System.Int32 PRIMARY_EFFECT_PRIORITY;
```

- `private static const System.Int32 SECONDARY_EFFECT_PRIORITY`  

```csharp
private static const System.Int32 SECONDARY_EFFECT_PRIORITY;
```


## Properties

- `public System.Collections.Generic.IEnumerable<Game.Prefabs.InfoviewPrefab> infoviews { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Prefabs.InfoviewPrefab> infoviews { get; }
```

- `public System.Collections.Generic.IEnumerable<Game.Prefabs.InfomodePrefab> infomodes { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Prefabs.InfomodePrefab> infomodes { get; }
```


## Constructors

- `public InfoviewInitializeSystem()`  

```csharp
public InfoviewInitializeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private FindInfoviews(Unity.Jobs.JobHandle inputDeps, Unity.Entities.EntityQuery infoviewQuery, Unity.Entities.EntityQuery infomodeQuery, Unity.Entities.EntityQuery objectQuery) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle FindInfoviews(Unity.Jobs.JobHandle inputDeps, Unity.Entities.EntityQuery infoviewQuery, Unity.Entities.EntityQuery infomodeQuery, Unity.Entities.EntityQuery objectQuery);
```

- `private InitializeInfoviews(Unity.Jobs.JobHandle inputDeps, Unity.Entities.EntityQuery infoviewGroup, Unity.Entities.EntityQuery infomodeGroup) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle InitializeInfoviews(Unity.Jobs.JobHandle inputDeps, Unity.Entities.EntityQuery infoviewGroup, Unity.Entities.EntityQuery infomodeGroup);
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

- `Game.Prefabs.InfoviewInitializeSystem+InfoModeData`  
- `Game.Prefabs.InfoviewInitializeSystem+FindInfoviewJob`  
- `Game.Prefabs.InfoviewInitializeSystem+PollutionType`  
- `Game.Prefabs.InfoviewInitializeSystem+WaterType`  
- `Game.Prefabs.InfoviewInitializeSystem+InfoviewBufferData`  
- `Game.Prefabs.InfoviewInitializeSystem+FindSubInfoviewJob`  
- `Game.Prefabs.InfoviewInitializeSystem+AssignInfoviewJob`  
- `Game.Prefabs.InfoviewInitializeSystem+TypeHandle`  
- `Game.Prefabs.InfoviewInitializeSystem+<get___infomodes_F6CD08E>d__30`  
- `Game.Prefabs.InfoviewInitializeSystem+<get___infoviews_5966D7E4>d__28`  
- `Game.Prefabs.InfoviewInitializeSystem+<get_infomodes>d__11`  
- `Game.Prefabs.InfoviewInitializeSystem+<get_infoviews>d__9`  

