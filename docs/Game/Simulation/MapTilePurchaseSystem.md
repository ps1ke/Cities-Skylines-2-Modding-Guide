# Game.Simulation.MapTilePurchaseSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IMapTilePurchaseSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MapTilePurchaseSystem : Game.GameSystemBase, Game.Simulation.IMapTilePurchaseSystem
{
    private Game.Tools.SelectionToolSystem m_SelectionToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Areas.MapTileSystem m_MapTileSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_SelectionQuery;
    private Unity.Entities.EntityQuery m_OwnedTileQuery;
    private Unity.Entities.EntityQuery m_LockedMapTilesQuery;
    private Unity.Entities.EntityQuery m_UnlockedMilestoneQuery;
    private Unity.Entities.EntityQuery m_LockedMilestoneQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Collections.NativeArray<System.Single> m_FeatureAmounts;
    private System.Single m_Cost;
    private System.Single m_Upkeep;
    private Game.Simulation.TilePurchaseErrorFlags <status>k__BackingField;
    private Game.Simulation.MapTilePurchaseSystem+TypeHandle __TypeHandle;
    private static readonly System.Double kMapTileSizeModifier;
    private static readonly System.Double kResourceModifier;
    private static readonly System.Int32 kAutoUnlockedTiles;
    private static readonly System.Double[] kMapFeatureBaselineModifiers;

    public Game.Simulation.TilePurchaseErrorFlags status { get; private set; }
    public System.Boolean selecting { get; set; }
    public System.Int32 cost { get; }
    public System.Int32 upkeep { get; }

    public MapTilePurchaseSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Int32 CalculateOwnedTiles();
    private System.Single CalculateOwnedTilesCost();
    public System.Int32 CalculateOwnedTilesUpkeep();
    public System.Int32 GetAvailableTiles();
    private System.Double GetBaselineModifier(System.Int32 mapFeature);
    public System.Single GetFeatureAmount(Game.Areas.MapFeature feature);
    public System.Single GetMapTileUpkeepCostMultiplier(System.Int32 tileCount);
    public System.Boolean GetMapTileUpkeepEnabled();
    public System.Int32 GetSelectedTileCount();
    public System.Boolean IsMilestonesLeft();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PurchaseSelection();
    private System.Boolean TryGetSelections(System.Boolean isReadOnly, Unity.Entities.DynamicBuffer`1[[Game.Tools.SelectionElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& selections);
    public System.Void UnlockMapTiles();
    public static System.Void UnlockTile(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity area);
    private System.Void UpdateStatus();
}
```


## Fields

- `private Game.Tools.SelectionToolSystem m_SelectionToolSystem`  

```csharp
private Game.Tools.SelectionToolSystem m_SelectionToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Areas.MapTileSystem m_MapTileSystem`  

```csharp
private Game.Areas.MapTileSystem m_MapTileSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_SelectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_SelectionQuery;
```

- `private Unity.Entities.EntityQuery m_OwnedTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_OwnedTileQuery;
```

- `private Unity.Entities.EntityQuery m_LockedMapTilesQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedMapTilesQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockedMilestoneQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedMilestoneQuery;
```

- `private Unity.Entities.EntityQuery m_LockedMilestoneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedMilestoneQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_FeatureAmounts`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_FeatureAmounts;
```

- `private System.Single m_Cost`  

```csharp
private System.Single m_Cost;
```

- `private System.Single m_Upkeep`  

```csharp
private System.Single m_Upkeep;
```

- `private Game.Simulation.TilePurchaseErrorFlags <status>k__BackingField`  

```csharp
private Game.Simulation.TilePurchaseErrorFlags <status>k__BackingField;
```

- `private Game.Simulation.MapTilePurchaseSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.MapTilePurchaseSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Double kMapTileSizeModifier`  

```csharp
private static readonly System.Double kMapTileSizeModifier;
```

- `private static readonly System.Double kResourceModifier`  

```csharp
private static readonly System.Double kResourceModifier;
```

- `private static readonly System.Int32 kAutoUnlockedTiles`  

```csharp
private static readonly System.Int32 kAutoUnlockedTiles;
```

- `private static readonly System.Double[] kMapFeatureBaselineModifiers`  

```csharp
private static readonly System.Double[] kMapFeatureBaselineModifiers;
```


## Properties

- `public Game.Simulation.TilePurchaseErrorFlags status { get; private set }`  

```csharp
public Game.Simulation.TilePurchaseErrorFlags status { get; private set; }
```

- `public System.Boolean selecting { get; set }`  

```csharp
public System.Boolean selecting { get; set; }
```

- `public System.Int32 cost { get }`  

```csharp
public System.Int32 cost { get; }
```

- `public System.Int32 upkeep { get }`  

```csharp
public System.Int32 upkeep { get; }
```


## Constructors

- `public MapTilePurchaseSystem()`  

```csharp
public MapTilePurchaseSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private CalculateOwnedTiles() : System.Int32`  

```csharp
private System.Int32 CalculateOwnedTiles();
```

- `private CalculateOwnedTilesCost() : System.Single`  

```csharp
private System.Single CalculateOwnedTilesCost();
```

- `public CalculateOwnedTilesUpkeep() : System.Int32`  

```csharp
public System.Int32 CalculateOwnedTilesUpkeep();
```

- `public GetAvailableTiles() : System.Int32`  

```csharp
public System.Int32 GetAvailableTiles();
```

- `private GetBaselineModifier(System.Int32 mapFeature) : System.Double`  

```csharp
private System.Double GetBaselineModifier(System.Int32 mapFeature);
```

- `public GetFeatureAmount(Game.Areas.MapFeature feature) : System.Single`  

```csharp
public System.Single GetFeatureAmount(Game.Areas.MapFeature feature);
```

- `public GetMapTileUpkeepCostMultiplier(System.Int32 tileCount) : System.Single`  

```csharp
public System.Single GetMapTileUpkeepCostMultiplier(System.Int32 tileCount);
```

- `public GetMapTileUpkeepEnabled() : System.Boolean`  

```csharp
public System.Boolean GetMapTileUpkeepEnabled();
```

- `public GetSelectedTileCount() : System.Int32`  

```csharp
public System.Int32 GetSelectedTileCount();
```

- `public IsMilestonesLeft() : System.Boolean`  

```csharp
public System.Boolean IsMilestonesLeft();
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PurchaseSelection() : System.Void`  

```csharp
public System.Void PurchaseSelection();
```

- `private TryGetSelections(System.Boolean isReadOnly, Unity.Entities.DynamicBuffer`1[[Game.Tools.SelectionElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& selections) : System.Boolean`  

```csharp
private System.Boolean TryGetSelections(System.Boolean isReadOnly, Unity.Entities.DynamicBuffer`1[[Game.Tools.SelectionElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& selections);
```

- `public UnlockMapTiles() : System.Void`  

```csharp
public System.Void UnlockMapTiles();
```

- `public static UnlockTile(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity area) : System.Void`  

```csharp
public static System.Void UnlockTile(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity area);
```

- `private UpdateStatus() : System.Void`  

```csharp
private System.Void UpdateStatus();
```


## Nested types

- `Game.Simulation.MapTilePurchaseSystem+TypeHandle`  

