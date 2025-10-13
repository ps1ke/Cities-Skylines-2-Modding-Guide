# Game.Simulation.CityModifierUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityModifierUpdateSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CityQuery;
    private Unity.Entities.EntityQuery m_EffectProviderQuery;
    private Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData m_CityModifierRefreshData;
    private Game.Simulation.CityModifierUpdateSystem+TypeHandle __TypeHandle;

    public CityModifierUpdateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Void AddToTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.CityModifierData> cityModifiers);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static System.Void InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList);
    public static System.Void InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.CityModifierData> cityModifiers);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CityQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityQuery;
```

- `private Unity.Entities.EntityQuery m_EffectProviderQuery`  

```csharp
private Unity.Entities.EntityQuery m_EffectProviderQuery;
```

- `private Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData m_CityModifierRefreshData`  

```csharp
private Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData m_CityModifierRefreshData;
```

- `private Game.Simulation.CityModifierUpdateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CityModifierUpdateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CityModifierUpdateSystem()`  

```csharp
public CityModifierUpdateSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static AddToTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.CityModifierData> cityModifiers) : System.Void`  

```csharp
public static System.Void AddToTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.CityModifierData> cityModifiers);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public static InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList) : System.Void`  

```csharp
public static System.Void InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList);
```

- `public static InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.CityModifierData> cityModifiers) : System.Void`  

```csharp
public static System.Void InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.CityModifierData> cityModifiers);
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

- `Game.Simulation.CityModifierUpdateSystem+UpdateCityModifiersJob`  
- `Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData`  
- `Game.Simulation.CityModifierUpdateSystem+TypeHandle`  

