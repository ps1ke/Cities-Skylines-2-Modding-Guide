# Game.Prefabs.ManualUITagsConfiguration

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ManualUITagsConfiguration : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.UITagPrefab m_ChirperPanel;
    public Game.Prefabs.UITagPrefab m_ChirperPanelButton;
    public Game.Prefabs.UITagPrefab m_ChirperPanelChirps;
    public Game.Prefabs.UITagPrefab m_CityInfoPanel;
    public Game.Prefabs.UITagPrefab m_CityInfoPanelButton;
    public Game.Prefabs.UITagPrefab m_CityInfoPanelDemandPage;
    public Game.Prefabs.UITagPrefab m_CityInfoPanelDemandTab;
    public Game.Prefabs.UITagPrefab m_CityInfoPanelPoliciesPage;
    public Game.Prefabs.UITagPrefab m_CityInfoPanelPoliciesTab;
    public Game.Prefabs.UITagPrefab m_EconomyPanelBudgetBalance;
    public Game.Prefabs.UITagPrefab m_EconomyPanelBudgetExpenses;
    public Game.Prefabs.UITagPrefab m_EconomyPanelBudgetPage;
    public Game.Prefabs.UITagPrefab m_EconomyPanelBudgetRevenue;
    public Game.Prefabs.UITagPrefab m_EconomyPanelBudgetTab;
    public Game.Prefabs.UITagPrefab m_EconomyPanelButton;
    public Game.Prefabs.UITagPrefab m_EconomyPanelLoansAccept;
    public Game.Prefabs.UITagPrefab m_EconomyPanelLoansPage;
    public Game.Prefabs.UITagPrefab m_EconomyPanelLoansSlider;
    public Game.Prefabs.UITagPrefab m_EconomyPanelLoansTab;
    public Game.Prefabs.UITagPrefab m_EconomyPanelProductionPage;
    public Game.Prefabs.UITagPrefab m_EconomyPanelProductionResources;
    public Game.Prefabs.UITagPrefab m_EconomyPanelProductionTab;
    public Game.Prefabs.UITagPrefab m_EconomyPanelServicesBudget;
    public Game.Prefabs.UITagPrefab m_EconomyPanelServicesList;
    public Game.Prefabs.UITagPrefab m_EconomyPanelServicesPage;
    public Game.Prefabs.UITagPrefab m_EconomyPanelServicesTab;
    public Game.Prefabs.UITagPrefab m_EconomyPanelTaxationEstimate;
    public Game.Prefabs.UITagPrefab m_EconomyPanelTaxationPage;
    public Game.Prefabs.UITagPrefab m_EconomyPanelTaxationRate;
    public Game.Prefabs.UITagPrefab m_EconomyPanelTaxationTab;
    public Game.Prefabs.UITagPrefab m_EconomyPanelTaxationType;
    public Game.Prefabs.UITagPrefab m_EventJournalPanel;
    public Game.Prefabs.UITagPrefab m_EventJournalPanelButton;
    public Game.Prefabs.UITagPrefab m_InfoviewsButton;
    public Game.Prefabs.UITagPrefab m_InfoviewsMenu;
    public Game.Prefabs.UITagPrefab m_InfoviewsPanel;
    public Game.Prefabs.UITagPrefab m_InfoviewsFireHazard;
    public Game.Prefabs.UITagPrefab m_LifePathPanel;
    public Game.Prefabs.UITagPrefab m_LifePathPanelBackButton;
    public Game.Prefabs.UITagPrefab m_LifePathPanelButton;
    public Game.Prefabs.UITagPrefab m_LifePathPanelChirps;
    public Game.Prefabs.UITagPrefab m_LifePathPanelDetails;
    public Game.Prefabs.UITagPrefab m_MapTilePanel;
    public Game.Prefabs.UITagPrefab m_MapTilePanelButton;
    public Game.Prefabs.UITagPrefab m_MapTilePanelResources;
    public Game.Prefabs.UITagPrefab m_MapTilePanelPurchase;
    public Game.Prefabs.UITagPrefab m_PhotoModePanel;
    public Game.Prefabs.UITagPrefab m_PhotoModePanelButton;
    public Game.Prefabs.UITagPrefab m_PhotoModePanelHideUI;
    public Game.Prefabs.UITagPrefab m_PhotoModePanelTakePicture;
    public Game.Prefabs.UITagPrefab m_PhotoModeTab;
    public Game.Prefabs.UITagPrefab m_PhotoModePanelTitle;
    public Game.Prefabs.UITagPrefab m_PhotoModeCinematicCameraToggle;
    public Game.Prefabs.UITagPrefab m_CinematicCameraPanel;
    public Game.Prefabs.UITagPrefab m_CinematicCameraPanelCaptureKey;
    public Game.Prefabs.UITagPrefab m_CinematicCameraPanelPlay;
    public Game.Prefabs.UITagPrefab m_CinematicCameraPanelStop;
    public Game.Prefabs.UITagPrefab m_CinematicCameraPanelHideUI;
    public Game.Prefabs.UITagPrefab m_CinematicCameraPanelSaveLoad;
    public Game.Prefabs.UITagPrefab m_CinematicCameraPanelReset;
    public Game.Prefabs.UITagPrefab m_CinematicCameraPanelTimelineSlider;
    public Game.Prefabs.UITagPrefab m_CinematicCameraPanelTransformCurves;
    public Game.Prefabs.UITagPrefab m_CinematicCameraPanelPropertyCurves;
    public Game.Prefabs.UITagPrefab m_CinematicCameraPanelPlaybackDurationSlider;
    public Game.Prefabs.UITagPrefab m_ProgressionPanel;
    public Game.Prefabs.UITagPrefab m_ProgressionPanelButton;
    public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentNode;
    public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentPage;
    public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentService;
    public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentTab;
    public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentUnlockableNode;
    public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentUnlockNode;
    public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestoneRewards;
    public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestoneRewardsMoney;
    public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestoneRewardsDevPoints;
    public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestoneRewardsMapTiles;
    public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestonesList;
    public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestonesPage;
    public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestonesTab;
    public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestoneXP;
    public Game.Prefabs.UITagPrefab m_RadioPanel;
    public Game.Prefabs.UITagPrefab m_RadioPanelAdsToggle;
    public Game.Prefabs.UITagPrefab m_RadioPanelButton;
    public Game.Prefabs.UITagPrefab m_RadioPanelNetworks;
    public Game.Prefabs.UITagPrefab m_RadioPanelStations;
    public Game.Prefabs.UITagPrefab m_RadioPanelVolumeSlider;
    public Game.Prefabs.UITagPrefab m_StatisticsPanel;
    public Game.Prefabs.UITagPrefab m_StatisticsPanelButton;
    public Game.Prefabs.UITagPrefab m_StatisticsPanelMenu;
    public Game.Prefabs.UITagPrefab m_StatisticsPanelTimeScale;
    public Game.Prefabs.UITagPrefab m_ToolbarBulldozerBar;
    public Game.Prefabs.UITagPrefab m_ToolbarDemand;
    public Game.Prefabs.UITagPrefab m_ToolbarSimulationDateTime;
    public Game.Prefabs.UITagPrefab m_ToolbarSimulationSpeed;
    public Game.Prefabs.UITagPrefab m_ToolbarSimulationToggle;
    public Game.Prefabs.UITagPrefab m_ToolbarUnderground;
    public Game.Prefabs.UITagPrefab m_ToolOptions;
    public Game.Prefabs.UITagPrefab m_ToolOptionsBrushSize;
    public Game.Prefabs.UITagPrefab m_ToolOptionsBrushStrength;
    public Game.Prefabs.UITagPrefab m_ToolOptionsElevation;
    public Game.Prefabs.UITagPrefab m_ToolOptionsElevationDecrease;
    public Game.Prefabs.UITagPrefab m_ToolOptionsElevationIncrease;
    public Game.Prefabs.UITagPrefab m_ToolOptionsElevationStep;
    public Game.Prefabs.UITagPrefab m_ToolOptionsModes;
    public Game.Prefabs.UITagPrefab m_ToolOptionsModesComplexCurve;
    public Game.Prefabs.UITagPrefab m_ToolOptionsModesContinuous;
    public Game.Prefabs.UITagPrefab m_ToolOptionsModesGrid;
    public Game.Prefabs.UITagPrefab m_ToolOptionsModesReplace;
    public Game.Prefabs.UITagPrefab m_ToolOptionsModesSimpleCurve;
    public Game.Prefabs.UITagPrefab m_ToolOptionsModesStraight;
    public Game.Prefabs.UITagPrefab m_ToolOptionsParallelMode;
    public Game.Prefabs.UITagPrefab m_ToolOptionsParallelModeOffset;
    public Game.Prefabs.UITagPrefab m_ToolOptionsParallelModeOffsetDecrease;
    public Game.Prefabs.UITagPrefab m_ToolOptionsParallelModeOffsetIncrease;
    public Game.Prefabs.UITagPrefab m_ToolOptionsSnapping;
    public Game.Prefabs.UITagPrefab m_ToolOptionsThemes;
    public Game.Prefabs.UITagPrefab m_ToolOptionsAssetPacks;
    public Game.Prefabs.UITagPrefab m_ToolOptionsUnderground;
    public Game.Prefabs.UITagPrefab m_TransportationOverviewPanel;
    public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelButton;
    public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelLegend;
    public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelLines;
    public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelTabCargo;
    public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelTabPublicTransport;
    public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelTransportTypes;
    public Game.Prefabs.UITagPrefab m_SelectedInfoPanel;
    public Game.Prefabs.UITagPrefab m_SelectedInfoPanelTitle;
    public Game.Prefabs.UITagPrefab m_SelectedInfoPanelPolicies;
    public Game.Prefabs.UITagPrefab m_SelectedInfoPanelDelete;
    public Game.Prefabs.UITagPrefab m_PauseMenuButton;
    public Game.Prefabs.UITagPrefab m_UpgradeGrid;
    public Game.Prefabs.UITagPrefab m_AssetGrid;
    public Game.Prefabs.UITagPrefab m_ActionHints;
    public Game.Prefabs.UITagPrefab m_AssetImportButton;
    public Game.Prefabs.UITagPrefab m_EditorInfoViewsPanel;
    public Game.Prefabs.UITagPrefab m_ResetTODButton;
    public Game.Prefabs.UITagPrefab m_SimulationPlayButton;
    public Game.Prefabs.UITagPrefab m_TutorialsToggle;
    public Game.Prefabs.UITagPrefab m_WorkspaceTitleBar;
    public Game.Prefabs.UITagPrefab m_SelectProjectRoot;
    public Game.Prefabs.UITagPrefab m_SelectAssets;
    public Game.Prefabs.UITagPrefab m_SelectTemplate;
    public Game.Prefabs.UITagPrefab m_ImportButton;
    public Game.Prefabs.UITagPrefab m_ModifyTerrainButton;

    public ManualUITagsConfiguration();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.UITagPrefab m_ChirperPanel`  

```csharp
public Game.Prefabs.UITagPrefab m_ChirperPanel;
```

- `public Game.Prefabs.UITagPrefab m_ChirperPanelButton`  

```csharp
public Game.Prefabs.UITagPrefab m_ChirperPanelButton;
```

- `public Game.Prefabs.UITagPrefab m_ChirperPanelChirps`  

```csharp
public Game.Prefabs.UITagPrefab m_ChirperPanelChirps;
```

- `public Game.Prefabs.UITagPrefab m_CityInfoPanel`  

```csharp
public Game.Prefabs.UITagPrefab m_CityInfoPanel;
```

- `public Game.Prefabs.UITagPrefab m_CityInfoPanelButton`  

```csharp
public Game.Prefabs.UITagPrefab m_CityInfoPanelButton;
```

- `public Game.Prefabs.UITagPrefab m_CityInfoPanelDemandPage`  

```csharp
public Game.Prefabs.UITagPrefab m_CityInfoPanelDemandPage;
```

- `public Game.Prefabs.UITagPrefab m_CityInfoPanelDemandTab`  

```csharp
public Game.Prefabs.UITagPrefab m_CityInfoPanelDemandTab;
```

- `public Game.Prefabs.UITagPrefab m_CityInfoPanelPoliciesPage`  

```csharp
public Game.Prefabs.UITagPrefab m_CityInfoPanelPoliciesPage;
```

- `public Game.Prefabs.UITagPrefab m_CityInfoPanelPoliciesTab`  

```csharp
public Game.Prefabs.UITagPrefab m_CityInfoPanelPoliciesTab;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelBudgetBalance`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelBudgetBalance;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelBudgetExpenses`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelBudgetExpenses;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelBudgetPage`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelBudgetPage;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelBudgetRevenue`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelBudgetRevenue;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelBudgetTab`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelBudgetTab;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelButton`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelButton;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelLoansAccept`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelLoansAccept;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelLoansPage`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelLoansPage;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelLoansSlider`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelLoansSlider;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelLoansTab`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelLoansTab;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelProductionPage`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelProductionPage;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelProductionResources`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelProductionResources;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelProductionTab`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelProductionTab;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelServicesBudget`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelServicesBudget;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelServicesList`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelServicesList;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelServicesPage`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelServicesPage;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelServicesTab`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelServicesTab;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelTaxationEstimate`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelTaxationEstimate;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelTaxationPage`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelTaxationPage;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelTaxationRate`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelTaxationRate;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelTaxationTab`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelTaxationTab;
```

- `public Game.Prefabs.UITagPrefab m_EconomyPanelTaxationType`  

```csharp
public Game.Prefabs.UITagPrefab m_EconomyPanelTaxationType;
```

- `public Game.Prefabs.UITagPrefab m_EventJournalPanel`  

```csharp
public Game.Prefabs.UITagPrefab m_EventJournalPanel;
```

- `public Game.Prefabs.UITagPrefab m_EventJournalPanelButton`  

```csharp
public Game.Prefabs.UITagPrefab m_EventJournalPanelButton;
```

- `public Game.Prefabs.UITagPrefab m_InfoviewsButton`  

```csharp
public Game.Prefabs.UITagPrefab m_InfoviewsButton;
```

- `public Game.Prefabs.UITagPrefab m_InfoviewsMenu`  

```csharp
public Game.Prefabs.UITagPrefab m_InfoviewsMenu;
```

- `public Game.Prefabs.UITagPrefab m_InfoviewsPanel`  

```csharp
public Game.Prefabs.UITagPrefab m_InfoviewsPanel;
```

- `public Game.Prefabs.UITagPrefab m_InfoviewsFireHazard`  

```csharp
public Game.Prefabs.UITagPrefab m_InfoviewsFireHazard;
```

- `public Game.Prefabs.UITagPrefab m_LifePathPanel`  

```csharp
public Game.Prefabs.UITagPrefab m_LifePathPanel;
```

- `public Game.Prefabs.UITagPrefab m_LifePathPanelBackButton`  

```csharp
public Game.Prefabs.UITagPrefab m_LifePathPanelBackButton;
```

- `public Game.Prefabs.UITagPrefab m_LifePathPanelButton`  

```csharp
public Game.Prefabs.UITagPrefab m_LifePathPanelButton;
```

- `public Game.Prefabs.UITagPrefab m_LifePathPanelChirps`  

```csharp
public Game.Prefabs.UITagPrefab m_LifePathPanelChirps;
```

- `public Game.Prefabs.UITagPrefab m_LifePathPanelDetails`  

```csharp
public Game.Prefabs.UITagPrefab m_LifePathPanelDetails;
```

- `public Game.Prefabs.UITagPrefab m_MapTilePanel`  

```csharp
public Game.Prefabs.UITagPrefab m_MapTilePanel;
```

- `public Game.Prefabs.UITagPrefab m_MapTilePanelButton`  

```csharp
public Game.Prefabs.UITagPrefab m_MapTilePanelButton;
```

- `public Game.Prefabs.UITagPrefab m_MapTilePanelResources`  

```csharp
public Game.Prefabs.UITagPrefab m_MapTilePanelResources;
```

- `public Game.Prefabs.UITagPrefab m_MapTilePanelPurchase`  

```csharp
public Game.Prefabs.UITagPrefab m_MapTilePanelPurchase;
```

- `public Game.Prefabs.UITagPrefab m_PhotoModePanel`  

```csharp
public Game.Prefabs.UITagPrefab m_PhotoModePanel;
```

- `public Game.Prefabs.UITagPrefab m_PhotoModePanelButton`  

```csharp
public Game.Prefabs.UITagPrefab m_PhotoModePanelButton;
```

- `public Game.Prefabs.UITagPrefab m_PhotoModePanelHideUI`  

```csharp
public Game.Prefabs.UITagPrefab m_PhotoModePanelHideUI;
```

- `public Game.Prefabs.UITagPrefab m_PhotoModePanelTakePicture`  

```csharp
public Game.Prefabs.UITagPrefab m_PhotoModePanelTakePicture;
```

- `public Game.Prefabs.UITagPrefab m_PhotoModeTab`  

```csharp
public Game.Prefabs.UITagPrefab m_PhotoModeTab;
```

- `public Game.Prefabs.UITagPrefab m_PhotoModePanelTitle`  

```csharp
public Game.Prefabs.UITagPrefab m_PhotoModePanelTitle;
```

- `public Game.Prefabs.UITagPrefab m_PhotoModeCinematicCameraToggle`  

```csharp
public Game.Prefabs.UITagPrefab m_PhotoModeCinematicCameraToggle;
```

- `public Game.Prefabs.UITagPrefab m_CinematicCameraPanel`  

```csharp
public Game.Prefabs.UITagPrefab m_CinematicCameraPanel;
```

- `public Game.Prefabs.UITagPrefab m_CinematicCameraPanelCaptureKey`  

```csharp
public Game.Prefabs.UITagPrefab m_CinematicCameraPanelCaptureKey;
```

- `public Game.Prefabs.UITagPrefab m_CinematicCameraPanelPlay`  

```csharp
public Game.Prefabs.UITagPrefab m_CinematicCameraPanelPlay;
```

- `public Game.Prefabs.UITagPrefab m_CinematicCameraPanelStop`  

```csharp
public Game.Prefabs.UITagPrefab m_CinematicCameraPanelStop;
```

- `public Game.Prefabs.UITagPrefab m_CinematicCameraPanelHideUI`  

```csharp
public Game.Prefabs.UITagPrefab m_CinematicCameraPanelHideUI;
```

- `public Game.Prefabs.UITagPrefab m_CinematicCameraPanelSaveLoad`  

```csharp
public Game.Prefabs.UITagPrefab m_CinematicCameraPanelSaveLoad;
```

- `public Game.Prefabs.UITagPrefab m_CinematicCameraPanelReset`  

```csharp
public Game.Prefabs.UITagPrefab m_CinematicCameraPanelReset;
```

- `public Game.Prefabs.UITagPrefab m_CinematicCameraPanelTimelineSlider`  

```csharp
public Game.Prefabs.UITagPrefab m_CinematicCameraPanelTimelineSlider;
```

- `public Game.Prefabs.UITagPrefab m_CinematicCameraPanelTransformCurves`  

```csharp
public Game.Prefabs.UITagPrefab m_CinematicCameraPanelTransformCurves;
```

- `public Game.Prefabs.UITagPrefab m_CinematicCameraPanelPropertyCurves`  

```csharp
public Game.Prefabs.UITagPrefab m_CinematicCameraPanelPropertyCurves;
```

- `public Game.Prefabs.UITagPrefab m_CinematicCameraPanelPlaybackDurationSlider`  

```csharp
public Game.Prefabs.UITagPrefab m_CinematicCameraPanelPlaybackDurationSlider;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanel`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanel;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanelButton`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanelButton;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentNode`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentNode;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentPage`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentPage;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentService`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentService;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentTab`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentTab;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentUnlockableNode`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentUnlockableNode;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentUnlockNode`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanelDevelopmentUnlockNode;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestoneRewards`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestoneRewards;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestoneRewardsMoney`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestoneRewardsMoney;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestoneRewardsDevPoints`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestoneRewardsDevPoints;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestoneRewardsMapTiles`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestoneRewardsMapTiles;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestonesList`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestonesList;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestonesPage`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestonesPage;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestonesTab`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestonesTab;
```

- `public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestoneXP`  

```csharp
public Game.Prefabs.UITagPrefab m_ProgressionPanelMilestoneXP;
```

- `public Game.Prefabs.UITagPrefab m_RadioPanel`  

```csharp
public Game.Prefabs.UITagPrefab m_RadioPanel;
```

- `public Game.Prefabs.UITagPrefab m_RadioPanelAdsToggle`  

```csharp
public Game.Prefabs.UITagPrefab m_RadioPanelAdsToggle;
```

- `public Game.Prefabs.UITagPrefab m_RadioPanelButton`  

```csharp
public Game.Prefabs.UITagPrefab m_RadioPanelButton;
```

- `public Game.Prefabs.UITagPrefab m_RadioPanelNetworks`  

```csharp
public Game.Prefabs.UITagPrefab m_RadioPanelNetworks;
```

- `public Game.Prefabs.UITagPrefab m_RadioPanelStations`  

```csharp
public Game.Prefabs.UITagPrefab m_RadioPanelStations;
```

- `public Game.Prefabs.UITagPrefab m_RadioPanelVolumeSlider`  

```csharp
public Game.Prefabs.UITagPrefab m_RadioPanelVolumeSlider;
```

- `public Game.Prefabs.UITagPrefab m_StatisticsPanel`  

```csharp
public Game.Prefabs.UITagPrefab m_StatisticsPanel;
```

- `public Game.Prefabs.UITagPrefab m_StatisticsPanelButton`  

```csharp
public Game.Prefabs.UITagPrefab m_StatisticsPanelButton;
```

- `public Game.Prefabs.UITagPrefab m_StatisticsPanelMenu`  

```csharp
public Game.Prefabs.UITagPrefab m_StatisticsPanelMenu;
```

- `public Game.Prefabs.UITagPrefab m_StatisticsPanelTimeScale`  

```csharp
public Game.Prefabs.UITagPrefab m_StatisticsPanelTimeScale;
```

- `public Game.Prefabs.UITagPrefab m_ToolbarBulldozerBar`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolbarBulldozerBar;
```

- `public Game.Prefabs.UITagPrefab m_ToolbarDemand`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolbarDemand;
```

- `public Game.Prefabs.UITagPrefab m_ToolbarSimulationDateTime`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolbarSimulationDateTime;
```

- `public Game.Prefabs.UITagPrefab m_ToolbarSimulationSpeed`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolbarSimulationSpeed;
```

- `public Game.Prefabs.UITagPrefab m_ToolbarSimulationToggle`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolbarSimulationToggle;
```

- `public Game.Prefabs.UITagPrefab m_ToolbarUnderground`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolbarUnderground;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptions`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptions;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsBrushSize`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsBrushSize;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsBrushStrength`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsBrushStrength;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsElevation`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsElevation;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsElevationDecrease`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsElevationDecrease;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsElevationIncrease`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsElevationIncrease;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsElevationStep`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsElevationStep;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsModes`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsModes;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsModesComplexCurve`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsModesComplexCurve;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsModesContinuous`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsModesContinuous;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsModesGrid`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsModesGrid;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsModesReplace`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsModesReplace;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsModesSimpleCurve`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsModesSimpleCurve;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsModesStraight`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsModesStraight;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsParallelMode`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsParallelMode;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsParallelModeOffset`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsParallelModeOffset;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsParallelModeOffsetDecrease`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsParallelModeOffsetDecrease;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsParallelModeOffsetIncrease`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsParallelModeOffsetIncrease;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsSnapping`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsSnapping;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsThemes`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsThemes;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsAssetPacks`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsAssetPacks;
```

- `public Game.Prefabs.UITagPrefab m_ToolOptionsUnderground`  

```csharp
public Game.Prefabs.UITagPrefab m_ToolOptionsUnderground;
```

- `public Game.Prefabs.UITagPrefab m_TransportationOverviewPanel`  

```csharp
public Game.Prefabs.UITagPrefab m_TransportationOverviewPanel;
```

- `public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelButton`  

```csharp
public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelButton;
```

- `public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelLegend`  

```csharp
public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelLegend;
```

- `public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelLines`  

```csharp
public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelLines;
```

- `public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelTabCargo`  

```csharp
public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelTabCargo;
```

- `public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelTabPublicTransport`  

```csharp
public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelTabPublicTransport;
```

- `public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelTransportTypes`  

```csharp
public Game.Prefabs.UITagPrefab m_TransportationOverviewPanelTransportTypes;
```

- `public Game.Prefabs.UITagPrefab m_SelectedInfoPanel`  

```csharp
public Game.Prefabs.UITagPrefab m_SelectedInfoPanel;
```

- `public Game.Prefabs.UITagPrefab m_SelectedInfoPanelTitle`  

```csharp
public Game.Prefabs.UITagPrefab m_SelectedInfoPanelTitle;
```

- `public Game.Prefabs.UITagPrefab m_SelectedInfoPanelPolicies`  

```csharp
public Game.Prefabs.UITagPrefab m_SelectedInfoPanelPolicies;
```

- `public Game.Prefabs.UITagPrefab m_SelectedInfoPanelDelete`  

```csharp
public Game.Prefabs.UITagPrefab m_SelectedInfoPanelDelete;
```

- `public Game.Prefabs.UITagPrefab m_PauseMenuButton`  

```csharp
public Game.Prefabs.UITagPrefab m_PauseMenuButton;
```

- `public Game.Prefabs.UITagPrefab m_UpgradeGrid`  

```csharp
public Game.Prefabs.UITagPrefab m_UpgradeGrid;
```

- `public Game.Prefabs.UITagPrefab m_AssetGrid`  

```csharp
public Game.Prefabs.UITagPrefab m_AssetGrid;
```

- `public Game.Prefabs.UITagPrefab m_ActionHints`  

```csharp
public Game.Prefabs.UITagPrefab m_ActionHints;
```

- `public Game.Prefabs.UITagPrefab m_AssetImportButton`  

```csharp
public Game.Prefabs.UITagPrefab m_AssetImportButton;
```

- `public Game.Prefabs.UITagPrefab m_EditorInfoViewsPanel`  

```csharp
public Game.Prefabs.UITagPrefab m_EditorInfoViewsPanel;
```

- `public Game.Prefabs.UITagPrefab m_ResetTODButton`  

```csharp
public Game.Prefabs.UITagPrefab m_ResetTODButton;
```

- `public Game.Prefabs.UITagPrefab m_SimulationPlayButton`  

```csharp
public Game.Prefabs.UITagPrefab m_SimulationPlayButton;
```

- `public Game.Prefabs.UITagPrefab m_TutorialsToggle`  

```csharp
public Game.Prefabs.UITagPrefab m_TutorialsToggle;
```

- `public Game.Prefabs.UITagPrefab m_WorkspaceTitleBar`  

```csharp
public Game.Prefabs.UITagPrefab m_WorkspaceTitleBar;
```

- `public Game.Prefabs.UITagPrefab m_SelectProjectRoot`  

```csharp
public Game.Prefabs.UITagPrefab m_SelectProjectRoot;
```

- `public Game.Prefabs.UITagPrefab m_SelectAssets`  

```csharp
public Game.Prefabs.UITagPrefab m_SelectAssets;
```

- `public Game.Prefabs.UITagPrefab m_SelectTemplate`  

```csharp
public Game.Prefabs.UITagPrefab m_SelectTemplate;
```

- `public Game.Prefabs.UITagPrefab m_ImportButton`  

```csharp
public Game.Prefabs.UITagPrefab m_ImportButton;
```

- `public Game.Prefabs.UITagPrefab m_ModifyTerrainButton`  

```csharp
public Game.Prefabs.UITagPrefab m_ModifyTerrainButton;
```


## Constructors

- `public ManualUITagsConfiguration()`  

```csharp
public ManualUITagsConfiguration();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		prefabs.Add(m_ChirperPanel);
		prefabs.Add(m_ChirperPanelButton);
		prefabs.Add(m_ChirperPanelChirps);
		prefabs.Add(m_CityInfoPanel);
		prefabs.Add(m_CityInfoPanelButton);
		prefabs.Add(m_CityInfoPanelDemandPage);
		prefabs.Add(m_CityInfoPanelDemandTab);
		prefabs.Add(m_CityInfoPanelPoliciesPage);
		prefabs.Add(m_CityInfoPanelPoliciesTab);
		prefabs.Add(m_EconomyPanelBudgetBalance);
		prefabs.Add(m_EconomyPanelBudgetExpenses);
		prefabs.Add(m_EconomyPanelBudgetPage);
		prefabs.Add(m_EconomyPanelBudgetRevenue);
		prefabs.Add(m_EconomyPanelBudgetTab);
		prefabs.Add(m_EconomyPanelButton);
		prefabs.Add(m_EconomyPanelLoansAccept);
		prefabs.Add(m_EconomyPanelLoansPage);
		prefabs.Add(m_EconomyPanelLoansSlider);
		prefabs.Add(m_EconomyPanelLoansTab);
		prefabs.Add(m_EconomyPanelProductionPage);
		prefabs.Add(m_EconomyPanelProductionResources);
		prefabs.Add(m_EconomyPanelProductionTab);
		prefabs.Add(m_EconomyPanelServicesBudget);
		prefabs.Add(m_EconomyPanelServicesList);
		prefabs.Add(m_EconomyPanelServicesPage);
		prefabs.Add(m_EconomyPanelServicesTab);
		prefabs.Add(m_EconomyPanelTaxationEstimate);
		prefabs.Add(m_EconomyPanelTaxationPage);
		prefabs.Add(m_EconomyPanelTaxationRate);
		prefabs.Add(m_EconomyPanelTaxationTab);
		prefabs.Add(m_EconomyPanelTaxationType);
		prefabs.Add(m_EventJournalPanel);
		prefabs.Add(m_EventJournalPanelButton);
		prefabs.Add(m_InfoviewsButton);
		prefabs.Add(m_InfoviewsMenu);
		prefabs.Add(m_InfoviewsPanel);
		prefabs.Add(m_InfoviewsFireHazard);
		prefabs.Add(m_LifePathPanel);
		prefabs.Add(m_LifePathPanelBackButton);
		prefabs.Add(m_LifePathPanelButton);
		prefabs.Add(m_LifePathPanelChirps);
		prefabs.Add(m_LifePathPanelDetails);
		prefabs.Add(m_MapTilePanel);
		prefabs.Add(m_MapTilePanelButton);
		prefabs.Add(m_MapTilePanelResources);
		prefabs.Add(m_MapTilePanelPurchase);
		prefabs.Add(m_PhotoModePanel);
		prefabs.Add(m_PhotoModePanelButton);
		prefabs.Add(m_PhotoModePanelHideUI);
		prefabs.Add(m_PhotoModePanelTakePicture);
		prefabs.Add(m_PhotoModeTab);
		prefabs.Add(m_PhotoModePanelTitle);
		prefabs.Add(m_PhotoModeCinematicCameraToggle);
		prefabs.Add(m_CinematicCameraPanel);
		prefabs.Add(m_CinematicCameraPanelCaptureKey);
		prefabs.Add(m_CinematicCameraPanelPlay);
		prefabs.Add(m_CinematicCameraPanelStop);
		prefabs.Add(m_CinematicCameraPanelHideUI);
		prefabs.Add(m_CinematicCameraPanelSaveLoad);
		prefabs.Add(m_CinematicCameraPanelReset);
		prefabs.Add(m_CinematicCameraPanelTimelineSlider);
		prefabs.Add(m_CinematicCameraPanelTransformCurves);
		prefabs.Add(m_CinematicCameraPanelPropertyCurves);
		prefabs.Add(m_ProgressionPanel);
		prefabs.Add(m_ProgressionPanelButton);
		prefabs.Add(m_ProgressionPanelDevelopmentNode);
		prefabs.Add(m_ProgressionPanelDevelopmentPage);
		prefabs.Add(m_ProgressionPanelDevelopmentService);
		prefabs.Add(m_ProgressionPanelDevelopmentTab);
		prefabs.Add(m_ProgressionPanelDevelopmentUnlockableNode);
		prefabs.Add(m_ProgressionPanelDevelopmentUnlockNode);
		prefabs.Add(m_ProgressionPanelMilestoneRewards);
		prefabs.Add(m_ProgressionPanelMilestoneRewardsMoney);
		prefabs.Add(m_ProgressionPanelMilestoneRewardsDevPoints);
		prefabs.Add(m_ProgressionPanelMilestoneRewardsMapTiles);
		prefabs.Add(m_ProgressionPanelMilestonesList);
		prefabs.Add(m_ProgressionPanelMilestonesPage);
		prefabs.Add(m_ProgressionPanelMilestonesTab);
		prefabs.Add(m_ProgressionPanelMilestoneXP);
		prefabs.Add(m_RadioPanel);
		prefabs.Add(m_RadioPanelAdsToggle);
		prefabs.Add(m_RadioPanelButton);
		prefabs.Add(m_RadioPanelNetworks);
		prefabs.Add(m_RadioPanelStations);
		prefabs.Add(m_RadioPanelVolumeSlider);
		prefabs.Add(m_StatisticsPanel);
		prefabs.Add(m_StatisticsPanelButton);
		prefabs.Add(m_StatisticsPanelMenu);
		prefabs.Add(m_StatisticsPanelTimeScale);
		prefabs.Add(m_ToolbarBulldozerBar);
		prefabs.Add(m_ToolbarDemand);
		prefabs.Add(m_ToolbarSimulationDateTime);
		prefabs.Add(m_ToolbarSimulationSpeed);
		prefabs.Add(m_ToolbarSimulationToggle);
		prefabs.Add(m_ToolbarUnderground);
		prefabs.Add(m_ToolOptions);
		prefabs.Add(m_ToolOptionsBrushSize);
		prefabs.Add(m_ToolOptionsBrushStrength);
		prefabs.Add(m_ToolOptionsElevation);
		prefabs.Add(m_ToolOptionsElevationDecrease);
		prefabs.Add(m_ToolOptionsElevationIncrease);
		prefabs.Add(m_ToolOptionsElevationStep);
		prefabs.Add(m_ToolOptionsModes);
		prefabs.Add(m_ToolOptionsModesComplexCurve);
		prefabs.Add(m_ToolOptionsModesContinuous);
		prefabs.Add(m_ToolOptionsModesGrid);
		prefabs.Add(m_ToolOptionsModesReplace);
		prefabs.Add(m_ToolOptionsModesSimpleCurve);
		prefabs.Add(m_ToolOptionsModesStraight);
		prefabs.Add(m_ToolOptionsParallelMode);
		prefabs.Add(m_ToolOptionsParallelModeOffset);
		prefabs.Add(m_ToolOptionsParallelModeOffsetDecrease);
		prefabs.Add(m_ToolOptionsParallelModeOffsetIncrease);
		prefabs.Add(m_ToolOptionsSnapping);
		prefabs.Add(m_ToolOptionsThemes);
		prefabs.Add(m_ToolOptionsAssetPacks);
		prefabs.Add(m_ToolOptionsUnderground);
		prefabs.Add(m_TransportationOverviewPanel);
		prefabs.Add(m_TransportationOverviewPanelButton);
		prefabs.Add(m_TransportationOverviewPanelLegend);
		prefabs.Add(m_TransportationOverviewPanelLines);
		prefabs.Add(m_TransportationOverviewPanelTabCargo);
		prefabs.Add(m_TransportationOverviewPanelTabPublicTransport);
		prefabs.Add(m_TransportationOverviewPanelTransportTypes);
		prefabs.Add(m_SelectedInfoPanel);
		prefabs.Add(m_SelectedInfoPanelTitle);
		prefabs.Add(m_PauseMenuButton);
		prefabs.Add(m_UpgradeGrid);
		prefabs.Add(m_AssetGrid);
		prefabs.Add(m_ActionHints);
		prefabs.Add(m_AssetImportButton);
		prefabs.Add(m_EditorInfoViewsPanel);
		prefabs.Add(m_ResetTODButton);
		prefabs.Add(m_SimulationPlayButton);
		prefabs.Add(m_TutorialsToggle);
		prefabs.Add(m_WorkspaceTitleBar);
		prefabs.Add(m_SelectProjectRoot);
		prefabs.Add(m_SelectAssets);
		prefabs.Add(m_SelectTemplate);
		prefabs.Add(m_ImportButton);
		prefabs.Add(m_ModifyTerrainButton);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<ManualUITagsConfigurationData>());
	}
```


