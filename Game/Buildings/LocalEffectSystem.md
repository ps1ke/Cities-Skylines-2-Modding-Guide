# Game.Buildings.LocalEffectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LocalEffectSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdatedProvidersQuery;
    private Unity.Entities.EntityQuery m_AllProvidersQuery;
    private Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> m_SearchTree;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private System.Boolean m_Loaded;
    private Game.Buildings.LocalEffectSystem+TypeHandle __TypeHandle;

    public LocalEffectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddLocalEffectReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddLocalEffectWriter(Unity.Jobs.JobHandle jobHandle);
    public static System.Void AddToTempList(Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalModifierData> localModifiers, System.Boolean disabled);
    public static System.Boolean GetEffectBounds(Game.Objects.Transform transform, Game.Prefabs.LocalModifierData localModifier, Game.Buildings.LocalEffectSystem+EffectBounds& effectBounds);
    public static System.Boolean GetEffectBounds(Game.Objects.Transform transform, System.Single efficiency, Game.Prefabs.LocalModifierData localModifier, Game.Buildings.LocalEffectSystem+EffectBounds& effectBounds);
    private System.Boolean GetLoaded();
    public Game.Buildings.LocalEffectSystem+ReadData GetReadData(Unity.Jobs.JobHandle& dependencies);
    public Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    public static System.Void InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalModifierData> localModifiers);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedProvidersQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedProvidersQuery;
```

- `private Unity.Entities.EntityQuery m_AllProvidersQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllProvidersQuery;
```

- `private Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> m_SearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> m_SearchTree;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Buildings.LocalEffectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.LocalEffectSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LocalEffectSystem()`  

```csharp
public LocalEffectSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddLocalEffectReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddLocalEffectReader(Unity.Jobs.JobHandle jobHandle);
```

- `public AddLocalEffectWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddLocalEffectWriter(Unity.Jobs.JobHandle jobHandle);
```

- `public static AddToTempList(Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalModifierData> localModifiers, System.Boolean disabled) : System.Void`  

```csharp
public static System.Void AddToTempList(Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalModifierData> localModifiers, System.Boolean disabled);
```

- `public static GetEffectBounds(Game.Objects.Transform transform, Game.Prefabs.LocalModifierData localModifier, Game.Buildings.LocalEffectSystem+EffectBounds& effectBounds) : System.Boolean`  

```csharp
public static System.Boolean GetEffectBounds(Game.Objects.Transform transform, Game.Prefabs.LocalModifierData localModifier, Game.Buildings.LocalEffectSystem+EffectBounds& effectBounds);
```

- `public static GetEffectBounds(Game.Objects.Transform transform, System.Single efficiency, Game.Prefabs.LocalModifierData localModifier, Game.Buildings.LocalEffectSystem+EffectBounds& effectBounds) : System.Boolean`  

```csharp
public static System.Boolean GetEffectBounds(Game.Objects.Transform transform, System.Single efficiency, Game.Prefabs.LocalModifierData localModifier, Game.Buildings.LocalEffectSystem+EffectBounds& effectBounds);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `public GetReadData(Unity.Jobs.JobHandle& dependencies) : Game.Buildings.LocalEffectSystem+ReadData`  

```csharp
public Game.Buildings.LocalEffectSystem+ReadData GetReadData(Unity.Jobs.JobHandle& dependencies);
```

- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds>`  

```csharp
public Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
```

- `public static InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalModifierData> localModifiers) : System.Void`  

```csharp
public static System.Void InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalModifierData> localModifiers);
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Buildings.LocalEffectSystem+EffectItem`  
- `Game.Buildings.LocalEffectSystem+EffectBounds`  
- `Game.Buildings.LocalEffectSystem+ReadData`  
- `Game.Buildings.LocalEffectSystem+UpdateLocalEffectsJob`  
- `Game.Buildings.LocalEffectSystem+TypeHandle`  

