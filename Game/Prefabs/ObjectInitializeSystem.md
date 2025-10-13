# Game.Prefabs.ObjectInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObjectInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_PlaceholderQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.ObjectInitializeSystem+TypeHandle __TypeHandle;

    public ObjectInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static Game.Prefabs.MeshGroupFlags GetMeshGroupFlag(Game.Objects.ObjectState state, System.Boolean inverse);
    private System.UInt16 GetRandomSeed(System.String name);
    private System.Void InitializePrefab(Game.Prefabs.AssetStampPrefab stampPrefab, Game.Prefabs.AssetStampData& assetStampData, Game.Prefabs.PlaceableObjectData& placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData);
    private System.Void InitializePrefab(Game.Prefabs.ObjectGeometryPrefab objectPrefab, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData, Game.Prefabs.GrowthScaleData& growthScaleData, Game.Prefabs.StackData& stackData, Game.Prefabs.QuantityObjectData& quantityObjectData, Game.Prefabs.CreatureData& creatureData, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMesh> meshes, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMeshGroup> meshGroups, Unity.Entities.DynamicBuffer<Game.Prefabs.CharacterElement> characterElements, System.Boolean isPlantObject, System.Boolean isHumanObject, System.Boolean isBuildingObject, System.Boolean isVehicleObject, System.Boolean isCreatureObject);
    private System.Void InitializePrefab(Game.Prefabs.MarkerObjectPrefab objectPrefab, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMesh> meshes);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void UpdateStackBounds(Colossal.Mathematics.Bounds1& stackBounds, Colossal.Mathematics.Bounds3& meshBounds, Game.Prefabs.StackProperties properties);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Entities.EntityQuery m_PlaceholderQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlaceholderQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.ObjectInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.ObjectInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ObjectInitializeSystem()`  

```csharp
public ObjectInitializeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private static GetMeshGroupFlag(Game.Objects.ObjectState state, System.Boolean inverse) : Game.Prefabs.MeshGroupFlags`  

```csharp
private static Game.Prefabs.MeshGroupFlags GetMeshGroupFlag(Game.Objects.ObjectState state, System.Boolean inverse);
```

- `private GetRandomSeed(System.String name) : System.UInt16`  

```csharp
private System.UInt16 GetRandomSeed(System.String name);
```

- `private InitializePrefab(Game.Prefabs.AssetStampPrefab stampPrefab, Game.Prefabs.AssetStampData& assetStampData, Game.Prefabs.PlaceableObjectData& placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData) : System.Void`  

```csharp
private System.Void InitializePrefab(Game.Prefabs.AssetStampPrefab stampPrefab, Game.Prefabs.AssetStampData& assetStampData, Game.Prefabs.PlaceableObjectData& placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData);
```

- `private InitializePrefab(Game.Prefabs.ObjectGeometryPrefab objectPrefab, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData, Game.Prefabs.GrowthScaleData& growthScaleData, Game.Prefabs.StackData& stackData, Game.Prefabs.QuantityObjectData& quantityObjectData, Game.Prefabs.CreatureData& creatureData, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMesh> meshes, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMeshGroup> meshGroups, Unity.Entities.DynamicBuffer<Game.Prefabs.CharacterElement> characterElements, System.Boolean isPlantObject, System.Boolean isHumanObject, System.Boolean isBuildingObject, System.Boolean isVehicleObject, System.Boolean isCreatureObject) : System.Void`  

```csharp
private System.Void InitializePrefab(Game.Prefabs.ObjectGeometryPrefab objectPrefab, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData, Game.Prefabs.GrowthScaleData& growthScaleData, Game.Prefabs.StackData& stackData, Game.Prefabs.QuantityObjectData& quantityObjectData, Game.Prefabs.CreatureData& creatureData, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMesh> meshes, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMeshGroup> meshGroups, Unity.Entities.DynamicBuffer<Game.Prefabs.CharacterElement> characterElements, System.Boolean isPlantObject, System.Boolean isHumanObject, System.Boolean isBuildingObject, System.Boolean isVehicleObject, System.Boolean isCreatureObject);
```

- `private InitializePrefab(Game.Prefabs.MarkerObjectPrefab objectPrefab, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMesh> meshes) : System.Void`  

```csharp
private System.Void InitializePrefab(Game.Prefabs.MarkerObjectPrefab objectPrefab, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMesh> meshes);
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

- `private UpdateStackBounds(Colossal.Mathematics.Bounds1& stackBounds, Colossal.Mathematics.Bounds3& meshBounds, Game.Prefabs.StackProperties properties) : System.Void`  

```csharp
private System.Void UpdateStackBounds(Colossal.Mathematics.Bounds1& stackBounds, Colossal.Mathematics.Bounds3& meshBounds, Game.Prefabs.StackProperties properties);
```


## Nested types

- `Game.Prefabs.ObjectInitializeSystem+FixPlaceholdersJob`  
- `Game.Prefabs.ObjectInitializeSystem+InitializeSubNetsJob`  
- `Game.Prefabs.ObjectInitializeSystem+FindPlaceholderRequirementsJob`  
- `Game.Prefabs.ObjectInitializeSystem+FindSubObjectRequirementsJob`  
- `Game.Prefabs.ObjectInitializeSystem+TypeHandle`  

