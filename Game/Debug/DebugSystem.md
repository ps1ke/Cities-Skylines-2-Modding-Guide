# Game.Debug.DebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `UnityEngine.Rendering.IDebugData`  

**Attributes:** `DebugContainer`, `CompilerGenerated`  

## Code

```csharp
public class DebugSystem : Game.GameSystemBase, UnityEngine.Rendering.IDebugData
{
    private System.String m_CommonComponentsFilter;
    private System.Boolean m_CommonComponentsUnused;
    private System.Collections.Generic.List<Game.Debug.ComponentDebugUtils+ComponentInfo> m_CommonComponents;
    private System.Collections.Generic.List<System.Object> m_DebugClasses;
    private System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>> m_Panels;
    private Game.Prefabs.PrefabBase m_LastToolPrefab;
    private System.Int32 m_ArchetypeCount;
    private System.Int32 m_FilteredArchetypeCount;
    private System.Int32 m_ChunkCount;
    private System.Int32 m_ChunkCapacity;
    private System.Int32 m_EntityCount;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.ZoneSpawnSystem m_ZoneSpawnSystem;
    private Game.Simulation.AreaSpawnSystem m_AreaSpawnSystem;
    private Game.Simulation.BuildingUpkeepSystem m_BuildingUpkeepSystem;
    private Game.Simulation.HouseholdFindPropertySystem m_HouseholdFindPropertySystem;
    private Game.Simulation.GraduationSystem m_GraduationSystem;
    private Game.Simulation.CrimeCheckSystem m_CrimeCheckSystem;
    private Game.Simulation.ApplyToSchoolSystem m_ApplyToSchoolSystem;
    private Game.Simulation.FindSchoolSystem m_FindSchoolSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.UI.Debug.DebugUISystem m_DebugUISystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.SnowSystem m_SnowSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private Game.Simulation.PlanetarySystem m_PlanetarySystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Rendering.ClimateRenderSystem m_ClimateRenderSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Game.Simulation.AdjustElectricityConsumptionSystem m_AdjustElectricityConsumptionSystem;
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Simulation.DispatchWaterSystem m_DispatchWaterSystem;
    private Game.Prefabs.UnlockAllSystem m_UnlockAllSystem;
    private Game.Simulation.TripNeededSystem m_TripNeededSystem;
    private Game.Triggers.LifePathEventSystem m_LifePathEventSystem;
    private Game.Simulation.BirthSystem m_BirthSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.UI.InGame.SignatureBuildingUISystem m_SignatureBuildingUISystem;
    private Unity.Entities.EntityQuery m_DebugQuery;
    private Unity.Entities.EntityQuery m_PolicyQuery;
    private Unity.Entities.EntityQuery m_NetQuery;
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Unity.Entities.EntityQuery m_ZoneQuery;
    private Unity.Entities.EntityQuery m_AreaQuery;
    private Unity.Entities.EntityQuery m_RouteQuery;
    private Unity.Entities.EntityQuery m_TerraformingQuery;
    private Unity.Entities.EntityQuery m_InfoviewQuery;
    private Unity.Entities.EntityQuery m_ThemeQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Unity.Entities.EntityQuery m_PollutionParameterQuery;
    private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
    private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
    private Unity.Entities.EntityQuery m_HealthcareParameterQuery;
    private Unity.Entities.EntityQuery m_ParkParameterQuery;
    private Unity.Entities.EntityQuery m_EducationParameterQuery;
    private Unity.Entities.EntityQuery m_TelecomParameterQuery;
    private Unity.Entities.EntityQuery m_GarbageParameterQuery;
    private Unity.Entities.EntityQuery m_PoliceParameterQuery;
    private Unity.Entities.EntityQuery m_LandValueQuery;
    private Unity.Entities.EntityQuery m_RenterQuery;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_SelectableQuery;
    private Unity.Entities.EntityQuery m_ServiceQuery;
    private Unity.Entities.EntityQuery m_TradeCostQuery;
    private Unity.Entities.EntityQuery m_TransferQuery;
    private Unity.Entities.EntityQuery m_TripNeededQuery;
    private Unity.Entities.EntityQuery m_HouseholdGroup;
    private Unity.Entities.EntityQuery m_HouseholdMemberGroup;
    private Unity.Entities.EntityQuery m_AtmosphereQuery;
    private Unity.Entities.EntityQuery m_BiomeQuery;
    private Unity.Entities.EntityQuery m_IconQuery;
    private Unity.Entities.EntityQuery m_CompanyGroup;
    private Unity.Entities.EntityQuery m_SignatureBuildingQuery;
    private Unity.Entities.EntityArchetype m_PolicyEventArchetype;
    private Unity.Mathematics.float3 m_LastSelectionPosition;
    private System.Boolean m_FastForwardClimateTime;
    private System.Int32 selectedModeIndex;
    private System.Boolean m_RenderingDebugUIInitialized;
    private Colossal.Rendering.DebugCustomPass m_DebugBlitPass;
    private UnityEngine.GameObject m_DebugBlitVolume;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Effects.EffectControlSystem m_EffectControlSystem;
    private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem;
    private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem;
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Game.Rendering.AreaBatchSystem m_AreaBatchSystem;
    private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
    private Game.Rendering.AnimatedSystem m_AnimatedSystem;
    private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
    private Game.Rendering.VegetationRenderSystem m_VegetationRenderSystem;
    private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private System.Collections.Generic.List<Game.Debug.DebugSystem+NotificationInfo> m_Notifications;
    private System.Collections.Generic.List<Game.Debug.DebugSystem+PathfindQueryItem> m_PathfindQueryBuffer;
    private System.Collections.Generic.List<Game.Debug.DebugSystem+SerializationItem> m_SerializationBuffer;
    private Game.Debug.DebugSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1508003740_0;
    private static readonly UnityEngine.GUIContent[] kDebugSimulationSpeedStrings;
    private static readonly System.Single[] kDebugSimulationSpeedValues;
    private static readonly UnityEngine.GUIContent[] kDebugWaterSpeedStrings;
    private static System.Int32[] m_DebugWaterSpeedValues;
    private static Game.Tools.ToolBaseSystem[] m_ToolSystems;
    private static UnityEngine.GUIContent[] m_ToolSystemNames;
    private static const System.String kDebugSaveName;

    public DebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Game.Tools.ToolBaseSystem <__BuildSimulationDebugUI_1F128DF8>b__249_0();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_1(Game.Tools.ToolBaseSystem value);
    private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_100();
    private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_101();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_102();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_103();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_104();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_105();
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_106();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_107(System.Single value);
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_110();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_111(System.Boolean value);
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_112();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_113(System.Boolean value);
    private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_114();
    private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_115();
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_116();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_117(System.Single value);
    private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_12();
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_120();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_121(System.Single value);
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_124();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_125(System.Single value);
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_128();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_129(System.Single value);
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_13();
    private System.Int32 <__BuildSimulationDebugUI_1F128DF8>b__249_132();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_133(System.Int32 value);
    private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_135();
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_136();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_137(System.Boolean value);
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_138();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_139(System.Single value);
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_14(System.Boolean value);
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_142();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_143();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_144();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_145();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_148();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_149();
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_15();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_151();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_152();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_153();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_154();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_155();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_156();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_157();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_158();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_159();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_16(System.Boolean value);
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_160();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_161();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_162();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_163();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_164();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_165();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_168(UnityEngine.Rendering.DebugUI+Field<System.String> field, System.String value);
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_169();
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_17();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_170();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_171();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_172();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_173();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_174();
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_175();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_176(System.Boolean value);
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_177();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_178(System.Boolean value);
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_179();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_18(System.Boolean value);
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_180(System.Boolean value);
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_181();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_182();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_19();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_2();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_20();
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_21();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_217();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_218();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_219();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_22(System.Boolean value);
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_220();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_221();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_222();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_223();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_224();
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_225();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_226(System.Single value);
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_229();
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_23();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_230(System.Single value);
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_24(System.Boolean value);
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_25();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_26(System.Boolean value);
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_27();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_28(System.Boolean value);
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_29();
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_3();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_30(System.Boolean value);
    private System.Int32 <__BuildSimulationDebugUI_1F128DF8>b__249_31();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_32(System.Int32 value);
    private System.Int32 <__BuildSimulationDebugUI_1F128DF8>b__249_35();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_36(System.Int32 value);
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_39();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_4(System.Single value);
    private System.Int32 <__BuildSimulationDebugUI_1F128DF8>b__249_42();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_43(System.Int32 value);
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_44();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_45();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_46();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_47();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_48();
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_49();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_5();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_50(System.Single value);
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_53();
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_54();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_55(System.Single value);
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_58();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_59(System.Boolean value);
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_6();
    private System.Int32 <__BuildSimulationDebugUI_1F128DF8>b__249_60();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_61(System.Int32 value);
    private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_64();
    private System.Int32 <__BuildSimulationDebugUI_1F128DF8>b__249_65();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_66(System.Int32 value);
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_69();
    private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_7();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_70(System.Boolean value);
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_71();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_72(System.Boolean value);
    private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_73();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_74(System.Boolean value);
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_75();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_76(System.Single value);
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_79();
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_8();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_80(System.Single value);
    private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_83();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_84(System.Single value);
    private Game.OverridableProperty<System.Single> <__BuildSimulationDebugUI_1F128DF8>b__249_87();
    private Game.OverridableProperty<System.Single> <__BuildSimulationDebugUI_1F128DF8>b__249_88();
    private System.Int32 <__BuildSimulationDebugUI_1F128DF8>b__249_89();
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_9(System.Single value);
    private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_90(System.Int32 value);
    private Game.OverridableProperty<System.Single> <__BuildSimulationDebugUI_1F128DF8>b__249_91();
    private Game.OverridableProperty<System.Single> <__BuildSimulationDebugUI_1F128DF8>b__249_92();
    private Game.OverridableProperty<System.Single> <__BuildSimulationDebugUI_1F128DF8>b__249_93();
    private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_94();
    private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_95();
    private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_96();
    private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_97();
    private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_98();
    private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_99();
    internal static System.Void <AddSystemGizmoField>g__RebuildGizmosDebugUI|233_0<T, TValue>(UnityEngine.Rendering.DebugUI+Field<TValue> field, TValue value);
    private System.String <BuildECSComponentsDebugUI>b__5_0();
    private System.Void <BuildECSComponentsDebugUI>b__5_1(System.String value);
    private System.Boolean <BuildECSComponentsDebugUI>b__5_2();
    private System.Void <BuildECSComponentsDebugUI>b__5_3(System.Boolean value);
    private System.Void <BuildECSComponentsDebugUI>b__5_4();
    private System.Object <BuildECSComponentsDebugUI>b__5_5();
    private System.Object <BuildECSComponentsDebugUI>b__5_6();
    private System.Object <BuildECSComponentsDebugUI>b__5_7();
    private System.Object <BuildECSComponentsDebugUI>b__5_8();
    private System.Void <BuildingUpgradeUI>g__Upgrade|155_0(Unity.Entities.Entity upgrade);
    private System.Void <BuildNotificationsDebugUI>b__239_0();
    private UnityEngine.Rendering.DebugUI+BoolField <BuildNotificationsDebugUI>b__239_1(Game.Debug.DebugSystem+NotificationInfo info);
    private Game.Tools.ToolBaseSystem <BuildSimulationDebugUI>b__127_0();
    private System.Void <BuildSimulationDebugUI>b__127_1(Game.Tools.ToolBaseSystem value);
    private System.Object <BuildSimulationDebugUI>b__127_100();
    private System.Object <BuildSimulationDebugUI>b__127_101();
    private System.Void <BuildSimulationDebugUI>b__127_102();
    private System.Void <BuildSimulationDebugUI>b__127_103();
    private System.Void <BuildSimulationDebugUI>b__127_104();
    private System.Void <BuildSimulationDebugUI>b__127_105();
    private System.Single <BuildSimulationDebugUI>b__127_106();
    private System.Void <BuildSimulationDebugUI>b__127_107(System.Single value);
    private System.Boolean <BuildSimulationDebugUI>b__127_110();
    private System.Void <BuildSimulationDebugUI>b__127_111(System.Boolean value);
    private System.Boolean <BuildSimulationDebugUI>b__127_112();
    private System.Void <BuildSimulationDebugUI>b__127_113(System.Boolean value);
    private System.Object <BuildSimulationDebugUI>b__127_114();
    private System.Object <BuildSimulationDebugUI>b__127_115();
    private System.Single <BuildSimulationDebugUI>b__127_116();
    private System.Void <BuildSimulationDebugUI>b__127_117(System.Single value);
    private System.Object <BuildSimulationDebugUI>b__127_12();
    private System.Single <BuildSimulationDebugUI>b__127_120();
    private System.Void <BuildSimulationDebugUI>b__127_121(System.Single value);
    private System.Single <BuildSimulationDebugUI>b__127_124();
    private System.Void <BuildSimulationDebugUI>b__127_125(System.Single value);
    private System.Single <BuildSimulationDebugUI>b__127_128();
    private System.Void <BuildSimulationDebugUI>b__127_129(System.Single value);
    private System.Boolean <BuildSimulationDebugUI>b__127_13();
    private System.Int32 <BuildSimulationDebugUI>b__127_132();
    private System.Void <BuildSimulationDebugUI>b__127_133(System.Int32 value);
    private System.Object <BuildSimulationDebugUI>b__127_135();
    private System.Boolean <BuildSimulationDebugUI>b__127_136();
    private System.Void <BuildSimulationDebugUI>b__127_137(System.Boolean value);
    private System.Single <BuildSimulationDebugUI>b__127_138();
    private System.Void <BuildSimulationDebugUI>b__127_139(System.Single value);
    private System.Void <BuildSimulationDebugUI>b__127_14(System.Boolean value);
    private System.Void <BuildSimulationDebugUI>b__127_142();
    private System.Void <BuildSimulationDebugUI>b__127_143();
    private System.Void <BuildSimulationDebugUI>b__127_144();
    private System.Void <BuildSimulationDebugUI>b__127_145();
    private System.Void <BuildSimulationDebugUI>b__127_149();
    private System.Boolean <BuildSimulationDebugUI>b__127_15();
    private System.Void <BuildSimulationDebugUI>b__127_151();
    private System.Void <BuildSimulationDebugUI>b__127_152();
    private System.Void <BuildSimulationDebugUI>b__127_153();
    private System.Void <BuildSimulationDebugUI>b__127_154();
    private System.Void <BuildSimulationDebugUI>b__127_155();
    private System.Void <BuildSimulationDebugUI>b__127_156();
    private System.Void <BuildSimulationDebugUI>b__127_157();
    private System.Void <BuildSimulationDebugUI>b__127_158();
    private System.Void <BuildSimulationDebugUI>b__127_159();
    private System.Void <BuildSimulationDebugUI>b__127_16(System.Boolean value);
    private System.Void <BuildSimulationDebugUI>b__127_160();
    private System.Void <BuildSimulationDebugUI>b__127_161();
    private System.Void <BuildSimulationDebugUI>b__127_162();
    private System.Void <BuildSimulationDebugUI>b__127_163();
    private System.Void <BuildSimulationDebugUI>b__127_164();
    private System.Void <BuildSimulationDebugUI>b__127_165();
    private System.Void <BuildSimulationDebugUI>b__127_168(UnityEngine.Rendering.DebugUI+Field<System.String> field, System.String value);
    private System.Void <BuildSimulationDebugUI>b__127_169();
    private System.Boolean <BuildSimulationDebugUI>b__127_17();
    private System.Void <BuildSimulationDebugUI>b__127_170();
    private System.Void <BuildSimulationDebugUI>b__127_171();
    private System.Void <BuildSimulationDebugUI>b__127_172();
    private System.Void <BuildSimulationDebugUI>b__127_173();
    private System.Void <BuildSimulationDebugUI>b__127_174();
    private System.Boolean <BuildSimulationDebugUI>b__127_175();
    private System.Void <BuildSimulationDebugUI>b__127_176(System.Boolean value);
    private System.Boolean <BuildSimulationDebugUI>b__127_177();
    private System.Void <BuildSimulationDebugUI>b__127_178(System.Boolean value);
    private System.Boolean <BuildSimulationDebugUI>b__127_179();
    private System.Void <BuildSimulationDebugUI>b__127_18(System.Boolean value);
    private System.Void <BuildSimulationDebugUI>b__127_180(System.Boolean value);
    private System.Void <BuildSimulationDebugUI>b__127_181();
    private System.Void <BuildSimulationDebugUI>b__127_182();
    private System.Void <BuildSimulationDebugUI>b__127_19();
    private System.Void <BuildSimulationDebugUI>b__127_2();
    private System.Void <BuildSimulationDebugUI>b__127_20();
    private System.Boolean <BuildSimulationDebugUI>b__127_21();
    private System.Void <BuildSimulationDebugUI>b__127_217();
    private System.Void <BuildSimulationDebugUI>b__127_218();
    private System.Void <BuildSimulationDebugUI>b__127_219();
    private System.Void <BuildSimulationDebugUI>b__127_22(System.Boolean value);
    private System.Void <BuildSimulationDebugUI>b__127_220();
    private System.Void <BuildSimulationDebugUI>b__127_221();
    private System.Void <BuildSimulationDebugUI>b__127_222();
    private System.Void <BuildSimulationDebugUI>b__127_223();
    private System.Void <BuildSimulationDebugUI>b__127_224();
    private System.Single <BuildSimulationDebugUI>b__127_225();
    private System.Void <BuildSimulationDebugUI>b__127_226(System.Single value);
    private System.Single <BuildSimulationDebugUI>b__127_229();
    private System.Boolean <BuildSimulationDebugUI>b__127_23();
    private System.Void <BuildSimulationDebugUI>b__127_230(System.Single value);
    private System.Void <BuildSimulationDebugUI>b__127_24(System.Boolean value);
    private System.Boolean <BuildSimulationDebugUI>b__127_25();
    private System.Void <BuildSimulationDebugUI>b__127_26(System.Boolean value);
    private System.Boolean <BuildSimulationDebugUI>b__127_27();
    private System.Void <BuildSimulationDebugUI>b__127_28(System.Boolean value);
    private System.Boolean <BuildSimulationDebugUI>b__127_29();
    private System.Single <BuildSimulationDebugUI>b__127_3();
    private System.Void <BuildSimulationDebugUI>b__127_30(System.Boolean value);
    private System.Int32 <BuildSimulationDebugUI>b__127_31();
    private System.Void <BuildSimulationDebugUI>b__127_32(System.Int32 value);
    private System.Int32 <BuildSimulationDebugUI>b__127_35();
    private System.Void <BuildSimulationDebugUI>b__127_36(System.Int32 value);
    private System.Void <BuildSimulationDebugUI>b__127_39();
    private System.Void <BuildSimulationDebugUI>b__127_4(System.Single value);
    private System.Int32 <BuildSimulationDebugUI>b__127_42();
    private System.Void <BuildSimulationDebugUI>b__127_43(System.Int32 value);
    private System.Void <BuildSimulationDebugUI>b__127_44();
    private System.Void <BuildSimulationDebugUI>b__127_45();
    private System.Void <BuildSimulationDebugUI>b__127_46();
    private System.Void <BuildSimulationDebugUI>b__127_47();
    private System.Void <BuildSimulationDebugUI>b__127_48();
    private System.Single <BuildSimulationDebugUI>b__127_49();
    private System.Void <BuildSimulationDebugUI>b__127_5();
    private System.Void <BuildSimulationDebugUI>b__127_50(System.Single value);
    private System.Single <BuildSimulationDebugUI>b__127_53();
    private System.Single <BuildSimulationDebugUI>b__127_54();
    private System.Void <BuildSimulationDebugUI>b__127_55(System.Single value);
    private System.Boolean <BuildSimulationDebugUI>b__127_58();
    private System.Void <BuildSimulationDebugUI>b__127_59(System.Boolean value);
    private System.Void <BuildSimulationDebugUI>b__127_6();
    private System.Int32 <BuildSimulationDebugUI>b__127_60();
    private System.Void <BuildSimulationDebugUI>b__127_61(System.Int32 value);
    private System.Object <BuildSimulationDebugUI>b__127_64();
    private System.Int32 <BuildSimulationDebugUI>b__127_65();
    private System.Void <BuildSimulationDebugUI>b__127_66(System.Int32 value);
    private System.Boolean <BuildSimulationDebugUI>b__127_69();
    private System.Object <BuildSimulationDebugUI>b__127_7();
    private System.Void <BuildSimulationDebugUI>b__127_70(System.Boolean value);
    private System.Boolean <BuildSimulationDebugUI>b__127_71();
    private System.Void <BuildSimulationDebugUI>b__127_72(System.Boolean value);
    private System.Boolean <BuildSimulationDebugUI>b__127_73();
    private System.Void <BuildSimulationDebugUI>b__127_74(System.Boolean value);
    private System.Single <BuildSimulationDebugUI>b__127_75();
    private System.Void <BuildSimulationDebugUI>b__127_76(System.Single value);
    private System.Single <BuildSimulationDebugUI>b__127_79();
    private System.Single <BuildSimulationDebugUI>b__127_8();
    private System.Void <BuildSimulationDebugUI>b__127_80(System.Single value);
    private System.Single <BuildSimulationDebugUI>b__127_83();
    private System.Void <BuildSimulationDebugUI>b__127_84(System.Single value);
    private Game.OverridableProperty<System.Single> <BuildSimulationDebugUI>b__127_87();
    private Game.OverridableProperty<System.Single> <BuildSimulationDebugUI>b__127_88();
    private System.Int32 <BuildSimulationDebugUI>b__127_89();
    private System.Void <BuildSimulationDebugUI>b__127_9(System.Single value);
    private System.Void <BuildSimulationDebugUI>b__127_90(System.Int32 value);
    private Game.OverridableProperty<System.Single> <BuildSimulationDebugUI>b__127_91();
    private Game.OverridableProperty<System.Single> <BuildSimulationDebugUI>b__127_92();
    private Game.OverridableProperty<System.Single> <BuildSimulationDebugUI>b__127_93();
    private System.Object <BuildSimulationDebugUI>b__127_94();
    private System.Object <BuildSimulationDebugUI>b__127_95();
    private System.Object <BuildSimulationDebugUI>b__127_96();
    private System.Object <BuildSimulationDebugUI>b__127_97();
    private System.Object <BuildSimulationDebugUI>b__127_98();
    private System.Object <BuildSimulationDebugUI>b__127_99();
    private System.Object <CreateEventUI>b__172_1();
    private System.Boolean <CreateToolUI>b__153_0();
    private System.Void <CreateToolUI>b__153_1(System.Boolean value);
    internal static System.Object <GetPrimitiveUIValueObject>g__GetValue|195_0(System.Object obj);
    private System.Void <InfoviewUI>b__171_0();
    private UnityEngine.Rendering.DebugUI+IContainer AddPanel(System.String name, System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> widgets, System.Int32 groupIndex, System.Boolean overrideIfExists);
    private static System.Void AddSystemGizmoField<T>(UnityEngine.Rendering.DebugUI+Container& container, Unity.Entities.World world, UnityEngine.Rendering.DebugUI+Widget[] additionalIfEnabled);
    public System.Void AgeSelectedCitizen();
    private System.Void AreaToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
    private System.Void BitToggle(UnityEngine.Rendering.DebugUI+Container container, System.String text, Game.Tools.ToolBaseSystem tool, Game.Tools.Snap bit);
    private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildClimateUI();
    private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildECSComponentsDebugUI();
    private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildGameplayDebugUI();
    private static System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildGizmosDebugUI(Unity.Entities.World world);
    private System.Void BuildingMoveUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Void BuildingUpgradeUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity prefab);
    private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildNotificationsDebugUI();
    private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildPathfindDebugUI();
    private static System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildPlatformsDebugUI(Unity.Entities.World world);
    private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildRenderingDebugUI();
    private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildSerializationDebugUI();
    private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildSimulationDebugUI();
    private static System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildVirtualTexturingDebugUI(Unity.Entities.World world);
    private System.Void BulldozeToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
    private System.Void CacheGameRenderingDebugUISystems();
    private System.Void CalculateCustomers();
    private System.Void CalculateEligible();
    private System.Void CalculateStudentsFromOC();
    private System.Void CleanupObsoleteEntities();
    private System.Void ClearSelection();
    private System.Void CreateDebugBlitPass();
    private System.Object CreateDebugClass(System.Type type);
    private UnityEngine.Rendering.DebugUI+Foldout CreateEventUI();
    private UnityEngine.Rendering.DebugUI+Container CreateToolUI();
    private static UnityEngine.Rendering.DebugUI+Widget CreateVolumeParameterWidget(System.String name, UnityEngine.Rendering.VolumeParameter param, System.Func<System.Boolean> isHiddenCallback);
    private System.Void DefaultToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
    private System.Void DisposeDebugClasses();
    private System.String EditorDate();
    private System.Void EnableNotification(Unity.Entities.Entity entity, System.Boolean enabled);
    private System.Void ExecuteMethod(System.Reflection.MethodInfo method, System.Object target, Game.Debug.DebugTabAttribute attribute);
    private System.Void ExportHeightMap();
    private System.Void FollowSelectedCitizen();
    public System.Void FullWithGarbage();
    private System.String GetAnimBuffer();
    private System.String GetAreaBuffer();
    private UnityEngine.Rendering.DebugUI+Foldout GetArrayFoldout(System.Array record1, System.Array record2);
    private System.String GetBatchAllocation();
    private System.String GetBatchGroups();
    private System.String GetBatchMaterials();
    private System.String GetBatchMeshes();
    private System.String GetBatchRenderers();
    private System.String GetBatchUpload();
    private System.String GetBoneBuffer();
    private System.String GetEffectCulling();
    private System.String GetEntityCulling();
    private UnityEngine.Rendering.DebugUI+Foldout GetFieldValueFoldout(System.Object object1, System.Object object2);
    private System.String GetIndexBuffer();
    private System.String GetMetaBuffer();
    private UnityEngine.Rendering.DebugUI+Value GetPrimitiveUIValueObject(System.Object object1, System.Object object2);
    private System.String GetProceduralEmissiveBuffer();
    private System.String GetProceduralEmissiveUpload();
    private System.String GetProceduralSkeletonBuffer();
    private System.String GetProceduralSkeletonUpload();
    private UnityEngine.Rendering.DebugUI+Foldout GetRecordFoldout(Game.Prefabs.Modes.ModePrefab+ModeDebugUILogInfo record);
    private System.String GetShapeBuffer();
    private T GetTool<T>();
    private System.Int32[] GetWaterSpeedValues();
    private System.Void GiveMaxResources();
    private System.Void HappinessFactors();
    private UnityEngine.Rendering.DebugUI+Widget InfoviewUI();
    private System.Void InitializeRenderingDebugUI();
    private System.Void LevelUpUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Void LoadGame();
    public System.Void MaxHouseholdsWealth();
    private System.Void NetToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
    private System.Void ObjectToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    private System.Void OnSelectionChanged(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Mathematics.float3 position);
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
    private UnityEngine.Rendering.DebugUI+Container OverridableProperty<T>(System.String displayName, System.Func<T> getter, System.Single min, System.Single max, System.Single incStep);
    private System.Void PolicyUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity);
    private System.Void PrintCommuterDistribute();
    private System.Void PrintNullHouseholds();
    private UnityEngine.Rendering.DebugUI+Widget RadioSelection<T>(System.String displayName, System.Func<T> getter, System.Action<T> setter, UnityEngine.GUIContent[] names, T[] values, System.Action onValueChanged);
    public static System.Void Rebuild(System.Func<Unity.Entities.World, System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>> method);
    public static System.Void Rebuild(System.Func<System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>> method);
    private static System.Void Rebuild(System.Delegate method);
    private System.Void RebuildSimulationDebugUI<T>(UnityEngine.Rendering.DebugUI+Field<T> field, T value);
    private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> RefreshGameplayModeDebug();
    private System.Void RefreshNotifications();
    private System.Void RegisterDebug();
    private System.Void ReloadWaterSources();
    private System.Void RemoveAllHomeless();
    private System.Void RemoveAllTourist();
    private System.Void RemoveResidentsAndVehicles();
    private System.Void ResetCommercialStorage();
    public System.Void ResetCompanyMoney();
    private System.Void ResetCrimeAccumulation();
    public System.Void ResetHouseholdsWealth();
    public System.Void ResetLandvalue();
    public System.Void ResetPollution();
    public System.Void ResetRents();
    private System.Void ResetServices();
    private System.Void ResetStorages();
    private System.Void ResetTradeCosts();
    private System.Void ResetTransfers();
    private System.Void ResetTripNeeded();
    public System.Void Restart();
    private System.Void RouteToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
    private System.Void SaveGame();
    public System.Void SelectEntity(System.String searchTerm);
    private System.Void SelectEntity(Unity.Entities.Entity entity);
    private T SelectNext<T>(Unity.Entities.EntityQuery group, T current);
    private Unity.Entities.Entity SelectNext(Unity.Entities.EntityQuery group, Unity.Entities.Entity current);
    private System.Void ServiceDistrictUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity);
    private System.Void StartEvent(Unity.Entities.Entity entity);
    private System.Void TerrainToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
    private UnityEngine.Rendering.DebugUI+EnumField ToggleSelection(System.String displayName, System.Func<System.Boolean> getter, System.Action<System.Boolean> setter, System.Action<UnityEngine.Rendering.DebugUI+Field<System.Int32>, System.Int32> onValueChanged);
    private System.Void ToolBrushUI(UnityEngine.Rendering.DebugUI+Container container, Game.Tools.ToolBaseSystem tool);
    private System.Void ToolSnapUI(UnityEngine.Rendering.DebugUI+Container container, Game.Tools.ToolBaseSystem tool);
    private System.Void TriggerTestLifeEvent();
    private System.Boolean TryFindSelectableEntity(System.Int32 index, Unity.Entities.Entity& entity);
    private System.Boolean TryGetPolicy(Unity.Entities.Entity entity, Unity.Entities.Entity policyType, Game.Policies.Policy& policy);
    private System.Action UnityEngine.Rendering.IDebugData.GetReset();
    private System.Void UnregisterDebug();
    private System.Void UnregisterDebugItems(System.String panelName, System.Collections.Generic.IEnumerable<UnityEngine.Rendering.DebugUI+Widget> items);
    private System.Void UpgradeToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
    private System.Void ZoneToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
}
```


## Fields

- `private System.String m_CommonComponentsFilter`  

```csharp
private System.String m_CommonComponentsFilter;
```

- `private System.Boolean m_CommonComponentsUnused`  

```csharp
private System.Boolean m_CommonComponentsUnused;
```

- `private System.Collections.Generic.List<Game.Debug.ComponentDebugUtils+ComponentInfo> m_CommonComponents`  

```csharp
private System.Collections.Generic.List<Game.Debug.ComponentDebugUtils+ComponentInfo> m_CommonComponents;
```

- `private System.Collections.Generic.List<System.Object> m_DebugClasses`  

```csharp
private System.Collections.Generic.List<System.Object> m_DebugClasses;
```

- `private System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>> m_Panels`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>> m_Panels;
```

- `private Game.Prefabs.PrefabBase m_LastToolPrefab`  

```csharp
private Game.Prefabs.PrefabBase m_LastToolPrefab;
```

- `private System.Int32 m_ArchetypeCount`  

```csharp
private System.Int32 m_ArchetypeCount;
```

- `private System.Int32 m_FilteredArchetypeCount`  

```csharp
private System.Int32 m_FilteredArchetypeCount;
```

- `private System.Int32 m_ChunkCount`  

```csharp
private System.Int32 m_ChunkCount;
```

- `private System.Int32 m_ChunkCapacity`  

```csharp
private System.Int32 m_ChunkCapacity;
```

- `private System.Int32 m_EntityCount`  

```csharp
private System.Int32 m_EntityCount;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.ZoneSpawnSystem m_ZoneSpawnSystem`  

```csharp
private Game.Simulation.ZoneSpawnSystem m_ZoneSpawnSystem;
```

- `private Game.Simulation.AreaSpawnSystem m_AreaSpawnSystem`  

```csharp
private Game.Simulation.AreaSpawnSystem m_AreaSpawnSystem;
```

- `private Game.Simulation.BuildingUpkeepSystem m_BuildingUpkeepSystem`  

```csharp
private Game.Simulation.BuildingUpkeepSystem m_BuildingUpkeepSystem;
```

- `private Game.Simulation.HouseholdFindPropertySystem m_HouseholdFindPropertySystem`  

```csharp
private Game.Simulation.HouseholdFindPropertySystem m_HouseholdFindPropertySystem;
```

- `private Game.Simulation.GraduationSystem m_GraduationSystem`  

```csharp
private Game.Simulation.GraduationSystem m_GraduationSystem;
```

- `private Game.Simulation.CrimeCheckSystem m_CrimeCheckSystem`  

```csharp
private Game.Simulation.CrimeCheckSystem m_CrimeCheckSystem;
```

- `private Game.Simulation.ApplyToSchoolSystem m_ApplyToSchoolSystem`  

```csharp
private Game.Simulation.ApplyToSchoolSystem m_ApplyToSchoolSystem;
```

- `private Game.Simulation.FindSchoolSystem m_FindSchoolSystem`  

```csharp
private Game.Simulation.FindSchoolSystem m_FindSchoolSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem`  

```csharp
private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.UI.Debug.DebugUISystem m_DebugUISystem`  

```csharp
private Game.UI.Debug.DebugUISystem m_DebugUISystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.SnowSystem m_SnowSystem`  

```csharp
private Game.Simulation.SnowSystem m_SnowSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  

```csharp
private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
```

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  

```csharp
private Game.Simulation.PlanetarySystem m_PlanetarySystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Rendering.ClimateRenderSystem m_ClimateRenderSystem`  

```csharp
private Game.Rendering.ClimateRenderSystem m_ClimateRenderSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Game.Simulation.AdjustElectricityConsumptionSystem m_AdjustElectricityConsumptionSystem`  

```csharp
private Game.Simulation.AdjustElectricityConsumptionSystem m_AdjustElectricityConsumptionSystem;
```

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  

```csharp
private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
```

- `private Game.Simulation.DispatchWaterSystem m_DispatchWaterSystem`  

```csharp
private Game.Simulation.DispatchWaterSystem m_DispatchWaterSystem;
```

- `private Game.Prefabs.UnlockAllSystem m_UnlockAllSystem`  

```csharp
private Game.Prefabs.UnlockAllSystem m_UnlockAllSystem;
```

- `private Game.Simulation.TripNeededSystem m_TripNeededSystem`  

```csharp
private Game.Simulation.TripNeededSystem m_TripNeededSystem;
```

- `private Game.Triggers.LifePathEventSystem m_LifePathEventSystem`  

```csharp
private Game.Triggers.LifePathEventSystem m_LifePathEventSystem;
```

- `private Game.Simulation.BirthSystem m_BirthSystem`  

```csharp
private Game.Simulation.BirthSystem m_BirthSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.UI.InGame.SignatureBuildingUISystem m_SignatureBuildingUISystem`  

```csharp
private Game.UI.InGame.SignatureBuildingUISystem m_SignatureBuildingUISystem;
```

- `private Unity.Entities.EntityQuery m_DebugQuery`  

```csharp
private Unity.Entities.EntityQuery m_DebugQuery;
```

- `private Unity.Entities.EntityQuery m_PolicyQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolicyQuery;
```

- `private Unity.Entities.EntityQuery m_NetQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetQuery;
```

- `private Unity.Entities.EntityQuery m_ObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectQuery;
```

- `private Unity.Entities.EntityQuery m_ZoneQuery`  

```csharp
private Unity.Entities.EntityQuery m_ZoneQuery;
```

- `private Unity.Entities.EntityQuery m_AreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaQuery;
```

- `private Unity.Entities.EntityQuery m_RouteQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteQuery;
```

- `private Unity.Entities.EntityQuery m_TerraformingQuery`  

```csharp
private Unity.Entities.EntityQuery m_TerraformingQuery;
```

- `private Unity.Entities.EntityQuery m_InfoviewQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfoviewQuery;
```

- `private Unity.Entities.EntityQuery m_ThemeQuery`  

```csharp
private Unity.Entities.EntityQuery m_ThemeQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Unity.Entities.EntityQuery m_PollutionParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PollutionParameterQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareParameterQuery;
```

- `private Unity.Entities.EntityQuery m_ParkParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkParameterQuery;
```

- `private Unity.Entities.EntityQuery m_EducationParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EducationParameterQuery;
```

- `private Unity.Entities.EntityQuery m_TelecomParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_TelecomParameterQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageParameterQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceParameterQuery;
```

- `private Unity.Entities.EntityQuery m_LandValueQuery`  

```csharp
private Unity.Entities.EntityQuery m_LandValueQuery;
```

- `private Unity.Entities.EntityQuery m_RenterQuery`  

```csharp
private Unity.Entities.EntityQuery m_RenterQuery;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_SelectableQuery`  

```csharp
private Unity.Entities.EntityQuery m_SelectableQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceQuery;
```

- `private Unity.Entities.EntityQuery m_TradeCostQuery`  

```csharp
private Unity.Entities.EntityQuery m_TradeCostQuery;
```

- `private Unity.Entities.EntityQuery m_TransferQuery`  

```csharp
private Unity.Entities.EntityQuery m_TransferQuery;
```

- `private Unity.Entities.EntityQuery m_TripNeededQuery`  

```csharp
private Unity.Entities.EntityQuery m_TripNeededQuery;
```

- `private Unity.Entities.EntityQuery m_HouseholdGroup`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdGroup;
```

- `private Unity.Entities.EntityQuery m_HouseholdMemberGroup`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdMemberGroup;
```

- `private Unity.Entities.EntityQuery m_AtmosphereQuery`  

```csharp
private Unity.Entities.EntityQuery m_AtmosphereQuery;
```

- `private Unity.Entities.EntityQuery m_BiomeQuery`  

```csharp
private Unity.Entities.EntityQuery m_BiomeQuery;
```

- `private Unity.Entities.EntityQuery m_IconQuery`  

```csharp
private Unity.Entities.EntityQuery m_IconQuery;
```

- `private Unity.Entities.EntityQuery m_CompanyGroup`  

```csharp
private Unity.Entities.EntityQuery m_CompanyGroup;
```

- `private Unity.Entities.EntityQuery m_SignatureBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_SignatureBuildingQuery;
```

- `private Unity.Entities.EntityArchetype m_PolicyEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PolicyEventArchetype;
```

- `private Unity.Mathematics.float3 m_LastSelectionPosition`  

```csharp
private Unity.Mathematics.float3 m_LastSelectionPosition;
```

- `private System.Boolean m_FastForwardClimateTime`  

```csharp
private System.Boolean m_FastForwardClimateTime;
```

- `private System.Int32 selectedModeIndex`  

```csharp
private System.Int32 selectedModeIndex;
```

- `private System.Boolean m_RenderingDebugUIInitialized`  

```csharp
private System.Boolean m_RenderingDebugUIInitialized;
```

- `private Colossal.Rendering.DebugCustomPass m_DebugBlitPass`  

```csharp
private Colossal.Rendering.DebugCustomPass m_DebugBlitPass;
```

- `private UnityEngine.GameObject m_DebugBlitVolume`  

```csharp
private UnityEngine.GameObject m_DebugBlitVolume;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Effects.EffectControlSystem m_EffectControlSystem`  

```csharp
private Game.Effects.EffectControlSystem m_EffectControlSystem;
```

- `private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem`  

```csharp
private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem;
```

- `private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem`  

```csharp
private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem;
```

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Game.Rendering.AreaBatchSystem m_AreaBatchSystem`  

```csharp
private Game.Rendering.AreaBatchSystem m_AreaBatchSystem;
```

- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  

```csharp
private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
```

- `private Game.Rendering.AnimatedSystem m_AnimatedSystem`  

```csharp
private Game.Rendering.AnimatedSystem m_AnimatedSystem;
```

- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  

```csharp
private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
```

- `private Game.Rendering.VegetationRenderSystem m_VegetationRenderSystem`  

```csharp
private Game.Rendering.VegetationRenderSystem m_VegetationRenderSystem;
```

- `private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem`  

```csharp
private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private System.Collections.Generic.List<Game.Debug.DebugSystem+NotificationInfo> m_Notifications`  

```csharp
private System.Collections.Generic.List<Game.Debug.DebugSystem+NotificationInfo> m_Notifications;
```

- `private System.Collections.Generic.List<Game.Debug.DebugSystem+PathfindQueryItem> m_PathfindQueryBuffer`  

```csharp
private System.Collections.Generic.List<Game.Debug.DebugSystem+PathfindQueryItem> m_PathfindQueryBuffer;
```

- `private System.Collections.Generic.List<Game.Debug.DebugSystem+SerializationItem> m_SerializationBuffer`  

```csharp
private System.Collections.Generic.List<Game.Debug.DebugSystem+SerializationItem> m_SerializationBuffer;
```

- `private Game.Debug.DebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.DebugSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1508003740_0`  

```csharp
private Unity.Entities.EntityQuery __query_1508003740_0;
```

- `private static readonly UnityEngine.GUIContent[] kDebugSimulationSpeedStrings`  

```csharp
private static readonly UnityEngine.GUIContent[] kDebugSimulationSpeedStrings;
```

- `private static readonly System.Single[] kDebugSimulationSpeedValues`  

```csharp
private static readonly System.Single[] kDebugSimulationSpeedValues;
```

- `private static readonly UnityEngine.GUIContent[] kDebugWaterSpeedStrings`  

```csharp
private static readonly UnityEngine.GUIContent[] kDebugWaterSpeedStrings;
```

- `private static System.Int32[] m_DebugWaterSpeedValues`  

```csharp
private static System.Int32[] m_DebugWaterSpeedValues;
```

- `private static Game.Tools.ToolBaseSystem[] m_ToolSystems`  

```csharp
private static Game.Tools.ToolBaseSystem[] m_ToolSystems;
```

- `private static UnityEngine.GUIContent[] m_ToolSystemNames`  

```csharp
private static UnityEngine.GUIContent[] m_ToolSystemNames;
```

- `private static const System.String kDebugSaveName`  

```csharp
private static const System.String kDebugSaveName;
```


## Constructors

- `public DebugSystem()`  

```csharp
public DebugSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_0() : Game.Tools.ToolBaseSystem`  

```csharp
private Game.Tools.ToolBaseSystem <__BuildSimulationDebugUI_1F128DF8>b__249_0();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_1(Game.Tools.ToolBaseSystem value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_1(Game.Tools.ToolBaseSystem value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_100() : System.Object`  

```csharp
private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_100();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_101() : System.Object`  

```csharp
private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_101();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_102() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_102();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_103() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_103();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_104() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_104();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_105() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_105();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_106() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_106();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_107(System.Single value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_107(System.Single value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_110() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_110();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_111(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_111(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_112() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_112();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_113(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_113(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_114() : System.Object`  

```csharp
private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_114();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_115() : System.Object`  

```csharp
private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_115();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_116() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_116();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_117(System.Single value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_117(System.Single value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_12() : System.Object`  

```csharp
private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_12();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_120() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_120();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_121(System.Single value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_121(System.Single value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_124() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_124();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_125(System.Single value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_125(System.Single value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_128() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_128();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_129(System.Single value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_129(System.Single value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_13() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_13();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_132() : System.Int32`  

```csharp
private System.Int32 <__BuildSimulationDebugUI_1F128DF8>b__249_132();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_133(System.Int32 value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_133(System.Int32 value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_135() : System.Object`  

```csharp
private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_135();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_136() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_136();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_137(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_137(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_138() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_138();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_139(System.Single value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_139(System.Single value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_14(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_14(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_142() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_142();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_143() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_143();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_144() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_144();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_145() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_145();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_148() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_148();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_149() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_149();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_15() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_15();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_151() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_151();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_152() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_152();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_153() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_153();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_154() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_154();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_155() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_155();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_156() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_156();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_157() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_157();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_158() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_158();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_159() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_159();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_16(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_16(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_160() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_160();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_161() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_161();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_162() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_162();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_163() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_163();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_164() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_164();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_165() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_165();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_168(UnityEngine.Rendering.DebugUI+Field<System.String> field, System.String value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_168(UnityEngine.Rendering.DebugUI+Field<System.String> field, System.String value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_169() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_169();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_17() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_17();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_170() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_170();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_171() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_171();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_172() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_172();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_173() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_173();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_174() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_174();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_175() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_175();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_176(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_176(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_177() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_177();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_178(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_178(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_179() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_179();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_18(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_18(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_180(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_180(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_181() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_181();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_182() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_182();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_19() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_19();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_2() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_2();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_20() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_20();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_21() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_21();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_217() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_217();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_218() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_218();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_219() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_219();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_22(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_22(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_220() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_220();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_221() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_221();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_222() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_222();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_223() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_223();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_224() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_224();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_225() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_225();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_226(System.Single value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_226(System.Single value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_229() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_229();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_23() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_23();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_230(System.Single value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_230(System.Single value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_24(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_24(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_25() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_25();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_26(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_26(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_27() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_27();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_28(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_28(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_29() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_29();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_3() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_3();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_30(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_30(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_31() : System.Int32`  

```csharp
private System.Int32 <__BuildSimulationDebugUI_1F128DF8>b__249_31();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_32(System.Int32 value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_32(System.Int32 value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_35() : System.Int32`  

```csharp
private System.Int32 <__BuildSimulationDebugUI_1F128DF8>b__249_35();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_36(System.Int32 value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_36(System.Int32 value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_39() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_39();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_4(System.Single value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_4(System.Single value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_42() : System.Int32`  

```csharp
private System.Int32 <__BuildSimulationDebugUI_1F128DF8>b__249_42();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_43(System.Int32 value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_43(System.Int32 value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_44() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_44();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_45() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_45();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_46() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_46();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_47() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_47();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_48() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_48();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_49() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_49();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_5() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_5();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_50(System.Single value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_50(System.Single value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_53() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_53();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_54() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_54();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_55(System.Single value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_55(System.Single value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_58() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_58();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_59(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_59(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_6() : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_6();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_60() : System.Int32`  

```csharp
private System.Int32 <__BuildSimulationDebugUI_1F128DF8>b__249_60();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_61(System.Int32 value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_61(System.Int32 value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_64() : System.Object`  

```csharp
private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_64();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_65() : System.Int32`  

```csharp
private System.Int32 <__BuildSimulationDebugUI_1F128DF8>b__249_65();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_66(System.Int32 value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_66(System.Int32 value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_69() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_69();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_7() : System.Object`  

```csharp
private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_7();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_70(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_70(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_71() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_71();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_72(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_72(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_73() : System.Boolean`  

```csharp
private System.Boolean <__BuildSimulationDebugUI_1F128DF8>b__249_73();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_74(System.Boolean value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_74(System.Boolean value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_75() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_75();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_76(System.Single value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_76(System.Single value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_79() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_79();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_8() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_8();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_80(System.Single value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_80(System.Single value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_83() : System.Single`  

```csharp
private System.Single <__BuildSimulationDebugUI_1F128DF8>b__249_83();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_84(System.Single value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_84(System.Single value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_87() : Game.OverridableProperty<System.Single>`  

```csharp
private Game.OverridableProperty<System.Single> <__BuildSimulationDebugUI_1F128DF8>b__249_87();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_88() : Game.OverridableProperty<System.Single>`  

```csharp
private Game.OverridableProperty<System.Single> <__BuildSimulationDebugUI_1F128DF8>b__249_88();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_89() : System.Int32`  

```csharp
private System.Int32 <__BuildSimulationDebugUI_1F128DF8>b__249_89();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_9(System.Single value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_9(System.Single value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_90(System.Int32 value) : System.Void`  

```csharp
private System.Void <__BuildSimulationDebugUI_1F128DF8>b__249_90(System.Int32 value);
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_91() : Game.OverridableProperty<System.Single>`  

```csharp
private Game.OverridableProperty<System.Single> <__BuildSimulationDebugUI_1F128DF8>b__249_91();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_92() : Game.OverridableProperty<System.Single>`  

```csharp
private Game.OverridableProperty<System.Single> <__BuildSimulationDebugUI_1F128DF8>b__249_92();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_93() : Game.OverridableProperty<System.Single>`  

```csharp
private Game.OverridableProperty<System.Single> <__BuildSimulationDebugUI_1F128DF8>b__249_93();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_94() : System.Object`  

```csharp
private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_94();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_95() : System.Object`  

```csharp
private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_95();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_96() : System.Object`  

```csharp
private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_96();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_97() : System.Object`  

```csharp
private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_97();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_98() : System.Object`  

```csharp
private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_98();
```

- `private <__BuildSimulationDebugUI_1F128DF8>b__249_99() : System.Object`  

```csharp
private System.Object <__BuildSimulationDebugUI_1F128DF8>b__249_99();
```

- `internal static <AddSystemGizmoField>g__RebuildGizmosDebugUI|233_0<T, TValue>(UnityEngine.Rendering.DebugUI+Field<TValue> field, TValue value) : System.Void`  

```csharp
internal static System.Void <AddSystemGizmoField>g__RebuildGizmosDebugUI|233_0<T, TValue>(UnityEngine.Rendering.DebugUI+Field<TValue> field, TValue value);
```

- `private <BuildECSComponentsDebugUI>b__5_0() : System.String`  

```csharp
private System.String <BuildECSComponentsDebugUI>b__5_0();
```

- `private <BuildECSComponentsDebugUI>b__5_1(System.String value) : System.Void`  

```csharp
private System.Void <BuildECSComponentsDebugUI>b__5_1(System.String value);
```

- `private <BuildECSComponentsDebugUI>b__5_2() : System.Boolean`  

```csharp
private System.Boolean <BuildECSComponentsDebugUI>b__5_2();
```

- `private <BuildECSComponentsDebugUI>b__5_3(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildECSComponentsDebugUI>b__5_3(System.Boolean value);
```

- `private <BuildECSComponentsDebugUI>b__5_4() : System.Void`  

```csharp
private System.Void <BuildECSComponentsDebugUI>b__5_4();
```

- `private <BuildECSComponentsDebugUI>b__5_5() : System.Object`  

```csharp
private System.Object <BuildECSComponentsDebugUI>b__5_5();
```

- `private <BuildECSComponentsDebugUI>b__5_6() : System.Object`  

```csharp
private System.Object <BuildECSComponentsDebugUI>b__5_6();
```

- `private <BuildECSComponentsDebugUI>b__5_7() : System.Object`  

```csharp
private System.Object <BuildECSComponentsDebugUI>b__5_7();
```

- `private <BuildECSComponentsDebugUI>b__5_8() : System.Object`  

```csharp
private System.Object <BuildECSComponentsDebugUI>b__5_8();
```

- `private <BuildingUpgradeUI>g__Upgrade|155_0(Unity.Entities.Entity upgrade) : System.Void`  

```csharp
private System.Void <BuildingUpgradeUI>g__Upgrade|155_0(Unity.Entities.Entity upgrade);
```

- `private <BuildNotificationsDebugUI>b__239_0() : System.Void`  

```csharp
private System.Void <BuildNotificationsDebugUI>b__239_0();
```

- `private <BuildNotificationsDebugUI>b__239_1(Game.Debug.DebugSystem+NotificationInfo info) : UnityEngine.Rendering.DebugUI+BoolField`  

```csharp
private UnityEngine.Rendering.DebugUI+BoolField <BuildNotificationsDebugUI>b__239_1(Game.Debug.DebugSystem+NotificationInfo info);
```

- `private <BuildSimulationDebugUI>b__127_0() : Game.Tools.ToolBaseSystem`  

```csharp
private Game.Tools.ToolBaseSystem <BuildSimulationDebugUI>b__127_0();
```

- `private <BuildSimulationDebugUI>b__127_1(Game.Tools.ToolBaseSystem value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_1(Game.Tools.ToolBaseSystem value);
```

- `private <BuildSimulationDebugUI>b__127_100() : System.Object`  

```csharp
private System.Object <BuildSimulationDebugUI>b__127_100();
```

- `private <BuildSimulationDebugUI>b__127_101() : System.Object`  

```csharp
private System.Object <BuildSimulationDebugUI>b__127_101();
```

- `private <BuildSimulationDebugUI>b__127_102() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_102();
```

- `private <BuildSimulationDebugUI>b__127_103() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_103();
```

- `private <BuildSimulationDebugUI>b__127_104() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_104();
```

- `private <BuildSimulationDebugUI>b__127_105() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_105();
```

- `private <BuildSimulationDebugUI>b__127_106() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_106();
```

- `private <BuildSimulationDebugUI>b__127_107(System.Single value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_107(System.Single value);
```

- `private <BuildSimulationDebugUI>b__127_110() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_110();
```

- `private <BuildSimulationDebugUI>b__127_111(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_111(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_112() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_112();
```

- `private <BuildSimulationDebugUI>b__127_113(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_113(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_114() : System.Object`  

```csharp
private System.Object <BuildSimulationDebugUI>b__127_114();
```

- `private <BuildSimulationDebugUI>b__127_115() : System.Object`  

```csharp
private System.Object <BuildSimulationDebugUI>b__127_115();
```

- `private <BuildSimulationDebugUI>b__127_116() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_116();
```

- `private <BuildSimulationDebugUI>b__127_117(System.Single value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_117(System.Single value);
```

- `private <BuildSimulationDebugUI>b__127_12() : System.Object`  

```csharp
private System.Object <BuildSimulationDebugUI>b__127_12();
```

- `private <BuildSimulationDebugUI>b__127_120() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_120();
```

- `private <BuildSimulationDebugUI>b__127_121(System.Single value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_121(System.Single value);
```

- `private <BuildSimulationDebugUI>b__127_124() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_124();
```

- `private <BuildSimulationDebugUI>b__127_125(System.Single value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_125(System.Single value);
```

- `private <BuildSimulationDebugUI>b__127_128() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_128();
```

- `private <BuildSimulationDebugUI>b__127_129(System.Single value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_129(System.Single value);
```

- `private <BuildSimulationDebugUI>b__127_13() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_13();
```

- `private <BuildSimulationDebugUI>b__127_132() : System.Int32`  

```csharp
private System.Int32 <BuildSimulationDebugUI>b__127_132();
```

- `private <BuildSimulationDebugUI>b__127_133(System.Int32 value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_133(System.Int32 value);
```

- `private <BuildSimulationDebugUI>b__127_135() : System.Object`  

```csharp
private System.Object <BuildSimulationDebugUI>b__127_135();
```

- `private <BuildSimulationDebugUI>b__127_136() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_136();
```

- `private <BuildSimulationDebugUI>b__127_137(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_137(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_138() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_138();
```

- `private <BuildSimulationDebugUI>b__127_139(System.Single value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_139(System.Single value);
```

- `private <BuildSimulationDebugUI>b__127_14(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_14(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_142() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_142();
```

- `private <BuildSimulationDebugUI>b__127_143() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_143();
```

- `private <BuildSimulationDebugUI>b__127_144() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_144();
```

- `private <BuildSimulationDebugUI>b__127_145() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_145();
```

- `private <BuildSimulationDebugUI>b__127_149() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_149();
```

- `private <BuildSimulationDebugUI>b__127_15() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_15();
```

- `private <BuildSimulationDebugUI>b__127_151() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_151();
```

- `private <BuildSimulationDebugUI>b__127_152() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_152();
```

- `private <BuildSimulationDebugUI>b__127_153() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_153();
```

- `private <BuildSimulationDebugUI>b__127_154() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_154();
```

- `private <BuildSimulationDebugUI>b__127_155() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_155();
```

- `private <BuildSimulationDebugUI>b__127_156() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_156();
```

- `private <BuildSimulationDebugUI>b__127_157() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_157();
```

- `private <BuildSimulationDebugUI>b__127_158() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_158();
```

- `private <BuildSimulationDebugUI>b__127_159() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_159();
```

- `private <BuildSimulationDebugUI>b__127_16(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_16(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_160() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_160();
```

- `private <BuildSimulationDebugUI>b__127_161() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_161();
```

- `private <BuildSimulationDebugUI>b__127_162() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_162();
```

- `private <BuildSimulationDebugUI>b__127_163() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_163();
```

- `private <BuildSimulationDebugUI>b__127_164() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_164();
```

- `private <BuildSimulationDebugUI>b__127_165() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_165();
```

- `private <BuildSimulationDebugUI>b__127_168(UnityEngine.Rendering.DebugUI+Field<System.String> field, System.String value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_168(UnityEngine.Rendering.DebugUI+Field<System.String> field, System.String value);
```

- `private <BuildSimulationDebugUI>b__127_169() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_169();
```

- `private <BuildSimulationDebugUI>b__127_17() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_17();
```

- `private <BuildSimulationDebugUI>b__127_170() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_170();
```

- `private <BuildSimulationDebugUI>b__127_171() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_171();
```

- `private <BuildSimulationDebugUI>b__127_172() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_172();
```

- `private <BuildSimulationDebugUI>b__127_173() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_173();
```

- `private <BuildSimulationDebugUI>b__127_174() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_174();
```

- `private <BuildSimulationDebugUI>b__127_175() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_175();
```

- `private <BuildSimulationDebugUI>b__127_176(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_176(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_177() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_177();
```

- `private <BuildSimulationDebugUI>b__127_178(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_178(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_179() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_179();
```

- `private <BuildSimulationDebugUI>b__127_18(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_18(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_180(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_180(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_181() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_181();
```

- `private <BuildSimulationDebugUI>b__127_182() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_182();
```

- `private <BuildSimulationDebugUI>b__127_19() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_19();
```

- `private <BuildSimulationDebugUI>b__127_2() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_2();
```

- `private <BuildSimulationDebugUI>b__127_20() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_20();
```

- `private <BuildSimulationDebugUI>b__127_21() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_21();
```

- `private <BuildSimulationDebugUI>b__127_217() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_217();
```

- `private <BuildSimulationDebugUI>b__127_218() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_218();
```

- `private <BuildSimulationDebugUI>b__127_219() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_219();
```

- `private <BuildSimulationDebugUI>b__127_22(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_22(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_220() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_220();
```

- `private <BuildSimulationDebugUI>b__127_221() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_221();
```

- `private <BuildSimulationDebugUI>b__127_222() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_222();
```

- `private <BuildSimulationDebugUI>b__127_223() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_223();
```

- `private <BuildSimulationDebugUI>b__127_224() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_224();
```

- `private <BuildSimulationDebugUI>b__127_225() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_225();
```

- `private <BuildSimulationDebugUI>b__127_226(System.Single value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_226(System.Single value);
```

- `private <BuildSimulationDebugUI>b__127_229() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_229();
```

- `private <BuildSimulationDebugUI>b__127_23() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_23();
```

- `private <BuildSimulationDebugUI>b__127_230(System.Single value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_230(System.Single value);
```

- `private <BuildSimulationDebugUI>b__127_24(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_24(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_25() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_25();
```

- `private <BuildSimulationDebugUI>b__127_26(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_26(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_27() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_27();
```

- `private <BuildSimulationDebugUI>b__127_28(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_28(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_29() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_29();
```

- `private <BuildSimulationDebugUI>b__127_3() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_3();
```

- `private <BuildSimulationDebugUI>b__127_30(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_30(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_31() : System.Int32`  

```csharp
private System.Int32 <BuildSimulationDebugUI>b__127_31();
```

- `private <BuildSimulationDebugUI>b__127_32(System.Int32 value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_32(System.Int32 value);
```

- `private <BuildSimulationDebugUI>b__127_35() : System.Int32`  

```csharp
private System.Int32 <BuildSimulationDebugUI>b__127_35();
```

- `private <BuildSimulationDebugUI>b__127_36(System.Int32 value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_36(System.Int32 value);
```

- `private <BuildSimulationDebugUI>b__127_39() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_39();
```

- `private <BuildSimulationDebugUI>b__127_4(System.Single value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_4(System.Single value);
```

- `private <BuildSimulationDebugUI>b__127_42() : System.Int32`  

```csharp
private System.Int32 <BuildSimulationDebugUI>b__127_42();
```

- `private <BuildSimulationDebugUI>b__127_43(System.Int32 value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_43(System.Int32 value);
```

- `private <BuildSimulationDebugUI>b__127_44() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_44();
```

- `private <BuildSimulationDebugUI>b__127_45() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_45();
```

- `private <BuildSimulationDebugUI>b__127_46() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_46();
```

- `private <BuildSimulationDebugUI>b__127_47() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_47();
```

- `private <BuildSimulationDebugUI>b__127_48() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_48();
```

- `private <BuildSimulationDebugUI>b__127_49() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_49();
```

- `private <BuildSimulationDebugUI>b__127_5() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_5();
```

- `private <BuildSimulationDebugUI>b__127_50(System.Single value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_50(System.Single value);
```

- `private <BuildSimulationDebugUI>b__127_53() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_53();
```

- `private <BuildSimulationDebugUI>b__127_54() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_54();
```

- `private <BuildSimulationDebugUI>b__127_55(System.Single value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_55(System.Single value);
```

- `private <BuildSimulationDebugUI>b__127_58() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_58();
```

- `private <BuildSimulationDebugUI>b__127_59(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_59(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_6() : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_6();
```

- `private <BuildSimulationDebugUI>b__127_60() : System.Int32`  

```csharp
private System.Int32 <BuildSimulationDebugUI>b__127_60();
```

- `private <BuildSimulationDebugUI>b__127_61(System.Int32 value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_61(System.Int32 value);
```

- `private <BuildSimulationDebugUI>b__127_64() : System.Object`  

```csharp
private System.Object <BuildSimulationDebugUI>b__127_64();
```

- `private <BuildSimulationDebugUI>b__127_65() : System.Int32`  

```csharp
private System.Int32 <BuildSimulationDebugUI>b__127_65();
```

- `private <BuildSimulationDebugUI>b__127_66(System.Int32 value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_66(System.Int32 value);
```

- `private <BuildSimulationDebugUI>b__127_69() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_69();
```

- `private <BuildSimulationDebugUI>b__127_7() : System.Object`  

```csharp
private System.Object <BuildSimulationDebugUI>b__127_7();
```

- `private <BuildSimulationDebugUI>b__127_70(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_70(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_71() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_71();
```

- `private <BuildSimulationDebugUI>b__127_72(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_72(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_73() : System.Boolean`  

```csharp
private System.Boolean <BuildSimulationDebugUI>b__127_73();
```

- `private <BuildSimulationDebugUI>b__127_74(System.Boolean value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_74(System.Boolean value);
```

- `private <BuildSimulationDebugUI>b__127_75() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_75();
```

- `private <BuildSimulationDebugUI>b__127_76(System.Single value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_76(System.Single value);
```

- `private <BuildSimulationDebugUI>b__127_79() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_79();
```

- `private <BuildSimulationDebugUI>b__127_8() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_8();
```

- `private <BuildSimulationDebugUI>b__127_80(System.Single value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_80(System.Single value);
```

- `private <BuildSimulationDebugUI>b__127_83() : System.Single`  

```csharp
private System.Single <BuildSimulationDebugUI>b__127_83();
```

- `private <BuildSimulationDebugUI>b__127_84(System.Single value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_84(System.Single value);
```

- `private <BuildSimulationDebugUI>b__127_87() : Game.OverridableProperty<System.Single>`  

```csharp
private Game.OverridableProperty<System.Single> <BuildSimulationDebugUI>b__127_87();
```

- `private <BuildSimulationDebugUI>b__127_88() : Game.OverridableProperty<System.Single>`  

```csharp
private Game.OverridableProperty<System.Single> <BuildSimulationDebugUI>b__127_88();
```

- `private <BuildSimulationDebugUI>b__127_89() : System.Int32`  

```csharp
private System.Int32 <BuildSimulationDebugUI>b__127_89();
```

- `private <BuildSimulationDebugUI>b__127_9(System.Single value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_9(System.Single value);
```

- `private <BuildSimulationDebugUI>b__127_90(System.Int32 value) : System.Void`  

```csharp
private System.Void <BuildSimulationDebugUI>b__127_90(System.Int32 value);
```

- `private <BuildSimulationDebugUI>b__127_91() : Game.OverridableProperty<System.Single>`  

```csharp
private Game.OverridableProperty<System.Single> <BuildSimulationDebugUI>b__127_91();
```

- `private <BuildSimulationDebugUI>b__127_92() : Game.OverridableProperty<System.Single>`  

```csharp
private Game.OverridableProperty<System.Single> <BuildSimulationDebugUI>b__127_92();
```

- `private <BuildSimulationDebugUI>b__127_93() : Game.OverridableProperty<System.Single>`  

```csharp
private Game.OverridableProperty<System.Single> <BuildSimulationDebugUI>b__127_93();
```

- `private <BuildSimulationDebugUI>b__127_94() : System.Object`  

```csharp
private System.Object <BuildSimulationDebugUI>b__127_94();
```

- `private <BuildSimulationDebugUI>b__127_95() : System.Object`  

```csharp
private System.Object <BuildSimulationDebugUI>b__127_95();
```

- `private <BuildSimulationDebugUI>b__127_96() : System.Object`  

```csharp
private System.Object <BuildSimulationDebugUI>b__127_96();
```

- `private <BuildSimulationDebugUI>b__127_97() : System.Object`  

```csharp
private System.Object <BuildSimulationDebugUI>b__127_97();
```

- `private <BuildSimulationDebugUI>b__127_98() : System.Object`  

```csharp
private System.Object <BuildSimulationDebugUI>b__127_98();
```

- `private <BuildSimulationDebugUI>b__127_99() : System.Object`  

```csharp
private System.Object <BuildSimulationDebugUI>b__127_99();
```

- `private <CreateEventUI>b__172_1() : System.Object`  

```csharp
private System.Object <CreateEventUI>b__172_1();
```

- `private <CreateToolUI>b__153_0() : System.Boolean`  

```csharp
private System.Boolean <CreateToolUI>b__153_0();
```

- `private <CreateToolUI>b__153_1(System.Boolean value) : System.Void`  

```csharp
private System.Void <CreateToolUI>b__153_1(System.Boolean value);
```

- `internal static <GetPrimitiveUIValueObject>g__GetValue|195_0(System.Object obj) : System.Object`  

```csharp
internal static System.Object <GetPrimitiveUIValueObject>g__GetValue|195_0(System.Object obj);
```

- `private <InfoviewUI>b__171_0() : System.Void`  

```csharp
private System.Void <InfoviewUI>b__171_0();
```

- `private AddPanel(System.String name, System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> widgets, System.Int32 groupIndex = -1, System.Boolean overrideIfExists = False) : UnityEngine.Rendering.DebugUI+IContainer`  

```csharp
private UnityEngine.Rendering.DebugUI+IContainer AddPanel(System.String name, System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> widgets, System.Int32 groupIndex, System.Boolean overrideIfExists);
```

- `private static AddSystemGizmoField<T>(UnityEngine.Rendering.DebugUI+Container& container, Unity.Entities.World world, UnityEngine.Rendering.DebugUI+Widget[] additionalIfEnabled) : System.Void`  

```csharp
private static System.Void AddSystemGizmoField<T>(UnityEngine.Rendering.DebugUI+Container& container, Unity.Entities.World world, UnityEngine.Rendering.DebugUI+Widget[] additionalIfEnabled);
```

- `public AgeSelectedCitizen() : System.Void`  

```csharp
public System.Void AgeSelectedCitizen();
```

- `private AreaToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private System.Void AreaToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
```

- `private BitToggle(UnityEngine.Rendering.DebugUI+Container container, System.String text, Game.Tools.ToolBaseSystem tool, Game.Tools.Snap bit) : System.Void`  

```csharp
private System.Void BitToggle(UnityEngine.Rendering.DebugUI+Container container, System.String text, Game.Tools.ToolBaseSystem tool, Game.Tools.Snap bit);
```

- `private BuildClimateUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildClimateUI();
```

- `private BuildECSComponentsDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildECSComponentsDebugUI();
```

- `private BuildGameplayDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildGameplayDebugUI();
```

- `private static BuildGizmosDebugUI(Unity.Entities.World world) : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private static System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildGizmosDebugUI(Unity.Entities.World world);
```

- `private BuildingMoveUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Void`  

```csharp
private System.Void BuildingMoveUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private BuildingUpgradeUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity prefab) : System.Void`  

```csharp
private System.Void BuildingUpgradeUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity prefab);
```

- `private BuildNotificationsDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildNotificationsDebugUI();
```

- `private BuildPathfindDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildPathfindDebugUI();
```

- `private static BuildPlatformsDebugUI(Unity.Entities.World world) : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private static System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildPlatformsDebugUI(Unity.Entities.World world);
```

- `private BuildRenderingDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildRenderingDebugUI();
```

- `private BuildSerializationDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildSerializationDebugUI();
```

- `private BuildSimulationDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildSimulationDebugUI();
```

- `private static BuildVirtualTexturingDebugUI(Unity.Entities.World world) : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private static System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildVirtualTexturingDebugUI(Unity.Entities.World world);
```

- `private BulldozeToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private System.Void BulldozeToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
```

- `private CacheGameRenderingDebugUISystems() : System.Void`  

```csharp
private System.Void CacheGameRenderingDebugUISystems();
```

- `private CalculateCustomers() : System.Void`  

```csharp
private System.Void CalculateCustomers();
```

- `private CalculateEligible() : System.Void`  

```csharp
private System.Void CalculateEligible();
```

- `private CalculateStudentsFromOC() : System.Void`  

```csharp
private System.Void CalculateStudentsFromOC();
```

- `private CleanupObsoleteEntities() : System.Void`  

```csharp
private System.Void CleanupObsoleteEntities();
```

- `private ClearSelection() : System.Void`  

```csharp
private System.Void ClearSelection();
```

- `private CreateDebugBlitPass() : System.Void`  

```csharp
private System.Void CreateDebugBlitPass();
```

- `private CreateDebugClass(System.Type type) : System.Object`  

```csharp
private System.Object CreateDebugClass(System.Type type);
```

- `private CreateEventUI() : UnityEngine.Rendering.DebugUI+Foldout`  

```csharp
private UnityEngine.Rendering.DebugUI+Foldout CreateEventUI();
```

- `private CreateToolUI() : UnityEngine.Rendering.DebugUI+Container`  

```csharp
private UnityEngine.Rendering.DebugUI+Container CreateToolUI();
```

- `private static CreateVolumeParameterWidget(System.String name, UnityEngine.Rendering.VolumeParameter param, System.Func<System.Boolean> isHiddenCallback = null) : UnityEngine.Rendering.DebugUI+Widget`  

```csharp
private static UnityEngine.Rendering.DebugUI+Widget CreateVolumeParameterWidget(System.String name, UnityEngine.Rendering.VolumeParameter param, System.Func<System.Boolean> isHiddenCallback);
```

- `private DefaultToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private System.Void DefaultToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
```

- `private DisposeDebugClasses() : System.Void`  

```csharp
private System.Void DisposeDebugClasses();
```

- `private EditorDate() : System.String`  

```csharp
private System.String EditorDate();
```

- `private EnableNotification(Unity.Entities.Entity entity, System.Boolean enabled) : System.Void`  

```csharp
private System.Void EnableNotification(Unity.Entities.Entity entity, System.Boolean enabled);
```

- `private ExecuteMethod(System.Reflection.MethodInfo method, System.Object target, Game.Debug.DebugTabAttribute attribute) : System.Void`  

```csharp
private System.Void ExecuteMethod(System.Reflection.MethodInfo method, System.Object target, Game.Debug.DebugTabAttribute attribute);
```

- `private ExportHeightMap() : System.Void`  

```csharp
private System.Void ExportHeightMap();
```

- `private FollowSelectedCitizen() : System.Void`  

```csharp
private System.Void FollowSelectedCitizen();
```

- `public FullWithGarbage() : System.Void`  

```csharp
public System.Void FullWithGarbage();
```

- `private GetAnimBuffer() : System.String`  

```csharp
private System.String GetAnimBuffer();
```

- `private GetAreaBuffer() : System.String`  

```csharp
private System.String GetAreaBuffer();
```

- `private GetArrayFoldout(System.Array record1, System.Array record2) : UnityEngine.Rendering.DebugUI+Foldout`  

```csharp
private UnityEngine.Rendering.DebugUI+Foldout GetArrayFoldout(System.Array record1, System.Array record2);
```

- `private GetBatchAllocation() : System.String`  

```csharp
private System.String GetBatchAllocation();
```

- `private GetBatchGroups() : System.String`  

```csharp
private System.String GetBatchGroups();
```

- `private GetBatchMaterials() : System.String`  

```csharp
private System.String GetBatchMaterials();
```

- `private GetBatchMeshes() : System.String`  

```csharp
private System.String GetBatchMeshes();
```

- `private GetBatchRenderers() : System.String`  

```csharp
private System.String GetBatchRenderers();
```

- `private GetBatchUpload() : System.String`  

```csharp
private System.String GetBatchUpload();
```

- `private GetBoneBuffer() : System.String`  

```csharp
private System.String GetBoneBuffer();
```

- `private GetEffectCulling() : System.String`  

```csharp
private System.String GetEffectCulling();
```

- `private GetEntityCulling() : System.String`  

```csharp
private System.String GetEntityCulling();
```

- `private GetFieldValueFoldout(System.Object object1, System.Object object2) : UnityEngine.Rendering.DebugUI+Foldout`  

```csharp
private UnityEngine.Rendering.DebugUI+Foldout GetFieldValueFoldout(System.Object object1, System.Object object2);
```

- `private GetIndexBuffer() : System.String`  

```csharp
private System.String GetIndexBuffer();
```

- `private GetMetaBuffer() : System.String`  

```csharp
private System.String GetMetaBuffer();
```

- `private GetPrimitiveUIValueObject(System.Object object1, System.Object object2) : UnityEngine.Rendering.DebugUI+Value`  

```csharp
private UnityEngine.Rendering.DebugUI+Value GetPrimitiveUIValueObject(System.Object object1, System.Object object2);
```

- `private GetProceduralEmissiveBuffer() : System.String`  

```csharp
private System.String GetProceduralEmissiveBuffer();
```

- `private GetProceduralEmissiveUpload() : System.String`  

```csharp
private System.String GetProceduralEmissiveUpload();
```

- `private GetProceduralSkeletonBuffer() : System.String`  

```csharp
private System.String GetProceduralSkeletonBuffer();
```

- `private GetProceduralSkeletonUpload() : System.String`  

```csharp
private System.String GetProceduralSkeletonUpload();
```

- `private GetRecordFoldout(Game.Prefabs.Modes.ModePrefab+ModeDebugUILogInfo record) : UnityEngine.Rendering.DebugUI+Foldout`  

```csharp
private UnityEngine.Rendering.DebugUI+Foldout GetRecordFoldout(Game.Prefabs.Modes.ModePrefab+ModeDebugUILogInfo record);
```

- `private GetShapeBuffer() : System.String`  

```csharp
private System.String GetShapeBuffer();
```

- `private GetTool<T>() : T`  

```csharp
private T GetTool<T>();
```

- `private GetWaterSpeedValues() : System.Int32[]`  

```csharp
private System.Int32[] GetWaterSpeedValues();
```

- `private GiveMaxResources() : System.Void`  

```csharp
private System.Void GiveMaxResources();
```

- `private HappinessFactors() : System.Void`  

```csharp
private System.Void HappinessFactors();
```

- `private InfoviewUI() : UnityEngine.Rendering.DebugUI+Widget`  

```csharp
private UnityEngine.Rendering.DebugUI+Widget InfoviewUI();
```

- `private InitializeRenderingDebugUI() : System.Void`  

```csharp
private System.Void InitializeRenderingDebugUI();
```

- `private LevelUpUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Void`  

```csharp
private System.Void LevelUpUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private LoadGame() : System.Void`  

```csharp
private System.Void LoadGame();
```

- `public MaxHouseholdsWealth() : System.Void`  

```csharp
public System.Void MaxHouseholdsWealth();
```

- `private NetToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private System.Void NetToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
```

- `private ObjectToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private System.Void ObjectToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
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

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `private OnSelectionChanged(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Mathematics.float3 position) : System.Void`  

```csharp
private System.Void OnSelectionChanged(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Mathematics.float3 position);
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private OverridableProperty<T>(System.String displayName, System.Func<T> getter, System.Single min = 0, System.Single max = 1, System.Single incStep = 0,001) : UnityEngine.Rendering.DebugUI+Container`  

```csharp
private UnityEngine.Rendering.DebugUI+Container OverridableProperty<T>(System.String displayName, System.Func<T> getter, System.Single min, System.Single max, System.Single incStep);
```

- `private PolicyUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void PolicyUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity);
```

- `private PrintCommuterDistribute() : System.Void`  

```csharp
private System.Void PrintCommuterDistribute();
```

- `private PrintNullHouseholds() : System.Void`  

```csharp
private System.Void PrintNullHouseholds();
```

- `private RadioSelection<T>(System.String displayName, System.Func<T> getter, System.Action<T> setter, UnityEngine.GUIContent[] names, T[] values, System.Action onValueChanged = null) : UnityEngine.Rendering.DebugUI+Widget`  

```csharp
private UnityEngine.Rendering.DebugUI+Widget RadioSelection<T>(System.String displayName, System.Func<T> getter, System.Action<T> setter, UnityEngine.GUIContent[] names, T[] values, System.Action onValueChanged);
```

- `public static Rebuild(System.Func<Unity.Entities.World, System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>> method) : System.Void`  

```csharp
public static System.Void Rebuild(System.Func<Unity.Entities.World, System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>> method);
```

- `public static Rebuild(System.Func<System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>> method) : System.Void`  

```csharp
public static System.Void Rebuild(System.Func<System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>> method);
```

- `private static Rebuild(System.Delegate method) : System.Void`  

```csharp
private static System.Void Rebuild(System.Delegate method);
```

- `private RebuildSimulationDebugUI<T>(UnityEngine.Rendering.DebugUI+Field<T> field, T value) : System.Void`  

```csharp
private System.Void RebuildSimulationDebugUI<T>(UnityEngine.Rendering.DebugUI+Field<T> field, T value);
```

- `private RefreshGameplayModeDebug() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> RefreshGameplayModeDebug();
```

- `private RefreshNotifications() : System.Void`  

```csharp
private System.Void RefreshNotifications();
```

- `private RegisterDebug() : System.Void`  

```csharp
private System.Void RegisterDebug();
```

- `private ReloadWaterSources() : System.Void`  

```csharp
private System.Void ReloadWaterSources();
```

- `private RemoveAllHomeless() : System.Void`  

```csharp
private System.Void RemoveAllHomeless();
```

- `private RemoveAllTourist() : System.Void`  

```csharp
private System.Void RemoveAllTourist();
```

- `private RemoveResidentsAndVehicles() : System.Void`  

```csharp
private System.Void RemoveResidentsAndVehicles();
```

- `private ResetCommercialStorage() : System.Void`  

```csharp
private System.Void ResetCommercialStorage();
```

- `public ResetCompanyMoney() : System.Void`  

```csharp
public System.Void ResetCompanyMoney();
```

- `private ResetCrimeAccumulation() : System.Void`  

```csharp
private System.Void ResetCrimeAccumulation();
```

- `public ResetHouseholdsWealth() : System.Void`  

```csharp
public System.Void ResetHouseholdsWealth();
```

- `public ResetLandvalue() : System.Void`  

```csharp
public System.Void ResetLandvalue();
```

- `public ResetPollution() : System.Void`  

```csharp
public System.Void ResetPollution();
```

- `public ResetRents() : System.Void`  

```csharp
public System.Void ResetRents();
```

- `private ResetServices() : System.Void`  

```csharp
private System.Void ResetServices();
```

- `private ResetStorages() : System.Void`  

```csharp
private System.Void ResetStorages();
```

- `private ResetTradeCosts() : System.Void`  

```csharp
private System.Void ResetTradeCosts();
```

- `private ResetTransfers() : System.Void`  

```csharp
private System.Void ResetTransfers();
```

- `private ResetTripNeeded() : System.Void`  

```csharp
private System.Void ResetTripNeeded();
```

- `public Restart() : System.Void`  

```csharp
public System.Void Restart();
```

- `private RouteToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private System.Void RouteToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
```

- `private SaveGame() : System.Void`  

```csharp
private System.Void SaveGame();
```

- `public SelectEntity(System.String searchTerm) : System.Void`  

```csharp
public System.Void SelectEntity(System.String searchTerm);
```

- `private SelectEntity(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void SelectEntity(Unity.Entities.Entity entity);
```

- `private SelectNext<T>(Unity.Entities.EntityQuery group, T current) : T`  

```csharp
private T SelectNext<T>(Unity.Entities.EntityQuery group, T current);
```

- `private SelectNext(Unity.Entities.EntityQuery group, Unity.Entities.Entity current) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity SelectNext(Unity.Entities.EntityQuery group, Unity.Entities.Entity current);
```

- `private ServiceDistrictUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void ServiceDistrictUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity);
```

- `private StartEvent(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void StartEvent(Unity.Entities.Entity entity);
```

- `private TerrainToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private System.Void TerrainToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
```

- `private ToggleSelection(System.String displayName, System.Func<System.Boolean> getter, System.Action<System.Boolean> setter, System.Action<UnityEngine.Rendering.DebugUI+Field<System.Int32>, System.Int32> onValueChanged = null) : UnityEngine.Rendering.DebugUI+EnumField`  

```csharp
private UnityEngine.Rendering.DebugUI+EnumField ToggleSelection(System.String displayName, System.Func<System.Boolean> getter, System.Action<System.Boolean> setter, System.Action<UnityEngine.Rendering.DebugUI+Field<System.Int32>, System.Int32> onValueChanged);
```

- `private ToolBrushUI(UnityEngine.Rendering.DebugUI+Container container, Game.Tools.ToolBaseSystem tool) : System.Void`  

```csharp
private System.Void ToolBrushUI(UnityEngine.Rendering.DebugUI+Container container, Game.Tools.ToolBaseSystem tool);
```

- `private ToolSnapUI(UnityEngine.Rendering.DebugUI+Container container, Game.Tools.ToolBaseSystem tool) : System.Void`  

```csharp
private System.Void ToolSnapUI(UnityEngine.Rendering.DebugUI+Container container, Game.Tools.ToolBaseSystem tool);
```

- `private TriggerTestLifeEvent() : System.Void`  

```csharp
private System.Void TriggerTestLifeEvent();
```

- `private TryFindSelectableEntity(System.Int32 index, Unity.Entities.Entity& entity) : System.Boolean`  

```csharp
private System.Boolean TryFindSelectableEntity(System.Int32 index, Unity.Entities.Entity& entity);
```

- `private TryGetPolicy(Unity.Entities.Entity entity, Unity.Entities.Entity policyType, Game.Policies.Policy& policy) : System.Boolean`  

```csharp
private System.Boolean TryGetPolicy(Unity.Entities.Entity entity, Unity.Entities.Entity policyType, Game.Policies.Policy& policy);
```

- `private UnityEngine.Rendering.IDebugData.GetReset() : System.Action`  

```csharp
private System.Action UnityEngine.Rendering.IDebugData.GetReset();
```

- `private UnregisterDebug() : System.Void`  

```csharp
private System.Void UnregisterDebug();
```

- `private UnregisterDebugItems(System.String panelName, System.Collections.Generic.IEnumerable<UnityEngine.Rendering.DebugUI+Widget> items) : System.Void`  

```csharp
private System.Void UnregisterDebugItems(System.String panelName, System.Collections.Generic.IEnumerable<UnityEngine.Rendering.DebugUI+Widget> items);
```

- `private UpgradeToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private System.Void UpgradeToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
```

- `private ZoneToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private System.Void ZoneToolSystemUI(UnityEngine.Rendering.DebugUI+Container container);
```


## Nested types

- `Game.Debug.DebugSystem+ToggleEnum`  
- `Game.Debug.DebugSystem+ToolUI`  
- `Game.Debug.DebugSystem+ResetServiceData`  
- `Game.Debug.DebugSystem+NotificationInfo`  
- `Game.Debug.DebugSystem+PathfindQueryItem`  
- `Game.Debug.DebugSystem+SerializationItem`  
- `Game.Debug.DebugSystem+TypeHandle`  
- `Game.Debug.DebugSystem+<>c`  
- `Game.Debug.DebugSystem+<>c__233<T>`  
- `Game.Debug.DebugSystem+<>c__DisplayClass0_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass0_1`  
- `Game.Debug.DebugSystem+<>c__DisplayClass0_2`  
- `Game.Debug.DebugSystem+<>c__DisplayClass0_3`  
- `Game.Debug.DebugSystem+<>c__DisplayClass118_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass119_0<T>`  
- `Game.Debug.DebugSystem+<>c__DisplayClass125_0<T>`  
- `Game.Debug.DebugSystem+<>c__DisplayClass154_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass154_1`  
- `Game.Debug.DebugSystem+<>c__DisplayClass154_2`  
- `Game.Debug.DebugSystem+<>c__DisplayClass154_3`  
- `Game.Debug.DebugSystem+<>c__DisplayClass155_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass156_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass157_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass162_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass162_1`  
- `Game.Debug.DebugSystem+<>c__DisplayClass162_2`  
- `Game.Debug.DebugSystem+<>c__DisplayClass163_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass164_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass165_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass165_1`  
- `Game.Debug.DebugSystem+<>c__DisplayClass166_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass167_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass168_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass170_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass171_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass172_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass174_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass176_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass189_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass191_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass195_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass1_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass1_1`  
- `Game.Debug.DebugSystem+<>c__DisplayClass1_2`  
- `Game.Debug.DebugSystem+<>c__DisplayClass232_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass232_1`  
- `Game.Debug.DebugSystem+<>c__DisplayClass232_2`  
- `Game.Debug.DebugSystem+<>c__DisplayClass232_3`  
- `Game.Debug.DebugSystem+<>c__DisplayClass233_0<T>`  
- `Game.Debug.DebugSystem+<>c__DisplayClass233_1<T>`  
- `Game.Debug.DebugSystem+<>c__DisplayClass234_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass239_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass242_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass242_1`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_1`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_10`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_11`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_12`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_13`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_14`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_15`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_16`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_17`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_18`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_2`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_3`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_4`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_5`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_6`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_7`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_8`  
- `Game.Debug.DebugSystem+<>c__DisplayClass243_9`  
- `Game.Debug.DebugSystem+<>c__DisplayClass246_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass246_1`  
- `Game.Debug.DebugSystem+<>c__DisplayClass247_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass249_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass255_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass255_1`  
- `Game.Debug.DebugSystem+<>c__DisplayClass257_0`  
- `Game.Debug.DebugSystem+<>c__DisplayClass257_1`  
- `Game.Debug.DebugSystem+<>c__DisplayClass5_0`  
- `Game.Debug.DebugSystem+<LoadGame>d__130`  
- `Game.Debug.DebugSystem+<SaveGame>d__129`  

