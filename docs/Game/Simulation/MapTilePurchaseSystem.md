# Game.Simulation.MapTilePurchaseSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IMapTilePurchaseSystem`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.SelectionToolSystem m_SelectionToolSystem`  
- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  
- `private Game.Areas.MapTileSystem m_MapTileSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Unity.Entities.EntityQuery m_SelectionQuery`  
- `private Unity.Entities.EntityQuery m_OwnedTileQuery`  
- `private Unity.Entities.EntityQuery m_LockedMapTilesQuery`  
- `private Unity.Entities.EntityQuery m_UnlockedMilestoneQuery`  
- `private Unity.Entities.EntityQuery m_LockedMilestoneQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Collections.NativeArray<System.Single> m_FeatureAmounts`  
- `private System.Single m_Cost`  
- `private System.Single m_Upkeep`  
- `private Game.Simulation.TilePurchaseErrorFlags <status>k__BackingField`  
- `private Game.Simulation.MapTilePurchaseSystem+TypeHandle __TypeHandle`  
- `private static readonly System.Double kMapTileSizeModifier`  
- `private static readonly System.Double kResourceModifier`  
- `private static readonly System.Int32 kAutoUnlockedTiles`  
- `private static readonly System.Double[] kMapFeatureBaselineModifiers`  

## Properties

- `public Game.Simulation.TilePurchaseErrorFlags status { get; private set }`  
- `public System.Boolean selecting { get; set }`  
- `public System.Int32 cost { get }`  
- `public System.Int32 upkeep { get }`  

## Constructors

- `public MapTilePurchaseSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private CalculateOwnedTiles() : System.Int32`  
- `private CalculateOwnedTilesCost() : System.Single`  
- `public CalculateOwnedTilesUpkeep() : System.Int32`  
- `public GetAvailableTiles() : System.Int32`  
- `private GetBaselineModifier(System.Int32 mapFeature) : System.Double`  
- `public GetFeatureAmount(Game.Areas.MapFeature feature) : System.Single`  
- `public GetMapTileUpkeepCostMultiplier(System.Int32 tileCount) : System.Single`  
- `public GetMapTileUpkeepEnabled() : System.Boolean`  
- `public GetSelectedTileCount() : System.Int32`  
- `public IsMilestonesLeft() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PurchaseSelection() : System.Void`  
- `private TryGetSelections(System.Boolean isReadOnly, Unity.Entities.DynamicBuffer`1[[Game.Tools.SelectionElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& selections) : System.Boolean`  
- `public UnlockMapTiles() : System.Void`  
- `public static UnlockTile(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity area) : System.Void`  
- `private UpdateStatus() : System.Void`  

## Nested types

- `Game.Simulation.MapTilePurchaseSystem+TypeHandle`  

