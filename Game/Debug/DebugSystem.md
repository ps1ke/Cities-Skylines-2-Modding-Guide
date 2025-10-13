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
[Preserve]
	public DebugSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<TerrainPropertiesData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1508003740_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
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
private DebugUI.IContainer AddPanel(string name, List<DebugUI.Widget> widgets, int groupIndex = -1, bool overrideIfExists = false)
	{
		DebugUI.Panel panel = DebugManager.instance.GetPanel(name, createIfNull: true, groupIndex, overrideIfExists);
		if (m_Panels.TryGetValue(name, out var value))
		{
			panel?.children.Remove(value);
		}
		m_Panels[name] = widgets;
		panel.children.Add(widgets);
		return panel;
	}
```

- `private static AddSystemGizmoField<T>(UnityEngine.Rendering.DebugUI+Container& container, Unity.Entities.World world, UnityEngine.Rendering.DebugUI+Widget[] additionalIfEnabled) : System.Void`  

```csharp
private static System.Void AddSystemGizmoField<T>(UnityEngine.Rendering.DebugUI+Container& container, Unity.Entities.World world, UnityEngine.Rendering.DebugUI+Widget[] additionalIfEnabled);
```

- `public AgeSelectedCitizen() : System.Void`  

```csharp
public void AgeSelectedCitizen()
	{
		ComponentLookup<Citizen> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<Game.Creatures.Resident> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Resident_RW_ComponentLookup, ref base.CheckedStateRef);
		Entity entity = Entity.Null;
		if (componentLookup.HasComponent(m_ToolSystem.selected))
		{
			entity = m_ToolSystem.selected;
		}
		if (componentLookup2.HasComponent(m_ToolSystem.selected))
		{
			entity = componentLookup2[m_ToolSystem.selected].m_Citizen;
		}
		if (entity != Entity.Null)
		{
			Citizen value = componentLookup[entity];
			value.m_BirthDay -= 12;
			UnityEngine.Debug.LogError(value.m_BirthDay);
			componentLookup[entity] = value;
			AgingSystem existingSystemManaged = base.World.GetExistingSystemManaged<AgingSystem>();
			AgingSystem.s_DebugAgeAllCitizens = true;
			existingSystemManaged.Update();
		}
	}
```

- `private AreaToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private void AreaToolSystemUI(DebugUI.Container container)
	{
		AreaToolSystem ats = GetTool<AreaToolSystem>();
		if (ats.GetPrefab() == null)
		{
			ats.prefab = SelectNext(m_AreaQuery, ats.prefab);
		}
		container.children.Add(new DebugUI.Value
		{
			displayName = "Type",
			getter = () => ats.prefab.name
		});
		container.children.Add(new DebugUI.Button
		{
			displayName = "Select next",
			action = delegate
			{
				ats.prefab = SelectNext(m_AreaQuery, ats.prefab);
			}
		});
	}
```

- `private BitToggle(UnityEngine.Rendering.DebugUI+Container container, System.String text, Game.Tools.ToolBaseSystem tool, Game.Tools.Snap bit) : System.Void`  

```csharp
private void BitToggle(DebugUI.Container container, string text, ToolBaseSystem tool, Snap bit)
	{
		container.children.Add(new DebugUI.BoolField
		{
			displayName = text,
			getter = () => (tool.selectedSnap & bit) != 0,
			setter = delegate(bool value)
			{
				tool.selectedSnap = (value ? (tool.selectedSnap | bit) : (tool.selectedSnap & ~bit));
			}
		});
	}
```

- `private BuildClimateUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private List<DebugUI.Widget> BuildClimateUI()
	{
		if (!GameManager.instance.gameMode.IsGameOrEditor())
		{
			return null;
		}
		ClimateRenderSystem climateRenderSystem = base.World.GetExistingSystemManaged<ClimateRenderSystem>();
		ClimateSystem climateSystem = base.World.GetExistingSystemManaged<ClimateSystem>();
		DebugUI.Foldout foldout = new DebugUI.Foldout
		{
			displayName = "Overrideable Properties"
		};
		foreach (KeyValuePair<Type, WeatherPropertiesStack.InterpolatedProperties> component in climateRenderSystem.propertiesStack.components)
		{
			DebugUI.Foldout foldout2 = new DebugUI.Foldout
			{
				displayName = component.Key.Name,
				opened = true
			};
			DebugUI.Foldout foldout3 = new DebugUI.Foldout
			{
				displayName = "Current"
			};
			FieldInfo[] fieldsInfo = component.Value.current.GetFieldsInfo();
			for (int i = 0; i < component.Value.current.parameters.Count; i++)
			{
				foldout3.children.Add(CreateVolumeParameterWidget(fieldsInfo[i].Name.Nicify() ?? "", component.Value.current.parameters[i]));
			}
			foldout2.children.Add(foldout3);
			foldout2.children.Add(new DebugUI.Value
			{
				displayName = "Interpolation mode",
				getter = () => component.Value.target.m_InterpolationMode
			});
			foldout2.children.Add(new DebugUI.Value
			{
				displayName = "Interpolation time",
				getter = () => component.Value.target.m_InterpolationTime
			});
			foldout2.children.Add(new DebugUI.Value
			{
				displayName = "Current lerp factor",
				getter = () => component.Value.time
			});
			DebugUI.Foldout foldout4 = new DebugUI.Foldout
			{
				displayName = "Previous"
			};
			for (int num = 0; num < component.Value.previous.parameters.Count; num++)
			{
				foldout4.children.Add(CreateVolumeParameterWidget(fieldsInfo[num].Name.Nicify() ?? "", component.Value.previous.parameters[num]));
			}
			foldout2.children.Add(foldout4);
			DebugUI.Foldout foldout5 = new DebugUI.Foldout
			{
				displayName = "Target"
			};
			for (int num2 = 0; num2 < component.Value.target.parameters.Count; num2++)
			{
				foldout5.children.Add(CreateVolumeParameterWidget(fieldsInfo[num2].Name.Nicify() ?? "", component.Value.target.parameters[num2]));
			}
			foldout2.children.Add(foldout5);
			DebugUI.Foldout foldout6 = new DebugUI.Foldout
			{
				displayName = "From"
			};
			for (int num3 = 0; num3 < component.Value.from.parameters.Count; num3++)
			{
				foldout6.children.Add(CreateVolumeParameterWidget(fieldsInfo[num3].Name.Nicify() ?? "", component.Value.from.parameters[num3]));
			}
			foldout2.children.Add(foldout6);
			DebugUI.Foldout foldout7 = new DebugUI.Foldout
			{
				displayName = "To"
			};
			for (int num4 = 0; num4 < component.Value.to.parameters.Count; num4++)
			{
				foldout7.children.Add(CreateVolumeParameterWidget(fieldsInfo[num4].Name.Nicify() ?? "", component.Value.to.parameters[num4]));
			}
			foldout2.children.Add(foldout7);
			foldout.children.Add(foldout2);
		}
		DebugUI.Foldout foldout8 = new DebugUI.Foldout
		{
			displayName = "Active weathers"
		};
		for (int num5 = 0; num5 < 5; num5++)
		{
			int index = num5;
			foldout8.children.Add(new DebugUI.Value
			{
				displayName = $"From #{num5}",
				getter = () => (index >= climateRenderSystem.fromWeatherPrefabs.Count) ? "None" : climateRenderSystem.fromWeatherPrefabs[index].name
			});
			foldout8.children.Add(new DebugUI.Value
			{
				displayName = $"To #{num5}",
				getter = () => (index >= climateRenderSystem.toWeatherPrefabs.Count) ? "None" : climateRenderSystem.toWeatherPrefabs[index].name
			});
		}
		return new List<DebugUI.Widget>
		{
			new DebugUI.BoolField
			{
				displayName = "Edit mode",
				getter = () => climateRenderSystem.editMode,
				setter = delegate(bool value)
				{
					climateRenderSystem.editMode = value;
				}
			},
			OverridableProperty("Climate time", () => climateSystem.currentDate),
			new DebugUI.BoolField
			{
				displayName = "Fast forward",
				getter = () => m_FastForwardClimateTime,
				setter = delegate(bool value)
				{
					m_FastForwardClimateTime = value;
				}
			},
			OverridableProperty("Cloudiness", () => climateSystem.cloudiness),
			OverridableProperty("Precipitation", () => climateSystem.precipitation),
			OverridableProperty("Aurora", () => climateSystem.aurora),
			foldout8,
			foldout,
			new DebugUI.BoolField
			{
				displayName = "Pause sim on lightning",
				getter = () => climateRenderSystem.pauseSimulationOnLightning,
				setter = delegate(bool value)
				{
					climateRenderSystem.pauseSimulationOnLightning = value;
				}
			},
			new DebugUI.Button
			{
				displayName = "Lightning Strike",
				action = delegate
				{
					climateRenderSystem.LightningStrike(m_LastSelectionPosition, m_LastSelectionPosition);
				}
			}
		};
	}
```

- `private BuildECSComponentsDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private List<DebugUI.Widget> BuildECSComponentsDebugUI()
	{
		List<DebugUI.Widget> list = new List<DebugUI.Widget>
		{
			new DebugUI.TextField
			{
				displayName = "Archetype Filter",
				getter = () => m_CommonComponentsFilter,
				setter = delegate(string value)
				{
					m_CommonComponentsFilter = value.Trim();
				}
			},
			new DebugUI.BoolField
			{
				displayName = "Exclude used archetypes",
				getter = () => m_CommonComponentsUnused,
				setter = delegate(bool value)
				{
					m_CommonComponentsUnused = value;
				}
			},
			new DebugUI.Button
			{
				displayName = "Refresh",
				action = delegate
				{
					m_CommonComponents = ComponentDebugUtils.GetCommonComponents(base.EntityManager, m_CommonComponentsFilter, m_CommonComponentsUnused, out m_ArchetypeCount, out m_FilteredArchetypeCount, out m_ChunkCount, out m_ChunkCapacity, out m_EntityCount);
					Rebuild(BuildECSComponentsDebugUI);
				}
			}
		};
		if (m_CommonComponents != null)
		{
			list.Add(new DebugUI.Value
			{
				displayName = "Total Entity Count",
				getter = () => m_EntityCount
			});
			list.Add(new DebugUI.Value
			{
				displayName = "Total Chunk Count",
				getter = () => m_ChunkCount
			});
			list.Add(new DebugUI.Value
			{
				displayName = "Total Archetype Count",
				getter = () => m_ArchetypeCount
			});
			list.Add(new DebugUI.Value
			{
				displayName = "Matching Archetype Count",
				getter = () => m_FilteredArchetypeCount
			});
			list.Add(new DebugUI.Container
			{
				displayName = (string.IsNullOrEmpty(m_CommonComponentsFilter) ? "Common components" : "Common components on matching archetypes"),
				children = { (IEnumerable<DebugUI.Widget>)m_CommonComponents.Select(delegate(ComponentDebugUtils.ComponentInfo info)
				{
					string value = ((info.m_ChunkCapacity > 0) ? $"{info.m_ArchetypeCount}, {100f * (float)info.m_EntityCount / (float)info.m_ChunkCapacity:F1}%" : info.m_ArchetypeCount.ToString());
					return new DebugUI.Value
					{
						displayName = info.m_Type.FullName.Replace("Game.", ""),
						getter = () => value
					};
				}) }
			});
		}
		return list;
	}
```

- `private BuildGameplayDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private List<DebugUI.Widget> BuildGameplayDebugUI()
	{
		TutorialSystem tutorialSystem = base.World.GetOrCreateSystemManaged<TutorialSystem>();
		if (base.World.EntityManager.TryGetBuffer(m_CitySystem.City, isReadOnly: true, out DynamicBuffer<ServiceFee> _))
		{
			return new List<DebugUI.Widget>
			{
				new DebugUI.BoolField
				{
					displayName = "Tutorials enabled",
					getter = () => tutorialSystem.tutorialEnabled,
					setter = delegate(bool value)
					{
						tutorialSystem.tutorialEnabled = value;
					}
				},
				new DebugUI.BoolField
				{
					displayName = "Freeze tutorials",
					getter = () => !tutorialSystem.Enabled,
					setter = delegate(bool value)
					{
						tutorialSystem.Enabled = !value;
					}
				},
				new DebugUI.Button
				{
					displayName = "Skip tutorial phase",
					action = delegate
					{
						tutorialSystem.CompleteCurrentTutorialPhase();
					}
				},
				new DebugUI.Button
				{
					displayName = "Show all tutorials in advisor",
					action = delegate
					{
						tutorialSystem.SetAllTutorialsShown();
					}
				},
				new DebugUI.Button
				{
					displayName = "Skip active tutorial list",
					action = delegate
					{
						tutorialSystem.SkipActiveList();
					}
				},
				new DebugUI.Value
				{
					displayName = "Active tutorial",
					getter = () => (!(tutorialSystem.activeTutorial != Entity.Null)) ? "None" : m_PrefabSystem.GetPrefab<PrefabBase>(tutorialSystem.activeTutorial).name
				},
				new DebugUI.Value
				{
					displayName = "Active tutorial list",
					getter = () => (!(tutorialSystem.activeTutorialList != Entity.Null)) ? "None" : m_PrefabSystem.GetPrefab<PrefabBase>(tutorialSystem.activeTutorialList).name
				},
				new DebugUI.BoolField
				{
					displayName = "Show developer info",
					getter = () => m_DebugUISystem.developerInfoVisible,
					setter = delegate(bool value)
					{
						m_DebugUISystem.developerInfoVisible = value;
					}
				},
				new DebugUI.BoolField
				{
					displayName = "Show unspawned objects",
					getter = () => m_RenderingSystem.unspawnedVisible,
					setter = delegate(bool value)
					{
						m_RenderingSystem.unspawnedVisible = value;
					}
				},
				new DebugUI.BoolField
				{
					displayName = "Show markers",
					getter = () => m_RenderingSystem.markersVisible,
					setter = delegate(bool value)
					{
						m_RenderingSystem.markersVisible = value;
					}
				},
				new DebugUI.BoolField
				{
					displayName = "Lefthand traffic",
					getter = () => m_CityConfigurationSystem.leftHandTraffic,
					setter = delegate(bool value)
					{
						m_CityConfigurationSystem.leftHandTraffic = value;
					}
				},
				new DebugUI.Value
				{
					displayName = "Default theme",
					getter = () => (!(m_CityConfigurationSystem.defaultTheme != Entity.Null)) ? "None" : m_PrefabSystem.GetPrefab<PrefabBase>(m_CityConfigurationSystem.defaultTheme).name
				},
				new DebugUI.Button
				{
					displayName = "Select next theme",
					action = delegate
					{
						m_CityConfigurationSystem.defaultTheme = SelectNext(m_ThemeQuery, m_CityConfigurationSystem.defaultTheme);
					}
				},
				new DebugUI.Button
				{
					displayName = "Unlock all",
					action = delegate
					{
						m_UnlockAllSystem.Enabled = true;
					}
				},
				new DebugUI.Button
				{
					displayName = "Get 200 XP",
					action = delegate
					{
						GetXP();
					}
				},
				new DebugUI.Button
				{
					displayName = "Next MS",
					action = delegate
					{
						UnlockMilestone();
					}
				},
				new DebugUI.Button
				{
					displayName = "Get 500k money",
					action = delegate
					{
						GetMoney(500000);
					}
				},
				new DebugUI.IntField
				{
					displayName = "Hospital service fee",
					getter = () => (int)GetFee(PlayerResource.Healthcare),
					setter = delegate(int value)
					{
						SetFee(PlayerResource.Healthcare, value);
					},
					min = () => 0,
					max = () => 1000,
					incStep = 10
				},
				new DebugUI.IntField
				{
					displayName = "Basic education service fee",
					getter = () => (int)GetFee(PlayerResource.BasicEducation),
					setter = delegate(int value)
					{
						SetFee(PlayerResource.BasicEducation, value);
					},
					min = () => 0,
					max = () => 1000,
					incStep = 10
				},
				new DebugUI.IntField
				{
					displayName = "Secondary education service fee",
					getter = () => (int)GetFee(PlayerResource.SecondaryEducation),
					setter = delegate(int value)
					{
						SetFee(PlayerResource.SecondaryEducation, value);
					},
					min = () => 0,
					max = () => 1000,
					incStep = 10
				},
				new DebugUI.IntField
				{
					displayName = "Higher education service fee",
					getter = () => (int)GetFee(PlayerResource.HigherEducation),
					setter = delegate(int value)
					{
						SetFee(PlayerResource.HigherEducation, value);
					},
					min = () => 0,
					max = () => 1000,
					incStep = 10
				},
				new DebugUI.FloatField
				{
					displayName = "Water usage fee",
					getter = () => GetFee(PlayerResource.Water),
					setter = delegate(float value)
					{
						SetFee(PlayerResource.Water, value);
					},
					min = () => 0f,
					max = () => 5f,
					incStep = 0.05f
				},
				new DebugUI.FloatField
				{
					displayName = "Garbage collection fee",
					getter = () => GetFee(PlayerResource.Garbage),
					setter = delegate(float value)
					{
						SetFee(PlayerResource.Garbage, value);
					},
					min = () => 0f,
					max = () => 1f,
					incStep = 0.01f
				},
				new DebugUI.FloatField
				{
					displayName = "Electricity fee",
					getter = () => GetFee(PlayerResource.Electricity),
					setter = delegate(float value)
					{
						SetFee(PlayerResource.Electricity, value);
					},
					min = () => 0.01f,
					max = () => 1f,
					incStep = 0.01f
				},
				new DebugUI.IntField
				{
					displayName = "Public transport fee",
					getter = () => (int)GetFee(PlayerResource.PublicTransport),
					setter = delegate(int value)
					{
						SetFee(PlayerResource.PublicTransport, value);
					},
					min = () => 0,
					max = () => 20,
					incStep = 1
				},
				new DebugUI.Button
				{
					displayName = "Display debug error",
					action = ErrorDialogManager.DisplayDebugErrorDialog
				},
				new DebugUI.Button
				{
					displayName = "Show signature buildings unlock popup",
					action = ShowSignaturePopup
				},
				new DebugUI.Button
				{
					displayName = "Clear signature buildings unlock popup",
					action = ClearSignaturePopup
				}
			};
		}
		return null;
		void ClearSignaturePopup()
		{
			m_SignatureBuildingUISystem.ClearUnlockedSignature();
		}
		float GetFee(PlayerResource resource)
		{
			if (base.World.EntityManager.TryGetBuffer(m_CitySystem.City, isReadOnly: true, out DynamicBuffer<ServiceFee> buffer2))
			{
				return ServiceFeeSystem.GetFee(resource, buffer2);
			}
			return 0f;
		}
		void GetMoney(int amount)
		{
			PlayerMoney componentData = base.EntityManager.GetComponentData<PlayerMoney>(m_CitySystem.City);
			componentData.Add(500000);
			base.EntityManager.SetComponentData(m_CitySystem.City, componentData);
		}
		void GetXP()
		{
			base.World.GetOrCreateSystemManaged<XPSystem>().GetQueue(out var _).Enqueue(new XPGain
			{
				reason = XPReason.Unknown,
				amount = 200
			});
		}
		void SetFee(PlayerResource resource, float value)
		{
			if (base.World.EntityManager.TryGetBuffer(m_CitySystem.City, isReadOnly: false, out DynamicBuffer<ServiceFee> buffer2))
			{
				ServiceFeeSystem.SetFee(resource, buffer2, value);
			}
		}
		void ShowSignaturePopup()
		{
			if (m_SignatureBuildingQuery.IsEmptyIgnoreFilter)
			{
				return;
			}
			foreach (Entity item in m_SignatureBuildingQuery.ToEntityArray(Allocator.Temp))
			{
				m_SignatureBuildingUISystem.AddUnlockedSignature(item);
			}
		}
		void UnlockMilestone()
		{
			int xP = GetEntityQuery(ComponentType.ReadOnly<XP>()).GetSingleton<XP>().m_XP;
			GetEntityQuery(ComponentType.ReadOnly<MilestoneLevel>()).GetSingleton<MilestoneLevel>();
			int amount = base.World.GetOrCreateSystemManaged<MilestoneSystem>().nextRequiredXP - xP;
			base.World.GetOrCreateSystemManaged<XPSystem>().GetQueue(out var _).Enqueue(new XPGain
			{
				reason = XPReason.Unknown,
				amount = amount
			});
		}
	}
```

- `private static BuildGizmosDebugUI(Unity.Entities.World world) : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private static List<DebugUI.Widget> BuildGizmosDebugUI(World world)
	{
		DebugUI.Value value = new DebugUI.Value
		{
			displayName = "Buildable Area",
			getter = () => (int)math.round(100f * world.GetOrCreateSystemManaged<BuildableAreaDebugSystem>().buildableArea)
		};
		DebugUI.Container container = new DebugUI.Container();
		AddSystemGizmoField<ObjectDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<NetDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<LaneDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<LightDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<WaterCullingDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<ZoneDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<AreaDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<CollapseSFXDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<ZoneAmbienceValueDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<RouteDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<NavigationDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<AvailabilityDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<DensityDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<CoverageDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<PathDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<PathfindDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<SearchTreeDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<TerrainAttractivenessDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<LandValueDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<EconomyDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<PollutionDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<GroundWaterDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<SoilWaterDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<GarbageDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<WaterDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<WindDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<EventDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<PropertyDebugSystem>(ref container, world, Array.Empty<DebugUI.Widget>());
		AddSystemGizmoField<BuildableAreaDebugSystem>(ref container, world, new DebugUI.Widget[1] { value });
		return new List<DebugUI.Widget> { container };
	}
```

- `private BuildingMoveUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Void`  

```csharp
private void BuildingMoveUI(DebugUI.Container container, Entity entity, Entity prefab)
	{
		if (m_ToolSystem.actionMode.IsEditor())
		{
			if (base.EntityManager.HasComponent<Game.Objects.Transform>(entity))
			{
				ObjectToolSystem objectToolSystem = GetTool<ObjectToolSystem>();
				container.children.Add(new DebugUI.Button
				{
					displayName = "Move",
					action = delegate
					{
						objectToolSystem.StartMoving(m_ToolSystem.selected);
						m_ToolSystem.activeTool = objectToolSystem;
					}
				});
			}
		}
		else if (base.EntityManager.HasComponent<Building>(entity) && !base.EntityManager.HasComponent<SpawnableBuildingData>(prefab))
		{
			if (base.EntityManager.HasComponent<Destroyed>(entity))
			{
				UpgradeToolSystem uts = GetTool<UpgradeToolSystem>();
				container.children.Add(new DebugUI.Button
				{
					displayName = "Rebuild",
					action = delegate
					{
						uts.prefab = null;
						m_ToolSystem.activeTool = uts;
					}
				});
			}
			else
			{
				ObjectToolSystem objectToolSystem2 = GetTool<ObjectToolSystem>();
				container.children.Add(new DebugUI.Button
				{
					displayName = "Relocate",
					action = delegate
					{
						objectToolSystem2.StartMoving(m_ToolSystem.selected);
						m_ToolSystem.activeTool = objectToolSystem2;
					}
				});
			}
		}
		if (base.EntityManager.HasComponent<Game.Objects.Object>(entity))
		{
			container.children.Add(new DebugUI.Button
			{
				displayName = "Update",
				action = delegate
				{
					m_EndFrameBarrier.CreateCommandBuffer().AddComponent(entity, default(Updated));
				}
			});
		}
	}
```

- `private BuildingUpgradeUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity prefab) : System.Void`  

```csharp
private void BuildingUpgradeUI(DebugUI.Container container, Entity prefab)
	{
		if (!base.EntityManager.HasComponent<BuildingUpgradeElement>(prefab))
		{
			return;
		}
		DynamicBuffer<BuildingUpgradeElement> buffer = base.EntityManager.GetBuffer<BuildingUpgradeElement>(prefab, isReadOnly: true);
		for (int i = 0; i < buffer.Length; i++)
		{
			Entity upgrade = buffer[i].m_Upgrade;
			PrefabBase prefab2 = m_PrefabSystem.GetPrefab<PrefabBase>(upgrade);
			container.children.Add(new DebugUI.Button
			{
				displayName = "Upgrade " + prefab2.name,
				action = delegate
				{
					Upgrade(upgrade);
				}
			});
		}
		void Upgrade(Entity entity)
		{
			if (base.EntityManager.HasComponent<PlaceableObjectData>(entity))
			{
				ObjectToolSystem tool = GetTool<ObjectToolSystem>();
				tool.mode = ObjectToolSystem.Mode.Upgrade;
				tool.prefab = m_PrefabSystem.GetPrefab<ObjectPrefab>(entity);
				m_ToolSystem.activeTool = tool;
			}
			else
			{
				UpgradeToolSystem tool2 = GetTool<UpgradeToolSystem>();
				tool2.prefab = m_PrefabSystem.GetPrefab<ObjectPrefab>(entity);
				m_ToolSystem.activeTool = tool2;
			}
		}
	}
```

- `private BuildNotificationsDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private List<DebugUI.Widget> BuildNotificationsDebugUI()
	{
		List<DebugUI.Widget> list = new List<DebugUI.Widget>
		{
			new DebugUI.Button
			{
				displayName = "Refresh",
				action = delegate
				{
					RefreshNotifications();
					Rebuild(BuildNotificationsDebugUI);
				}
			}
		};
		if (m_Notifications != null)
		{
			list.Add(new DebugUI.Container
			{
				displayName = "Notifications",
				children = { (IEnumerable<DebugUI.Widget>)m_Notifications.Select((NotificationInfo info) => new DebugUI.BoolField
				{
					displayName = $"{m_PrefabSystem.GetPrefab<NotificationIconPrefab>(info.m_Prefab).name} ({info.m_Instances})",
					getter = () => base.EntityManager.IsComponentEnabled<NotificationIconDisplayData>(info.m_Prefab),
					setter = delegate(bool value)
					{
						EnableNotification(info.m_Prefab, value);
					}
				}) }
			});
		}
		return list;
	}
```

- `private BuildPathfindDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private List<DebugUI.Widget> BuildPathfindDebugUI()
	{
		PathfindResultSystem pathfindResultSystem = base.World.GetOrCreateSystemManaged<PathfindResultSystem>();
		PathfindQueueSystem pathfindQueueSystem = base.World.GetOrCreateSystemManaged<PathfindQueueSystem>();
		DebugUI.Table table = new DebugUI.Table
		{
			displayName = "Top 20 queries",
			isReadOnly = true
		};
		for (int i = 0; i < 20; i++)
		{
			int index = i;
			DebugUI.Table.Row row = new DebugUI.Table.Row
			{
				displayName = "#" + (i + 1),
				opened = true
			};
			row.children.Add(new DebugUI.Value
			{
				displayName = "System type",
				getter = () => GetPathfindSystem(index)
			});
			row.children.Add(new DebugUI.Value
			{
				displayName = "Query type",
				getter = () => GetPathfindType(index)
			});
			row.children.Add(new DebugUI.Value
			{
				displayName = "Query count",
				getter = () => GetPathfindCount(index)
			});
			row.children.Add(new DebugUI.Value
			{
				displayName = "Success rate",
				getter = () => GetSuccessRate(index)
			});
			row.children.Add(new DebugUI.Value
			{
				displayName = "Average graph traversal",
				getter = () => GetPathfindTraversal(index)
			});
			row.children.Add(new DebugUI.Value
			{
				displayName = "Average efficiency",
				getter = () => GetPathfindEfficiency(index)
			});
			table.children.Add(row);
		}
		return new List<DebugUI.Widget>
		{
			new DebugUI.Value
			{
				displayName = "Graph edge count",
				getter = () => pathfindQueueSystem.GetGraphSize()
			},
			new DebugUI.Value
			{
				displayName = "Graph memory",
				getter = GetGraphMemory
			},
			new DebugUI.Value
			{
				displayName = "Query memory",
				getter = GetQueryMemory
			},
			new DebugUI.Value
			{
				displayName = "Pending queries",
				getter = () => pathfindResultSystem.pendingRequestCount
			},
			new DebugUI.Value
			{
				displayName = "Simulation frame margin",
				getter = GetSimulationFrameMargin
			},
			new DebugUI.Value
			{
				displayName = "Total queries",
				getter = () => GetPathfindCount(-1)
			},
			new DebugUI.Value
			{
				displayName = "Success rate",
				getter = () => GetSuccessRate(-1)
			},
			new DebugUI.Value
			{
				displayName = "Average graph traversal",
				getter = () => GetPathfindTraversal(-1)
			},
			new DebugUI.Value
			{
				displayName = "Average efficiency",
				getter = () => GetPathfindEfficiency(-1)
			},
			table
		};
		string GetGraphMemory()
		{
			pathfindQueueSystem.GetGraphMemory(out var usedMemory, out var allocatedMemory);
			return FormatUtils.FormatBytes(usedMemory) + " / " + FormatUtils.FormatBytes(allocatedMemory);
		}
		object GetPathfindCount(int num)
		{
			if (num < 0)
			{
				Dictionary<PathfindResultSystem.ResultKey, PathfindResultSystem.ResultValue> queryStats = pathfindResultSystem.queryStats;
				if (m_PathfindQueryBuffer != null)
				{
					m_PathfindQueryBuffer.Clear();
				}
				else
				{
					m_PathfindQueryBuffer = new List<PathfindQueryItem>(queryStats.Count);
				}
				foreach (KeyValuePair<PathfindResultSystem.ResultKey, PathfindResultSystem.ResultValue> item in queryStats)
				{
					m_PathfindQueryBuffer.Add(new PathfindQueryItem
					{
						m_Key = item.Key,
						m_Value = item.Value
					});
				}
				m_PathfindQueryBuffer.Sort();
				int num2 = 0;
				for (int j = 0; j < m_PathfindQueryBuffer.Count; j++)
				{
					num2 += m_PathfindQueryBuffer[j].m_Value.m_QueryCount;
				}
				return num2;
			}
			if (m_PathfindQueryBuffer != null && num < m_PathfindQueryBuffer.Count)
			{
				return m_PathfindQueryBuffer[num].m_Value.m_QueryCount;
			}
			return "-";
		}
		object GetPathfindEfficiency(int num)
		{
			if (m_PathfindQueryBuffer == null)
			{
				return "-";
			}
			if (num < 0)
			{
				int num2 = 0;
				float num3 = 0f;
				for (int j = 0; j < m_PathfindQueryBuffer.Count; j++)
				{
					PathfindResultSystem.ResultValue resultValue = m_PathfindQueryBuffer[j].m_Value;
					num2 += resultValue.m_QueryCount;
					num3 += resultValue.m_Efficiency;
				}
				return num3 / math.max(1f, num2) * 100f + " %";
			}
			if (num < m_PathfindQueryBuffer.Count)
			{
				PathfindResultSystem.ResultValue resultValue2 = m_PathfindQueryBuffer[num].m_Value;
				return resultValue2.m_Efficiency / math.max(1f, resultValue2.m_QueryCount) * 100f + " %";
			}
			return "-";
		}
		object GetPathfindSystem(int num)
		{
			if (m_PathfindQueryBuffer != null && num < m_PathfindQueryBuffer.Count)
			{
				PathfindResultSystem.ResultKey resultKey = m_PathfindQueryBuffer[num].m_Key;
				if (resultKey.m_System != null)
				{
					return resultKey.m_System.GetType().Name;
				}
				return "-";
			}
			return "-";
		}
		object GetPathfindTraversal(int num)
		{
			if (m_PathfindQueryBuffer == null)
			{
				return "-";
			}
			if (num < 0)
			{
				int num2 = 0;
				float num3 = 0f;
				for (int j = 0; j < m_PathfindQueryBuffer.Count; j++)
				{
					PathfindResultSystem.ResultValue resultValue = m_PathfindQueryBuffer[j].m_Value;
					num2 += resultValue.m_QueryCount;
					num3 += resultValue.m_GraphTraversal;
				}
				return num3 / math.max(1f, num2) * 100f + " %";
			}
			if (num < m_PathfindQueryBuffer.Count)
			{
				PathfindResultSystem.ResultValue resultValue2 = m_PathfindQueryBuffer[num].m_Value;
				return resultValue2.m_GraphTraversal / math.max(1f, resultValue2.m_QueryCount) * 100f + " %";
			}
			return "-";
		}
		object GetPathfindType(int num)
		{
			if (m_PathfindQueryBuffer != null && num < m_PathfindQueryBuffer.Count)
			{
				PathfindResultSystem.ResultKey resultKey = m_PathfindQueryBuffer[num].m_Key;
				switch (resultKey.m_QueryType)
				{
				case PathfindResultSystem.QueryType.Pathfind:
					if (resultKey.m_OriginType == SetupTargetType.None && resultKey.m_DestinationType == SetupTargetType.None)
					{
						return "Pathfind";
					}
					return resultKey.m_OriginType.ToString() + " -> " + resultKey.m_DestinationType;
				case PathfindResultSystem.QueryType.Coverage:
					return "Coverage";
				case PathfindResultSystem.QueryType.Availability:
					return "Availability";
				default:
					return "-";
				}
			}
			return "-";
		}
		string GetQueryMemory()
		{
			pathfindQueueSystem.GetQueryMemory(out var usedMemory, out var allocatedMemory);
			return FormatUtils.FormatBytes(usedMemory) + " / " + FormatUtils.FormatBytes(allocatedMemory);
		}
		object GetSimulationFrameMargin()
		{
			if (pathfindResultSystem.pendingSimulationFrame < uint.MaxValue)
			{
				int num = (int)math.max(0u, pathfindResultSystem.pendingSimulationFrame - m_SimulationSystem.frameIndex - 1);
				if (num > 0)
				{
					float num2 = (float)num * (1f / 48f);
					if (num2 < 1f)
					{
						return $"{num}: Slowing down ({num2}x)";
					}
					return num;
				}
				return "None: Blocking simulation!";
			}
			return "Infinite";
		}
		object GetSuccessRate(int num)
		{
			if (m_PathfindQueryBuffer == null)
			{
				return "-";
			}
			if (num < 0)
			{
				int num2 = 0;
				int num3 = 0;
				for (int j = 0; j < m_PathfindQueryBuffer.Count; j++)
				{
					PathfindResultSystem.ResultValue resultValue = m_PathfindQueryBuffer[j].m_Value;
					num2 += resultValue.m_QueryCount;
					num3 += resultValue.m_SuccessCount;
				}
				return (float)num3 / math.max(1f, num2) * 100f + " %";
			}
			if (num < m_PathfindQueryBuffer.Count)
			{
				PathfindResultSystem.ResultValue resultValue2 = m_PathfindQueryBuffer[num].m_Value;
				return (float)resultValue2.m_SuccessCount / math.max(1f, resultValue2.m_QueryCount) * 100f + " %";
			}
			return "-";
		}
	}
```

- `private static BuildPlatformsDebugUI(Unity.Entities.World world) : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private static List<DebugUI.Widget> BuildPlatformsDebugUI(World world)
	{
		if (!GameManager.instance.configuration.qaDeveloperMode)
		{
			return null;
		}
		AchievementTriggerSystem achievementTriggerSystem = world.GetExistingSystemManaged<AchievementTriggerSystem>();
		DebugUI.Foldout foldout = new DebugUI.Foldout
		{
			displayName = "Platform managers"
		};
		foreach (IPlatformSupport platformManager in PlatformManager.instance.platformManagers)
		{
			foldout.children.Add(new DebugUI.BoolField
			{
				displayName = platformManager.name,
				getter = () => platformManager.isInitialized,
				setter = delegate(bool value)
				{
					if (value)
					{
						platformManager.Initialize(CancellationToken.None);
					}
					else
					{
						platformManager.Dispose(disposeEvents: false, CancellationToken.None);
					}
				}
			});
		}
		DebugUI.Foldout foldout2 = new DebugUI.Foldout
		{
			displayName = "Remote storages"
		};
		foreach (IRemoteStorageSupport remoteStorage in PlatformManager.instance.remoteStorages)
		{
			foldout2.children.Add(new DebugUI.Value
			{
				displayName = remoteStorage.name,
				getter = () => (!remoteStorage.isInitialized) ? "Not Initialized" : "Initialized"
			});
			foldout2.children.Add(new DebugUI.Button
			{
				displayName = "Wipe data",
				action = delegate
				{
					GameManager.instance.userInterface.appBindings.ShowConfirmationDialog(new ConfirmationDialog(null, "Common.DIALOG_MESSAGE[ConfirmRemoteStorageWipe]", "Common.DIALOG_ACTION[Yes]", "Common.DIALOG_ACTION[No]"), delegate(int ret)
					{
						if (ret == 0)
						{
							remoteStorage.Wipe();
						}
					});
				}
			});
		}
		DebugUI.Foldout foldout3 = new DebugUI.Foldout
		{
			displayName = "User backends"
		};
		foreach (IUserSupport userBackend in PlatformManager.instance.userBackends)
		{
			foldout3.children.Add(new DebugUI.Value
			{
				displayName = userBackend.name,
				getter = () => (!userBackend.isInitialized) ? "Not Initialized" : "Initialized"
			});
		}
		DebugUI.Foldout foldout4 = new DebugUI.Foldout
		{
			displayName = "Mod Backends"
		};
		foreach (IModSupport modBackend in PlatformManager.instance.modsBackends)
		{
			foldout4.children.Add(new DebugUI.Value
			{
				displayName = modBackend.name,
				getter = () => (!modBackend.isInitialized) ? "Not Initialized" : "Initialized"
			});
		}
		DebugUI.Foldout foldout5 = new DebugUI.Foldout
		{
			displayName = "Telemetry Backends"
		};
		foreach (ITelemetrySupport telemetryBackend in PlatformManager.instance.telemetryBackends)
		{
			foldout5.children.Add(new DebugUI.Value
			{
				displayName = telemetryBackend.name,
				getter = () => (!telemetryBackend.isInitialized) ? "Not Initialized" : "Initialized"
			});
		}
		DebugUI.Foldout foldout6 = new DebugUI.Foldout
		{
			displayName = "Achievements Backends"
		};
		foldout6.children.Add(new DebugUI.Value
		{
			displayName = "Achievements enabled",
			getter = () => PlatformManager.instance.achievementsEnabled
		});
		foreach (IAchievementsSupport achievementsBackend in PlatformManager.instance.achievementsBackends)
		{
			foldout6.children.Add(new DebugUI.Value
			{
				displayName = achievementsBackend.name,
				getter = () => (!achievementsBackend.isInitialized) ? "Not Initialized" : "Initialized"
			});
			DebugUI.Foldout foldout7 = new DebugUI.Foldout
			{
				displayName = $"{achievementsBackend.name} entries ({achievementsBackend.CountAchievements(onlyAchieved: true)}/{achievementsBackend.CountAchievements()})"
			};
			foreach (IAchievement achievement in achievementsBackend.EnumerateAchievements())
			{
				DebugUI.Foldout foldout8 = new DebugUI.Foldout
				{
					displayName = $"{achievement.internalName} ({achievement.id})"
				};
				foldout8.children.Add(new DebugUI.Value
				{
					displayName = achievement.backendId,
					getter = () => string.Empty
				});
				foldout8.children.Add(new DebugUI.Value
				{
					displayName = "Achieved",
					getter = () => achievement.achieved
				});
				if (achievement.isIncremental)
				{
					foldout8.children.Add(new DebugUI.Value
					{
						displayName = "Progress",
						getter = () => $"{(achievement.achieved ? achievement.maxProgress : achievement.progress)}/{achievement.maxProgress}"
					});
				}
				if (achievementTriggerSystem.GetDebugData(achievement.id, out var _))
				{
					foldout8.children.Add(new DebugUI.Value
					{
						displayName = "Additional data",
						getter = () => (!achievementTriggerSystem.GetDebugData(achievement.id, out var data2)) ? string.Empty : data2
					});
				}
				foldout7.children.Add(foldout8);
			}
			foldout7.children.Add(new DebugUI.Button
			{
				displayName = "Reset",
				action = delegate
				{
					achievementsBackend.ResetAchievements();
				}
			});
			foldout6.children.Add(foldout7);
		}
		DebugUI.Foldout foldout9 = new DebugUI.Foldout
		{
			displayName = "Rich presence handlers"
		};
		foreach (IRichPresenceSupport richPresenceHandler in PlatformManager.instance.richPresenceHandlers)
		{
			foldout9.children.Add(new DebugUI.Value
			{
				displayName = richPresenceHandler.name,
				getter = () => (!richPresenceHandler.isInitialized) ? "Not Initialized" : "Initialized"
			});
		}
		DebugUI.Foldout foldout10 = new DebugUI.Foldout
		{
			displayName = "Virtual keyboard support"
		};
		foreach (IVirtualKeyboardSupport virtualKeyboardHandler in PlatformManager.instance.virtualKeyboardHandlers)
		{
			foldout10.children.Add(new DebugUI.Value
			{
				displayName = virtualKeyboardHandler.name,
				getter = () => (!virtualKeyboardHandler.isInitialized) ? "Not Initialized" : "Initialized"
			});
		}
		DebugUI.Foldout foldout11 = new DebugUI.Foldout
		{
			displayName = "Overlay support"
		};
		foreach (IOverlaySupport overlayHandler in PlatformManager.instance.overlayHandlers)
		{
			foldout11.children.Add(new DebugUI.Value
			{
				displayName = overlayHandler.name,
				getter = () => overlayHandler.isOverlaySupported
			});
		}
		DebugUI.Foldout foldout12 = new DebugUI.Foldout
		{
			displayName = "Transfer managers"
		};
		foreach (ITransferSupport transferManager in PlatformManager.instance.transferManagers)
		{
			foldout12.children.Add(new DebugUI.Value
			{
				displayName = transferManager.name,
				getter = () => (!transferManager.isInitialized) ? "Not Initialized" : "Initialized"
			});
		}
		DebugUI.Foldout foldout13 = new DebugUI.Foldout
		{
			displayName = "Device association support"
		};
		foreach (IDeviceAssociationSupport deviceAssociationHandler in PlatformManager.instance.deviceAssociationHandlers)
		{
			foldout13.children.Add(new DebugUI.Value
			{
				displayName = deviceAssociationHandler.name,
				getter = () => (!deviceAssociationHandler.isInitialized) ? "Not Initialized" : "Initialized"
			});
		}
		DebugUI.Foldout foldout14 = new DebugUI.Foldout
		{
			displayName = "Dlc backends"
		};
		PlatformManager localBackend = PlatformManager.instance;
		foldout14.children.Add(new DebugUI.Value
		{
			displayName = localBackend.name,
			getter = () => (!localBackend.isInitialized) ? "Not Initialized" : "Initialized"
		});
		DebugUI.Foldout foldout15 = new DebugUI.Foldout
		{
			displayName = $"{localBackend.name} entries ({localBackend.dlcCount}/{PlatformManager.instance.dlcCount})"
		};
		foreach (IDlc item4 in localBackend.EnumerateLocalDLCs())
		{
			bool isOwned = localBackend.IsDlcOwned(item4.id);
			DebugUI.Value item = new DebugUI.Value
			{
				displayName = $"{item4.internalName} ({item4.id})",
				getter = () => (!isOwned) ? "Not Owned" : "Owned"
			};
			foldout15.children.Add(item);
		}
		foldout14.children.Add(foldout15);
		foreach (IDlcSupport dlcBackend in PlatformManager.instance.dlcBackends)
		{
			foldout14.children.Add(new DebugUI.Value
			{
				displayName = dlcBackend.name,
				getter = () => (!dlcBackend.isInitialized) ? "Not Initialized" : "Initialized"
			});
			DebugUI.Foldout foldout16 = new DebugUI.Foldout
			{
				displayName = $"{dlcBackend.name} entries ({dlcBackend.dlcCount}/{PlatformManager.instance.dlcCount})"
			};
			foreach (IDlc item5 in dlcBackend.EnumerateDLCs())
			{
				bool isOwned2 = dlcBackend.IsDlcOwned(item5);
				DebugUI.Value item2 = new DebugUI.Value
				{
					displayName = $"{item5.internalName} ({item5.id})",
					getter = () => (!isOwned2) ? "Not Owned" : "Owned"
				};
				foldout16.children.Add(item2);
			}
			foldout14.children.Add(foldout16);
		}
		DebugUI.Foldout foldout17 = new DebugUI.Foldout
		{
			displayName = "App state handlers"
		};
		foreach (IAppStateSupport appStateHandler in PlatformManager.instance.appStateHandlers)
		{
			foldout17.children.Add(new DebugUI.Value
			{
				displayName = appStateHandler.name,
				getter = () => (!appStateHandler.isInitialized) ? "Not Initialized" : "Initialized"
			});
		}
		DebugUI.Foldout foldout18 = new DebugUI.Foldout
		{
			displayName = "Screen capture handlers"
		};
		foreach (IScreenCaptureSupport screenCaptureHandler in PlatformManager.instance.screenCaptureHandlers)
		{
			foldout18.children.Add(new DebugUI.Value
			{
				displayName = screenCaptureHandler.name,
				getter = () => (!screenCaptureHandler.isInitialized) ? "Not Initialized" : "Initialized"
			});
		}
		DebugUI.Foldout foldout19 = new DebugUI.Foldout
		{
			displayName = "Content Prefabs"
		};
		string[] availablePrerequisitesNames = GameManager.instance.GetAvailablePrerequisitesNames();
		if (availablePrerequisitesNames != null)
		{
			string[] array = availablePrerequisitesNames;
			foreach (string displayName in array)
			{
				foldout19.children.Add(new DebugUI.Value
				{
					displayName = displayName,
					getter = () => string.Empty
				});
			}
		}
		List<DebugUI.Widget> list = new List<DebugUI.Widget>
		{
			foldout, foldout2, foldout3, foldout4, foldout5, foldout6, foldout9, foldout10, foldout11, foldout12,
			foldout13, foldout14, foldout17, foldout18, foldout19
		};
		PdxSdkPlatform pdxSdkPlatform = PlatformManager.instance.GetPSI<PdxSdkPlatform>("PdxSdk");
		if (pdxSdkPlatform != null)
		{
			DebugUI.Button item3 = new DebugUI.Button
			{
				displayName = "Reset pdx content unlock",
				action = delegate
				{
					foreach (IDlc item6 in pdxSdkPlatform.EnumerateDLCs())
					{
						PlatformManager.instance.UserDataDelete(item6.internalName);
					}
					PlatformManager.instance.UserDataDelete("hasEverLoggedIn");
				}
			};
			list.Add(item3);
		}
		return list;
	}
```

- `private BuildRenderingDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private List<DebugUI.Widget> BuildRenderingDebugUI()
	{
		InitializeRenderingDebugUI();
		DebugUI.Foldout foldout = new DebugUI.Foldout
		{
			displayName = "Custom passes"
		};
		CustomPassVolume[] array = UnityEngine.Object.FindObjectsOfType<CustomPassVolume>();
		for (int i = 0; i < array.Length; i++)
		{
			foreach (CustomPass cp in array[i].customPasses)
			{
				foldout.children.Add(new DebugUI.BoolField
				{
					displayName = cp.name,
					getter = () => cp.enabled,
					setter = delegate(bool value)
					{
						cp.enabled = value;
					}
				});
			}
		}
		TerrainSurface terrainSurface = TerrainSurface.GetValidSurface();
		DebugUI.Foldout foldout2 = new DebugUI.Foldout
		{
			displayName = "Terrain"
		};
		foldout2.children.Add(new DebugUI.IntField
		{
			displayName = "CBT Max Depth",
			getter = () => (!(terrainSurface != null)) ? 25 : terrainSurface.MaxTreeDepth,
			setter = delegate(int value)
			{
				if (terrainSurface != null)
				{
					terrainSurface.MaxTreeDepth = value;
				}
			},
			min = () => 8,
			max = () => 28,
			incStep = 1
		});
		foldout2.children.Add(new DebugUI.Value
		{
			displayName = "Tri count",
			getter = () => (terrainSurface != null) ? terrainSurface.GetCameraTriangleCount(Camera.main) : (-1)
		});
		foldout2.children.Add(new DebugUI.BoolField
		{
			displayName = "Foliage",
			getter = () => m_VegetationRenderSystem.Enabled,
			setter = delegate(bool value)
			{
				m_VegetationRenderSystem.Enabled = value;
			}
		});
		foldout2.children.Add(new DebugUI.Button
		{
			displayName = "Refresh splatmap",
			action = delegate
			{
				m_TerrainMaterialSystem.ForceUpdateWholeSplatmap();
			}
		});
		List<DebugUI.Widget> list = new List<DebugUI.Widget>
		{
			new DebugUI.EnumField
			{
				displayName = "Texture Debug Mode",
				getter = () => (int)m_DebugBlitPass.textureDebugMode,
				setter = delegate(int value)
				{
					m_DebugBlitPass.textureDebugMode = (DebugCustomPass.TextureDebugMode)value;
				},
				autoEnum = typeof(DebugCustomPass.TextureDebugMode),
				onValueChanged = RebuildRenderingDebugUI<int>,
				getIndex = () => (int)m_DebugBlitPass.textureDebugMode,
				setIndex = delegate(int value)
				{
					m_DebugBlitPass.textureDebugMode = (DebugCustomPass.TextureDebugMode)value;
				}
			}
		};
		if (m_DebugBlitPass.textureDebugMode != DebugCustomPass.TextureDebugMode.None)
		{
			m_DebugBlitPass.sliceIndex = 0;
			DebugUI.Container container = new DebugUI.Container();
			m_DebugBlitPass.minValue = m_DebugBlitPass.GetDefaultMinValue();
			m_DebugBlitPass.maxValue = m_DebugBlitPass.GetDefaultMaxValue();
			m_DebugBlitPass.showExtra = m_DebugBlitPass.HasExtra();
			if (m_DebugBlitPass.SetupTexture(out var tex, out var sliceCount))
			{
				container.children.Add(new DebugUI.Value
				{
					displayName = "Format",
					getter = () => (tex != null) ? tex.graphicsFormat : GraphicsFormat.None
				});
				container.children.Add(new DebugUI.FloatField
				{
					displayName = "Overlay Ratio",
					getter = () => m_DebugBlitPass.debugOverlayRatio,
					setter = delegate(float value)
					{
						m_DebugBlitPass.debugOverlayRatio = value;
					},
					min = () => 0f,
					max = () => 1f,
					incStep = 0.001f
				});
				if (sliceCount > 0)
				{
					container.children.Add(new DebugUI.IntField
					{
						displayName = "Slice",
						getter = () => m_DebugBlitPass.sliceIndex,
						setter = delegate(int value)
						{
							m_DebugBlitPass.sliceIndex = value;
						},
						min = () => 0,
						max = () => sliceCount,
						incStep = 1
					});
				}
			}
			if (m_DebugBlitPass.textureDebugMode == DebugCustomPass.TextureDebugMode.TerrainTesselation)
			{
				container.children.Add(new DebugUI.Value
				{
					displayName = "Terrain triangle count",
					getter = () => (terrainSurface != null) ? terrainSurface.GetCameraTriangleCount(Camera.main) : (-1)
				});
			}
			list.Add(container);
		}
		if (m_DebugBlitPass.textureDebugMode >= DebugCustomPass.TextureDebugMode.HeightMap && m_DebugBlitPass.textureDebugMode <= DebugCustomPass.TextureDebugMode.Wind)
		{
			m_DebugBlitPass.minValue = m_DebugBlitPass.GetDefaultMinValue();
			m_DebugBlitPass.maxValue = m_DebugBlitPass.GetDefaultMaxValue();
			m_DebugBlitPass.showExtra = m_DebugBlitPass.HasExtra();
			list.Add(new DebugUI.Container
			{
				children = 
				{
					(DebugUI.Widget)new DebugUI.FloatField
					{
						displayName = "Zoom Level",
						getter = () => m_DebugBlitPass.zoom,
						setter = delegate(float value)
						{
							m_DebugBlitPass.zoom = value;
						},
						min = () => 0f,
						max = () => 1f,
						incStep = 0.001f
					},
					(DebugUI.Widget)new DebugUI.FloatField
					{
						displayName = "Min Range",
						getter = () => m_DebugBlitPass.minValue,
						setter = delegate(float value)
						{
							m_DebugBlitPass.minValue = value;
						},
						min = () => m_DebugBlitPass.GetMinValue(),
						max = () => m_DebugBlitPass.GetMaxValue(),
						incStep = 0.001f
					},
					(DebugUI.Widget)new DebugUI.FloatField
					{
						displayName = "Max Range",
						getter = () => m_DebugBlitPass.maxValue,
						setter = delegate(float value)
						{
							m_DebugBlitPass.maxValue = value;
						},
						min = () => m_DebugBlitPass.GetMinValue(),
						max = () => m_DebugBlitPass.GetMaxValue(),
						incStep = 0.001f
					}
				}
			});
			if (m_DebugBlitPass.HasExtra())
			{
				list.Add(new DebugUI.Container
				{
					children = { (DebugUI.Widget)new DebugUI.BoolField
					{
						displayName = "Show Extra",
						getter = () => m_DebugBlitPass.showExtra,
						setter = delegate(bool value)
						{
							m_DebugBlitPass.showExtra = value;
						}
					} }
				});
			}
		}
		else if (m_DebugBlitPass.textureDebugMode >= DebugCustomPass.TextureDebugMode.WaterSurfaceSpectrum && m_DebugBlitPass.textureDebugMode <= DebugCustomPass.TextureDebugMode.WaterSurfaceCaustics)
		{
			m_DebugBlitPass.minValue = m_DebugBlitPass.GetDefaultMinValue();
			m_DebugBlitPass.maxValue = m_DebugBlitPass.GetDefaultMaxValue();
			list.Add(new DebugUI.Container
			{
				children = 
				{
					(DebugUI.Widget)new DebugUI.FloatField
					{
						displayName = "Min Range",
						getter = () => m_DebugBlitPass.minValue,
						setter = delegate(float value)
						{
							m_DebugBlitPass.minValue = value;
						},
						min = () => m_DebugBlitPass.GetMinValue(),
						max = () => m_DebugBlitPass.GetMaxValue(),
						incStep = 0.001f
					},
					(DebugUI.Widget)new DebugUI.FloatField
					{
						displayName = "Max Range",
						getter = () => m_DebugBlitPass.maxValue,
						setter = delegate(float value)
						{
							m_DebugBlitPass.maxValue = value;
						},
						min = () => m_DebugBlitPass.GetMinValue(),
						max = () => m_DebugBlitPass.GetMaxValue(),
						incStep = 0.001f
					}
				}
			});
		}
		list.AddRange(new List<DebugUI.Widget>
		{
			new DebugUI.Value
			{
				displayName = "Entity culling",
				getter = GetEntityCulling
			},
			new DebugUI.Value
			{
				displayName = "Effect culling",
				getter = GetEffectCulling
			},
			new DebugUI.Value
			{
				displayName = "Batch allocation",
				getter = GetBatchAllocation
			},
			new DebugUI.Value
			{
				displayName = "Batch upload",
				getter = GetBatchUpload
			},
			new DebugUI.Value
			{
				displayName = "Batch groups",
				getter = GetBatchGroups
			},
			new DebugUI.Value
			{
				displayName = "Batch renderers",
				getter = GetBatchRenderers
			},
			new DebugUI.Value
			{
				displayName = "Batch materials",
				getter = GetBatchMaterials
			},
			new DebugUI.Value
			{
				displayName = "Batch meshes",
				getter = GetBatchMeshes
			},
			new DebugUI.Value
			{
				displayName = "Area triangle buffer",
				getter = GetAreaBuffer
			},
			new DebugUI.Value
			{
				displayName = "Procedural skeleton buffer",
				getter = GetProceduralSkeletonBuffer
			},
			new DebugUI.Value
			{
				displayName = "Procedural skeleton upload",
				getter = GetProceduralSkeletonUpload
			},
			new DebugUI.Value
			{
				displayName = "Procedural emissive buffer",
				getter = GetProceduralEmissiveBuffer
			},
			new DebugUI.Value
			{
				displayName = "Procedural emissive upload",
				getter = GetProceduralEmissiveUpload
			},
			new DebugUI.Value
			{
				displayName = "Animation shape buffer",
				getter = GetShapeBuffer
			},
			new DebugUI.Value
			{
				displayName = "Animation bone buffer",
				getter = GetBoneBuffer
			},
			new DebugUI.Value
			{
				displayName = "Animation frame buffer",
				getter = GetAnimBuffer
			},
			new DebugUI.Value
			{
				displayName = "Animation index buffer",
				getter = GetIndexBuffer
			},
			new DebugUI.Value
			{
				displayName = "Animation meta buffer",
				getter = GetMetaBuffer
			},
			new DebugUI.FloatField
			{
				displayName = "Level of detail",
				getter = () => m_RenderingSystem.levelOfDetail,
				setter = delegate(float value)
				{
					if (m_RenderingSystem.levelOfDetail != value)
					{
						m_RenderingSystem.levelOfDetail = value;
					}
				},
				min = () => 0.01f,
				max = () => 1f,
				incStep = 0.01f
			},
			new DebugUI.BoolField
			{
				displayName = "Disable lod models",
				getter = () => m_RenderingSystem.disableLodModels,
				setter = delegate(bool value)
				{
					m_RenderingSystem.disableLodModels = value;
				}
			},
			new DebugUI.BoolField
			{
				displayName = "Disable mesh loading",
				getter = () => !m_BatchMeshSystem.enableMeshLoading,
				setter = delegate(bool value)
				{
					m_BatchMeshSystem.enableMeshLoading = !value;
				}
			},
			new DebugUI.BoolField
			{
				displayName = "Force mesh unloading",
				getter = () => m_BatchMeshSystem.forceMeshUnloading,
				setter = delegate(bool value)
				{
					m_BatchMeshSystem.forceMeshUnloading = value;
				}
			},
			new DebugUI.BoolField
			{
				displayName = "Strict mesh memory budget",
				getter = () => m_BatchMeshSystem.strictMemoryBudget,
				setter = delegate(bool value)
				{
					m_BatchMeshSystem.strictMemoryBudget = value;
				}
			},
			new DebugUI.BoolField
			{
				displayName = "Long cross fade",
				getter = () => m_RenderingSystem.debugCrossFade,
				setter = delegate(bool value)
				{
					m_RenderingSystem.debugCrossFade = value;
				}
			},
			foldout,
			foldout2
		});
		ObservableList<DebugUI.Widget> shaders = new ObservableList<DebugUI.Widget>();
		shaders.Add(new DebugUI.BoolField
		{
			displayName = "All",
			getter = delegate
			{
				if (m_RenderingSystem.enabledShaders.Count + 1 != shaders.Count)
				{
					Rebuild(BuildRenderingDebugUI);
				}
				foreach (KeyValuePair<Shader, bool> enabledShader in m_RenderingSystem.enabledShaders)
				{
					if (!enabledShader.Value)
					{
						return false;
					}
				}
				return true;
			},
			setter = delegate(bool value)
			{
				foreach (KeyValuePair<Shader, bool> item in new List<KeyValuePair<Shader, bool>>(m_RenderingSystem.enabledShaders))
				{
					if (item.Value != value)
					{
						m_RenderingSystem.SetShaderEnabled(item.Key, value);
					}
				}
			}
		});
		foreach (KeyValuePair<Shader, bool> enabledShader2 in m_RenderingSystem.enabledShaders)
		{
			Shader shader = enabledShader2.Key;
			shaders.Add(new DebugUI.BoolField
			{
				displayName = shader.name,
				getter = () => m_RenderingSystem.IsShaderEnabled(shader),
				setter = delegate(bool value)
				{
					m_RenderingSystem.SetShaderEnabled(shader, value);
				}
			});
		}
		list.Add(new DebugUI.Foldout("Shaders", shaders));
		AdaptiveDynamicResolutionScale adrs = AdaptiveDynamicResolutionScale.instance;
		list.Add(new DebugUI.BoolField
		{
			displayName = "Dynamic Resolution",
			getter = () => adrs.isEnabled,
			setter = delegate(bool value)
			{
				adrs.SetParams(value, adrs.isAdaptive, adrs.minScale, adrs.upscaleFilter, Camera.main);
			},
			onValueChanged = RebuildRenderingDebugUI<bool>
		});
		if (adrs.isEnabled)
		{
			list.Add(new DebugUI.Container
			{
				children = 
				{
					(DebugUI.Widget)new DebugUI.BoolField
					{
						displayName = "Auto Adaptive",
						getter = () => adrs.isAdaptive,
						setter = delegate(bool value)
						{
							adrs.SetParams(adrs.isEnabled, value, adrs.minScale, adrs.upscaleFilter, Camera.main);
						},
						onValueChanged = RebuildRenderingDebugUI<bool>
					},
					(DebugUI.Widget)new DebugUI.FloatField
					{
						displayName = (adrs.isAdaptive ? "Min Scale" : "Scale"),
						getter = () => adrs.minScale,
						setter = delegate(float value)
						{
							adrs.SetParams(adrs.isEnabled, adrs.isAdaptive, value, adrs.upscaleFilter, Camera.main);
						},
						min = () => 0.5f,
						max = () => 1f,
						incStep = 0.01f
					},
					(DebugUI.Widget)new DebugUI.EnumField
					{
						displayName = "Upscale Filter",
						getter = () => (int)adrs.upscaleFilter,
						setter = delegate(int value)
						{
							adrs.SetParams(adrs.isEnabled, adrs.isAdaptive, adrs.minScale, (AdaptiveDynamicResolutionScale.DynResUpscaleFilter)value, Camera.main);
						},
						autoEnum = typeof(AdaptiveDynamicResolutionScale.DynResUpscaleFilter),
						getIndex = () => (int)AdaptiveDynamicResolutionScale.instance.upscaleFilter,
						setIndex = delegate
						{
						}
					},
					(DebugUI.Widget)new DebugUI.Value
					{
						displayName = "Debug",
						getter = () => adrs.debugState
					}
				}
			});
		}
		list.Add(new DebugUI.BoolField
		{
			displayName = "Punctual Lights",
			getter = () => HDRPDotsInputs.PunctualLightsEnable,
			setter = delegate(bool value)
			{
				HDRPDotsInputs.PunctualLightsEnable = value;
			},
			onValueChanged = RebuildRenderingDebugUI<bool>
		});
		if (HDRPDotsInputs.PunctualLightsEnable)
		{
			list.Add(new DebugUI.BoolField
			{
				displayName = "Punctual Lights Cookies",
				getter = () => HDRPDotsInputs.PunctualLightsCookies,
				setter = delegate(bool value)
				{
					HDRPDotsInputs.PunctualLightsCookies = value;
				},
				onValueChanged = RebuildRenderingDebugUI<bool>
			});
			list.Add(new DebugUI.IntField
			{
				displayName = "Max Punctual Lights",
				getter = () => m_RenderingSystem.maxLightCount,
				setter = delegate(int value)
				{
					m_RenderingSystem.maxLightCount = value;
				},
				min = () => 512,
				max = () => 16384,
				incStep = 256,
				intStepMult = 16,
				onValueChanged = RebuildRenderingDebugUI<int>
			});
			list.Add(new DebugUI.BoolField
			{
				displayName = "Enable Min-Max light culling optim",
				getter = () => LightCullingSystem.s_enableMinMaxLightCullingOptim,
				setter = delegate(bool value)
				{
					LightCullingSystem.s_enableMinMaxLightCullingOptim = value;
				}
			});
			list.Add(new DebugUI.FloatField
			{
				displayName = "Max Distance Culling Scale",
				getter = () => LightCullingSystem.s_maxLightDistanceScale,
				setter = delegate(float value)
				{
					LightCullingSystem.s_maxLightDistanceScale = value;
				},
				min = () => 1f,
				max = () => 3f,
				incStep = 0.1f
			});
			list.Add(new DebugUI.FloatField
			{
				displayName = "Min Distance Culling Scale",
				getter = () => LightCullingSystem.s_minLightDistanceScale,
				setter = delegate(float value)
				{
					LightCullingSystem.s_minLightDistanceScale = value;
				},
				min = () => 0.1f,
				max = () => 0.9f,
				incStep = 0.1f
			});
		}
		list.Add(new DebugUI.Value
		{
			displayName = "Number of punctual lights",
			getter = () => HDRPDotsInputs.NumPunctualLights
		});
		return list;
		void RebuildRenderingDebugUI<TValue>(DebugUI.Field<TValue> field, TValue value)
		{
			Rebuild(BuildRenderingDebugUI);
		}
	}
```

- `private BuildSerializationDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private List<DebugUI.Widget> BuildSerializationDebugUI()
	{
		SerializerSystem serializerSystem = base.World.GetOrCreateSystemManaged<SerializerSystem>();
		List<DebugUI.Widget> list = new List<DebugUI.Widget>();
		if (serializerSystem.componentLibrary != null && serializerSystem.systemLibrary != null)
		{
			list.Add(new DebugUI.Value
			{
				displayName = "Uncompressed size (Overhead)",
				getter = () => GetItem(-1)
			});
			DebugUI.Table table = new DebugUI.Table
			{
				displayName = "Top 100 types",
				isReadOnly = true
			};
			for (int num = 0; num < 100; num++)
			{
				int index = num;
				table.children.Add(new DebugUI.Value
				{
					displayName = "#" + (num + 1),
					getter = () => GetItem(index)
				});
			}
			list.Add(table);
		}
		return list;
		object GetItem(int num4)
		{
			string text = null;
			int num2 = -1;
			int num3 = -1;
			if (num4 == -1)
			{
				ComponentSerializerLibrary componentLibrary = serializerSystem.componentLibrary;
				SystemSerializerLibrary systemLibrary = serializerSystem.systemLibrary;
				int serializerCount = componentLibrary.GetSerializerCount();
				int serializerCount2 = systemLibrary.GetSerializerCount();
				num2 = serializerSystem.totalSize;
				num3 = serializerSystem.totalSize;
				if (m_SerializationBuffer != null)
				{
					m_SerializationBuffer.Clear();
				}
				else
				{
					m_SerializationBuffer = new List<SerializationItem>(serializerCount + serializerCount2 + 1);
				}
				for (int i = 0; i < serializerCount; i++)
				{
					int overhead;
					int serializedSize = componentLibrary.GetSerializedSize(i, out overhead);
					m_SerializationBuffer.Add(new SerializationItem
					{
						m_Type = componentLibrary.GetSerializer(i).GetComponentType(),
						m_TotalSize = serializedSize + overhead,
						m_OverheadSize = overhead
					});
					num3 -= serializedSize;
				}
				for (int j = 0; j < serializerCount2; j++)
				{
					int overhead2;
					int serializedSize2 = systemLibrary.GetSerializedSize(j, out overhead2);
					m_SerializationBuffer.Add(new SerializationItem
					{
						m_Type = systemLibrary.GetSerializer(j).GetSystemType(),
						m_TotalSize = serializedSize2 + overhead2,
						m_OverheadSize = overhead2
					});
					num3 -= serializedSize2;
				}
				int obsoleteSerializedSize = componentLibrary.GetObsoleteSerializedSize(out var overhead3);
				obsoleteSerializedSize += systemLibrary.GetObsoleteSerializedSize(out var overhead4);
				m_SerializationBuffer.Add(new SerializationItem
				{
					m_Type = null,
					m_TotalSize = obsoleteSerializedSize + overhead3 + overhead4,
					m_OverheadSize = overhead3 + overhead4
				});
				num3 -= obsoleteSerializedSize;
				m_SerializationBuffer.Sort();
			}
			else if (m_SerializationBuffer != null && num4 < m_SerializationBuffer.Count)
			{
				SerializationItem serializationItem = m_SerializationBuffer[num4];
				text = ((!(serializationItem.m_Type == null)) ? serializationItem.m_Type.Name : "Unknown");
				num2 = serializationItem.m_TotalSize;
				num3 = serializationItem.m_OverheadSize;
			}
			if (num2 >= 0)
			{
				string text2 = ((num2 < 1024) ? (num2 + " B (") : ((num2 >= 1048576) ? ((num2 >> 20) + " MB (") : ((num2 >> 10) + " kB (")));
				text2 = ((num3 < 1024) ? (text2 + num3 + " B)") : ((num3 >= 1048576) ? (text2 + (num3 >> 20) + " MB)") : (text2 + (num3 >> 10) + " kB)")));
				if (text != null)
				{
					return text + "\t" + text2;
				}
				return text2;
			}
			return "-";
		}
	}
```

- `private BuildSimulationDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private List<DebugUI.Widget> BuildSimulationDebugUI()
	{
		if (GameManager.instance.gameMode.IsGameOrEditor())
		{
			string entitySearchQuery = string.Empty;
			AtmosphereData atmosphere = default(AtmosphereData);
			if (!m_AtmosphereQuery.IsEmptyIgnoreFilter)
			{
				atmosphere = m_AtmosphereQuery.GetSingleton<AtmosphereData>();
			}
			BiomeData biome = default(BiomeData);
			if (!m_BiomeQuery.IsEmptyIgnoreFilter)
			{
				biome = m_BiomeQuery.GetSingleton<BiomeData>();
			}
			PollutionParameterData pollution = default(PollutionParameterData);
			if (!m_PollutionParameterQuery.IsEmptyIgnoreFilter)
			{
				pollution = m_PollutionParameterQuery.GetSingleton<PollutionParameterData>();
			}
			Entity prefab;
			List<DebugUI.Widget> list = new List<DebugUI.Widget>
			{
				RadioSelection("Active tool", () => m_ToolSystem.activeTool, delegate(ToolBaseSystem value)
				{
					m_ToolSystem.activeTool = value;
				}, m_ToolSystemNames, m_ToolSystems, delegate
				{
					Rebuild(BuildSimulationDebugUI);
				}),
				CreateToolUI(),
				InfoviewUI(),
				new DebugUI.Button
				{
					displayName = "Save game",
					action = delegate
					{
						SaveGame();
					}
				},
				new DebugUI.Button
				{
					displayName = "Load game",
					action = delegate
					{
						LoadGame();
					}
				},
				RadioSelection("Sim speed", () => m_SimulationSystem.selectedSpeed, delegate(float value)
				{
					m_SimulationSystem.selectedSpeed = value;
				}, kDebugSimulationSpeedStrings, kDebugSimulationSpeedValues),
				new DebugUI.Value
				{
					displayName = "Smooth speed",
					getter = () => m_SimulationSystem.smoothSpeed
				},
				new DebugUI.FloatField
				{
					displayName = "Interpolation offset",
					getter = () => m_RenderingSystem.frameOffset,
					setter = delegate(float value)
					{
						if (m_RenderingSystem.frameOffset != value)
						{
							m_RenderingSystem.frameOffset = value;
						}
					},
					min = () => -1f,
					max = () => 1f,
					incStep = 0.01f
				},
				new DebugUI.Value
				{
					displayName = "Step Time (ms)",
					getter = () => m_SimulationSystem.frameDuration * 1000f
				},
				new DebugUI.BoolField
				{
					displayName = "Disable trips",
					getter = () => m_TripNeededSystem.debugDisableSpawning,
					setter = delegate(bool value)
					{
						m_TripNeededSystem.debugDisableSpawning = value;
					}
				},
				new DebugUI.BoolField
				{
					displayName = "Disable homeless",
					getter = () => m_HouseholdFindPropertySystem.debugDisableHomeless,
					setter = delegate(bool value)
					{
						RemoveAllHomeless();
						m_HouseholdFindPropertySystem.debugDisableHomeless = value;
					}
				},
				new DebugUI.BoolField
				{
					displayName = "Debug Lifepath Chirps ",
					getter = () => m_LifePathEventSystem.m_DebugLifePathChirps,
					setter = delegate(bool value)
					{
						m_LifePathEventSystem.m_DebugLifePathChirps = value;
					}
				},
				new DebugUI.Button
				{
					displayName = "Remove residents/vehicles",
					action = delegate
					{
						RemoveResidentsAndVehicles();
					}
				},
				new DebugUI.Button
				{
					displayName = "Cleanup obsolete entities",
					action = delegate
					{
						CleanupObsoleteEntities();
					}
				},
				new DebugUI.Foldout("Test Mode", new ObservableList<DebugUI.Widget>
				{
					new DebugUI.IntField
					{
						displayName = "Birth Chance",
						getter = () => m_BirthSystem.m_BirthChance,
						setter = delegate(int value)
						{
							m_BirthSystem.m_BirthChance = value;
						},
						min = () => 0,
						max = () => 1000
					},
					new DebugUI.IntField
					{
						displayName = "Speedup graduation",
						getter = () => m_GraduationSystem.debugFastGraduationLevel,
						setter = delegate(int value)
						{
							m_GraduationSystem.debugFastGraduationLevel = value;
						},
						min = () => 0,
						max = () => 4
					},
					ToggleSelection("Full Crime test mode", () => m_CrimeCheckSystem.debugFullCrimeMode, delegate(bool value)
					{
						m_CrimeCheckSystem.debugFullCrimeMode = value;
					}),
					ToggleSelection("Superfast building spawning", () => m_ZoneSpawnSystem.debugFastSpawn, delegate(bool value)
					{
						m_ZoneSpawnSystem.debugFastSpawn = value;
					}),
					ToggleSelection("Superfast area-prop spawning", () => m_AreaSpawnSystem.debugFastSpawn, delegate(bool value)
					{
						m_AreaSpawnSystem.debugFastSpawn = value;
					}),
					ToggleSelection("Superfast leveling", () => m_BuildingUpkeepSystem.debugFastLeveling, delegate(bool value)
					{
						m_BuildingUpkeepSystem.debugFastLeveling = value;
					}),
					ToggleSelection("Superfast enter school", () => m_ApplyToSchoolSystem.debugFastApplySchool && m_FindSchoolSystem.debugFastFindSchool, delegate(bool value)
					{
						m_ApplyToSchoolSystem.debugFastApplySchool = value;
						m_FindSchoolSystem.debugFastFindSchool = value;
					}),
					new DebugUI.Button
					{
						displayName = "Reset All Crime Accumulation to 0",
						action = delegate
						{
							ResetCrimeAccumulation();
						}
					}
				}),
				new DebugUI.Foldout("Diversity", new ObservableList<DebugUI.Widget>
				{
					new DebugUI.Value
					{
						displayName = "Atmosphere",
						getter = () => (!m_PrefabSystem.TryGetPrefab<PrefabBase>(atmosphere.m_AtmospherePrefab, out prefab)) ? "None" : prefab.name
					},
					new DebugUI.Value
					{
						displayName = "Biome",
						getter = () => (!m_PrefabSystem.TryGetPrefab<PrefabBase>(biome.m_BiomePrefab, out prefab)) ? "None" : prefab.name
					}
				}),
				new DebugUI.Foldout("Water", new ObservableList<DebugUI.Widget>
				{
					RadioSelection("Water sim speed", () => m_WaterSystem.WaterSimSpeed, delegate(int value)
					{
						m_WaterSystem.WaterSimSpeed = value;
					}, kDebugWaterSpeedStrings, GetWaterSpeedValues()),
					new DebugUI.Button
					{
						displayName = "Save water",
						action = delegate
						{
							m_WaterSystem.Save();
						}
					},
					new DebugUI.Button
					{
						displayName = "Load water",
						action = delegate
						{
							m_WaterSystem.JobLoad();
						}
					},
					new DebugUI.Button
					{
						displayName = "Restart water",
						action = delegate
						{
							m_WaterSystem.Restart();
						}
					},
					new DebugUI.Button
					{
						displayName = "Water to sealevel",
						action = delegate
						{
							m_WaterSystem.ResetToSealevel();
						}
					},
					new DebugUI.Button
					{
						displayName = "Reload Water Sources",
						action = delegate
						{
							ReloadWaterSources();
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Time step override",
						getter = () => m_WaterSystem.TimeStepOverride,
						setter = delegate(float value)
						{
							m_WaterSystem.TimeStepOverride = value;
						},
						min = () => 0f,
						max = () => 1f,
						incStep = 0.01f
					},
					new DebugUI.FloatField
					{
						displayName = "Current Time Step",
						getter = () => m_WaterSystem.GetTimeStep()
					},
					new DebugUI.FloatField
					{
						displayName = "Max Velocity",
						getter = () => m_WaterSystem.MaxVelocity,
						setter = delegate(float value)
						{
							m_WaterSystem.MaxVelocity = value;
						},
						min = () => 0f,
						max = () => 16f,
						incStep = 0.025f
					},
					new DebugUI.BoolField
					{
						displayName = "Use Active Cells Culling",
						getter = () => m_WaterSystem.UseActiveCellsCulling,
						setter = delegate(bool value)
						{
							m_WaterSystem.UseActiveCellsCulling = value;
						}
					},
					new DebugUI.IntField
					{
						displayName = "Water Grid Size Multiplier",
						getter = () => m_WaterSystem.GridSizeMultiplier,
						setter = delegate(int value)
						{
							m_WaterSystem.GridSizeMultiplier = value;
						},
						min = () => 0,
						max = () => 6
					},
					new DebugUI.Value
					{
						displayName = "Water grid size",
						getter = () => $"{m_WaterSystem.GridSize} {2048 / m_WaterSystem.GridSize}x{2048 / m_WaterSystem.GridSize}"
					},
					new DebugUI.IntField
					{
						displayName = "Flow number of Downscale",
						getter = () => m_WaterSystem.FlowMapNumDownscale,
						setter = delegate(int value)
						{
							m_WaterSystem.FlowMapNumDownscale = value;
						},
						min = () => 0,
						max = () => 3,
						onValueChanged = RebuildSimulationDebugUI
					},
					new DebugUI.BoolField
					{
						displayName = "Blur flow",
						getter = () => m_WaterSystem.BlurFlowMap,
						setter = delegate(bool value)
						{
							m_WaterSystem.BlurFlowMap = value;
						}
					},
					new DebugUI.BoolField
					{
						displayName = "Enable flow Downscale",
						getter = () => m_WaterSystem.EnableFlowDownscale,
						setter = delegate(bool value)
						{
							m_WaterSystem.EnableFlowDownscale = value;
						}
					},
					new DebugUI.BoolField
					{
						displayName = "Flow limiter for render",
						getter = () => m_WaterSystem.FlowPostProcess,
						setter = delegate(bool value)
						{
							m_WaterSystem.FlowPostProcess = value;
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Max Water Flow Length for render",
						getter = () => m_WaterSystem.MaxFlowlengthForRender,
						setter = delegate(float value)
						{
							m_WaterSystem.MaxFlowlengthForRender = value;
						},
						min = () => 0f,
						max = () => 5f,
						incStep = 0.1f
					},
					new DebugUI.FloatField
					{
						displayName = "Water Flow Render Multiplier",
						getter = () => m_WaterSystem.PostFlowspeedMultiplier,
						setter = delegate(float value)
						{
							m_WaterSystem.PostFlowspeedMultiplier = value;
						},
						min = () => 0f,
						max = () => 10f,
						incStep = 0.1f
					},
					new DebugUI.FloatField
					{
						displayName = "Water Pollution Decay Rate",
						getter = () => m_WaterSystem.m_PollutionDecayRate,
						setter = delegate(float value)
						{
							m_WaterSystem.m_PollutionDecayRate = value;
						},
						min = () => 0f,
						max = () => 0.1f,
						incStep = 1E-05f
					}
				}),
				new DebugUI.Foldout("Weather & climate", new ObservableList<DebugUI.Widget>
				{
					OverridableProperty("Climate time", () => m_ClimateSystem.currentDate),
					new DebugUI.Value
					{
						displayName = "Current climate",
						getter = () => (!(m_ClimateSystem.currentClimate != Entity.Null)) ? "None" : m_PrefabSystem.GetPrefab<PrefabBase>(m_ClimateSystem.currentClimate).name
					},
					new DebugUI.Value
					{
						displayName = "Current season",
						getter = () => (!(m_ClimateSystem.currentSeason != Entity.Null)) ? "None" : m_PrefabSystem.GetPrefab<PrefabBase>(m_ClimateSystem.currentSeason).name
					},
					new DebugUI.Foldout("Season stats", new ObservableList<DebugUI.Widget>
					{
						new DebugUI.Value
						{
							displayName = "Average temperature",
							getter = () => m_ClimateSystem.seasonTemperature
						},
						new DebugUI.Value
						{
							displayName = "Average precipitation",
							getter = () => m_ClimateSystem.seasonPrecipitation
						},
						new DebugUI.Value
						{
							displayName = "Average cloudiness",
							getter = () => m_ClimateSystem.seasonCloudiness
						}
					}),
					OverridableProperty("Temperature", () => m_ClimateSystem.temperature, -50f, 50f),
					new DebugUI.Foldout("Temperature stats", new ObservableList<DebugUI.Widget>
					{
						new DebugUI.Value
						{
							displayName = "Yearly average temperature",
							getter = () => m_ClimateSystem.averageTemperature
						},
						new DebugUI.Value
						{
							displayName = "Freezing temperature",
							getter = () => m_ClimateSystem.freezingTemperature
						},
						new DebugUI.Value
						{
							displayName = "Temperature base height",
							getter = () => m_ClimateSystem.temperatureBaseHeight
						}
					}),
					RadioSelection("Snow sim speed", () => m_SnowSystem.SnowSimSpeed, delegate(int value)
					{
						m_SnowSystem.SnowSimSpeed = value;
					}, kDebugWaterSpeedStrings, GetWaterSpeedValues()),
					OverridableProperty("Precipitation", () => m_ClimateSystem.precipitation),
					OverridableProperty("Cloudiness", () => m_ClimateSystem.cloudiness),
					OverridableProperty("Aurora", () => m_ClimateSystem.aurora),
					new DebugUI.Button
					{
						displayName = "Remove snow",
						action = delegate
						{
							base.World.GetOrCreateSystemManaged<SnowSystem>().DebugReset();
						}
					},
					new DebugUI.Button
					{
						displayName = "Save Wind",
						action = delegate
						{
							base.World.GetOrCreateSystemManaged<WindSimulationSystem>().DebugSave();
						}
					},
					new DebugUI.Button
					{
						displayName = "Load Wind",
						action = delegate
						{
							base.World.GetOrCreateSystemManaged<WindSimulationSystem>().DebugLoad();
						}
					},
					new DebugUI.Button
					{
						displayName = "Reset Wind",
						action = delegate
						{
							base.World.GetOrCreateSystemManaged<WindSimulationSystem>().SetDefaults(default(Context));
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Precipitation volume scale",
						getter = () => m_ClimateRenderSystem.precipitationVolumeScale,
						setter = delegate(float value)
						{
							m_ClimateRenderSystem.precipitationVolumeScale = value;
						},
						min = () => 5f,
						max = () => 300f,
						incStep = 0.1f
					},
					new DebugUI.BoolField
					{
						displayName = "Global VFX time from Simulation time",
						getter = () => m_ClimateRenderSystem.globalEffectTimeStepFromSimulation,
						setter = delegate(bool value)
						{
							m_ClimateRenderSystem.globalEffectTimeStepFromSimulation = value;
						}
					},
					new DebugUI.BoolField
					{
						displayName = "Weather VFX time from Simulation time",
						getter = () => m_ClimateRenderSystem.weatherEffectTimeStepFromSimulation,
						setter = delegate(bool value)
						{
							m_ClimateRenderSystem.weatherEffectTimeStepFromSimulation = value;
						}
					},
					new DebugUI.Value
					{
						displayName = "Temperature Electricity Consumption Multiplier",
						getter = () => m_AdjustElectricityConsumptionSystem.GetTemperatureMultiplier(m_ClimateSystem.temperature)
					}
				}),
				new DebugUI.Foldout("Time", new ObservableList<DebugUI.Widget>
				{
					new DebugUI.Value
					{
						displayName = "Time/Date",
						getter = () => EditorDate()
					},
					new DebugUI.FloatField
					{
						displayName = "Latitude",
						getter = () => m_PlanetarySystem.latitude,
						setter = delegate(float value)
						{
							m_PlanetarySystem.latitude = value;
						},
						min = () => -90f,
						max = () => 90f
					},
					new DebugUI.FloatField
					{
						displayName = "Longitude",
						getter = () => m_PlanetarySystem.longitude,
						setter = delegate(float value)
						{
							m_PlanetarySystem.longitude = value;
						},
						min = () => -180f,
						max = () => 180f
					},
					new DebugUI.FloatField
					{
						displayName = "Day of year",
						getter = () => m_PlanetarySystem.day,
						setter = delegate(float value)
						{
							m_PlanetarySystem.day = (int)value;
						},
						min = () => 1f,
						max = () => 365f
					},
					new DebugUI.FloatField
					{
						displayName = "Time of day",
						getter = () => m_PlanetarySystem.time,
						setter = delegate(float value)
						{
							m_PlanetarySystem.time = value;
						},
						min = () => 0f,
						max = () => 24f
					},
					new DebugUI.IntField
					{
						displayName = "Number of lunar cycles per year",
						getter = () => m_PlanetarySystem.numberOfLunarCyclesPerYear,
						setter = delegate(int value)
						{
							m_PlanetarySystem.numberOfLunarCyclesPerYear = value;
						},
						min = () => 0
					},
					new DebugUI.Value
					{
						displayName = "Day of year (Moon)",
						getter = () => m_PlanetarySystem.moonDay
					},
					new DebugUI.BoolField
					{
						displayName = "Override time for debug",
						getter = () => m_PlanetarySystem.overrideTime,
						setter = delegate(bool value)
						{
							m_PlanetarySystem.overrideTime = value;
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Time of day multiplier",
						getter = () => m_PlanetarySystem.debugTimeMultiplier,
						setter = delegate(float value)
						{
							m_PlanetarySystem.debugTimeMultiplier = value;
						},
						min = () => 0f,
						max = () => 100f
					},
					new DebugUI.Button
					{
						displayName = "Advance time 1h",
						action = delegate
						{
							m_TimeSystem.DebugAdvanceTime(60);
						}
					},
					new DebugUI.Button
					{
						displayName = "Advance time 12h",
						action = delegate
						{
							m_TimeSystem.DebugAdvanceTime(720);
						}
					},
					new DebugUI.Button
					{
						displayName = "Advance time 6d",
						action = delegate
						{
							m_TimeSystem.DebugAdvanceTime(8640);
						}
					}
				}),
				new DebugUI.Foldout("Economy", new ObservableList<DebugUI.Widget>
				{
					new DebugUI.Button
					{
						displayName = "Give max resource",
						action = delegate
						{
							GiveMaxResources();
						}
					},
					new DebugUI.Button
					{
						displayName = "Print age debug",
						action = delegate
						{
							EconomyDebugSystem.PrintAgeDebug();
						}
					},
					new DebugUI.Button
					{
						displayName = "Print school debug",
						action = delegate
						{
							EconomyDebugSystem.PrintSchoolDebug();
						}
					},
					new DebugUI.Button
					{
						displayName = "Print company debug",
						action = delegate
						{
							EconomyDebugSystem.PrintCompanyDebug(InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef));
						}
					},
					new DebugUI.Button
					{
						displayName = "Print trade debug",
						action = delegate
						{
							EconomyDebugSystem.PrintTradeDebug(base.World.GetOrCreateSystemManaged<TradeSystem>(), base.EntityManager.GetBuffer<CityModifier>(m_CitySystem.City, isReadOnly: true));
						}
					},
					new DebugUI.Button
					{
						displayName = "Remove extra companies",
						action = delegate
						{
							EconomyDebugSystem.RemoveExtraCompanies();
						}
					},
					new DebugUI.Button
					{
						displayName = "Print null households",
						action = delegate
						{
							PrintNullHouseholds();
						}
					},
					new DebugUI.Button
					{
						displayName = "Calc customers",
						action = delegate
						{
							CalculateCustomers();
						}
					},
					new DebugUI.Button
					{
						displayName = "Calc eligible",
						action = delegate
						{
							CalculateEligible();
						}
					},
					new DebugUI.Button
					{
						displayName = "Calc students from OC",
						action = delegate
						{
							CalculateStudentsFromOC();
						}
					},
					new DebugUI.Button
					{
						displayName = "Happiness factors",
						action = delegate
						{
							HappinessFactors();
						}
					},
					new DebugUI.Button
					{
						displayName = "Reset land value",
						action = delegate
						{
							ResetLandvalue();
						}
					},
					new DebugUI.Button
					{
						displayName = "Reset households wealth",
						action = delegate
						{
							ResetHouseholdsWealth();
						}
					},
					new DebugUI.Button
					{
						displayName = "Max households wealth",
						action = delegate
						{
							MaxHouseholdsWealth();
						}
					},
					new DebugUI.Button
					{
						displayName = "Reset company money",
						action = delegate
						{
							ResetCompanyMoney();
						}
					},
					new DebugUI.Button
					{
						displayName = "Reset rents",
						action = delegate
						{
							ResetRents();
						}
					},
					new DebugUI.Button
					{
						displayName = "Reset services",
						action = delegate
						{
							ResetServices();
						}
					},
					new DebugUI.Button
					{
						displayName = "Reset trade costs",
						action = delegate
						{
							ResetTradeCosts();
						}
					},
					new DebugUI.Button
					{
						displayName = "Reset transfers",
						action = delegate
						{
							ResetTransfers();
						}
					},
					new DebugUI.Button
					{
						displayName = "Reset trip neededs",
						action = delegate
						{
							ResetTripNeeded();
						}
					},
					new DebugUI.Button
					{
						displayName = "Reset storages",
						action = delegate
						{
							ResetStorages();
						}
					},
					new IntInputField
					{
						displayName = "Select entity",
						getter = () => entitySearchQuery,
						setter = delegate(string value)
						{
							entitySearchQuery = value;
						},
						onValueChanged = delegate(DebugUI.Field<string> field, string value)
						{
							SelectEntity(value);
						}
					},
					new DebugUI.Button
					{
						displayName = "Follow selected citizen",
						action = delegate
						{
							FollowSelectedCitizen();
						}
					},
					new DebugUI.Button
					{
						displayName = "Age selected citizen",
						action = delegate
						{
							AgeSelectedCitizen();
						}
					},
					new DebugUI.Button
					{
						displayName = "Trigger Test Life Event",
						action = delegate
						{
							TriggerTestLifeEvent();
						}
					},
					new DebugUI.Button
					{
						displayName = "Discard statistics",
						action = delegate
						{
							m_CityStatisticsSystem.DiscardStatistics();
						}
					},
					new DebugUI.Button
					{
						displayName = "Print commuter distribution",
						action = delegate
						{
							PrintCommuterDistribute();
						}
					}
				}),
				new DebugUI.Foldout("Electricty & Water", new ObservableList<DebugUI.Widget>
				{
					new DebugUI.Button
					{
						displayName = "Reset Electricity",
						action = delegate
						{
							m_ElectricityFlowSystem.Reset();
							m_ElectricityFlowSystem.Enabled = true;
						}
					},
					new DebugUI.BoolField
					{
						displayName = "Water Pipe Fluid Flow",
						getter = () => m_WaterPipeFlowSystem.fluidFlowEnabled,
						setter = delegate(bool value)
						{
							m_WaterPipeFlowSystem.fluidFlowEnabled = value;
						}
					},
					new DebugUI.BoolField
					{
						displayName = "Disable Water consumption",
						getter = () => m_DispatchWaterSystem.freshConsumptionDisabled,
						setter = delegate(bool value)
						{
							m_DispatchWaterSystem.freshConsumptionDisabled = value;
						}
					},
					new DebugUI.BoolField
					{
						displayName = "Disable Sewage generation",
						getter = () => m_DispatchWaterSystem.sewageConsumptionDisabled,
						setter = delegate(bool value)
						{
							m_DispatchWaterSystem.sewageConsumptionDisabled = value;
						}
					}
				}),
				new DebugUI.Foldout("Pollution", new ObservableList<DebugUI.Widget>
				{
					new DebugUI.Button
					{
						displayName = "Full selected buidling with garbage",
						action = delegate
						{
							FullWithGarbage();
						}
					},
					new DebugUI.Button
					{
						displayName = "Reset pollution",
						action = delegate
						{
							ResetPollution();
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Ground Multiplier",
						incStep = 5f,
						getter = () => pollution.m_GroundMultiplier,
						setter = delegate(float value)
						{
							pollution.m_GroundMultiplier = value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Air Multiplier",
						incStep = 25f,
						getter = () => pollution.m_AirMultiplier,
						setter = delegate(float value)
						{
							pollution.m_AirMultiplier = value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Noise Multiplier",
						incStep = 50f,
						getter = () => pollution.m_NoiseMultiplier,
						setter = delegate(float value)
						{
							pollution.m_NoiseMultiplier = value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Net Noise Multiplier",
						incStep = 1f,
						getter = () => pollution.m_NetNoiseMultiplier,
						setter = delegate(float value)
						{
							pollution.m_NetNoiseMultiplier = value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Net Air Multiplier",
						incStep = 1f,
						getter = () => pollution.m_NetAirMultiplier,
						setter = delegate(float value)
						{
							pollution.m_NetAirMultiplier = value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Ground Radius",
						incStep = 5f,
						getter = () => pollution.m_GroundRadius,
						setter = delegate(float value)
						{
							pollution.m_GroundRadius = value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Air Radius",
						incStep = 5f,
						getter = () => pollution.m_AirRadius,
						setter = delegate(float value)
						{
							pollution.m_AirRadius = value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Noise Radius",
						incStep = 50f,
						getter = () => pollution.m_NoiseRadius,
						setter = delegate(float value)
						{
							pollution.m_NoiseRadius = value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Net Noise Radius",
						incStep = 5f,
						getter = () => pollution.m_NetNoiseRadius,
						setter = delegate(float value)
						{
							pollution.m_NetNoiseRadius = value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Wind Advection Speed",
						incStep = 5f,
						getter = () => pollution.m_WindAdvectionSpeed,
						setter = delegate(float value)
						{
							pollution.m_WindAdvectionSpeed = value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.IntField
					{
						displayName = "Air Fade",
						incStep = 1,
						getter = () => pollution.m_AirFade,
						setter = delegate(int value)
						{
							pollution.m_AirFade = (short)value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.IntField
					{
						displayName = "Ground Fade",
						incStep = 50,
						getter = () => pollution.m_GroundFade,
						setter = delegate(int value)
						{
							pollution.m_GroundFade = (short)value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Plant Air Multiplier",
						getter = () => pollution.m_PlantAirMultiplier,
						setter = delegate(float value)
						{
							pollution.m_PlantAirMultiplier = (short)value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Plant Ground Multiplier",
						getter = () => pollution.m_PlantGroundMultiplier,
						setter = delegate(float value)
						{
							pollution.m_PlantGroundMultiplier = (short)value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Plant Fade",
						incStep = 1f,
						getter = () => pollution.m_PlantFade,
						setter = delegate(float value)
						{
							pollution.m_PlantFade = (short)value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Fertility Ground Multiplier",
						incStep = 1f,
						getter = () => pollution.m_FertilityGroundMultiplier,
						setter = delegate(float value)
						{
							pollution.m_FertilityGroundMultiplier = (short)value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					},
					new DebugUI.FloatField
					{
						displayName = "Distance Expotent",
						incStep = 1f,
						getter = () => pollution.m_DistanceExponent,
						setter = delegate(float value)
						{
							pollution.m_DistanceExponent = (short)value;
							base.EntityManager.SetComponentData(m_PollutionParameterQuery.GetSingletonEntity(), pollution);
						}
					}
				}),
				CreateEventUI(),
				new DebugUI.Foldout("Terrain", new ObservableList<DebugUI.Widget>
				{
					new DebugUI.Button
					{
						displayName = "Export heightmap",
						action = ExportHeightMap
					}
				}),
				new DebugUI.Foldout("Triggers", new ObservableList<DebugUI.Widget>
				{
					new DebugUI.Button
					{
						displayName = "Create Chirps",
						action = delegate
						{
							NativeQueue<TriggerAction> nativeQueue = base.World.GetExistingSystemManaged<TriggerSystem>().CreateActionBuffer();
							nativeQueue.Enqueue(new TriggerAction(TriggerType.NoOutsideConnection, Entity.Null, 0f));
							nativeQueue.Enqueue(new TriggerAction(TriggerType.UnpaidLoan, Entity.Null, 999f));
						}
					}
				}),
				new DebugUI.Foldout("Cleanup", new ObservableList<DebugUI.Widget>
				{
					new DebugUI.Button
					{
						displayName = "Remove All TouristHousehold",
						action = delegate
						{
							RemoveAllTourist();
						}
					},
					new DebugUI.Button
					{
						displayName = "Remove All HomelessHousehold",
						action = delegate
						{
							RemoveAllHomeless();
						}
					},
					new DebugUI.Button
					{
						displayName = "Reset Commercial Storage",
						action = delegate
						{
							ResetCommercialStorage();
						}
					}
				}),
				new DebugUI.Foldout("Error Check", new ObservableList<DebugUI.Widget>
				{
					new DebugUI.Button
					{
						displayName = "Check property rent errors",
						action = delegate
						{
							NativeArray<Entity> nativeArray = GetEntityQuery(ComponentType.ReadOnly<PropertyRenter>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>()).ToEntityArray(Allocator.Temp);
							Dictionary<int, Entity> dictionary = new Dictionary<int, Entity>();
							for (int i = 0; i < nativeArray.Length; i++)
							{
								PropertyRenter componentData = base.EntityManager.GetComponentData<PropertyRenter>(nativeArray[i]);
								if (base.EntityManager.TryGetBuffer(componentData.m_Property, isReadOnly: true, out DynamicBuffer<Renter> buffer))
								{
									bool flag = false;
									for (int j = 0; j < buffer.Length; j++)
									{
										if (buffer[j].m_Renter.Index == nativeArray[i].Index)
										{
											flag = true;
										}
									}
									if (!flag)
									{
										UnityEngine.Debug.LogWarning($"Found invalid renter :{nativeArray[i].Index} of building:{componentData.m_Property.Index}");
									}
								}
								if (!base.EntityManager.HasComponent<Household>(nativeArray[i]))
								{
									if (dictionary.ContainsKey(componentData.m_Property.Index))
									{
										UnityEngine.Debug.LogWarning($"duplicate property:{componentData.m_Property.Index} found, renter:{nativeArray[i].Index} & {dictionary[componentData.m_Property.Index].Index}");
									}
									else
									{
										dictionary[componentData.m_Property.Index] = nativeArray[i];
									}
								}
							}
							nativeArray.Dispose();
						}
					},
					new DebugUI.Button
					{
						displayName = "Force Send Renter Update Event",
						action = delegate
						{
							NativeArray<Entity> nativeArray = GetEntityQuery(ComponentType.ReadOnly<Renter>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>()).ToEntityArray(Allocator.Temp);
							EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
							for (int i = 0; i < nativeArray.Length; i++)
							{
								EntityArchetype archetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<RentersUpdated>());
								Entity e = entityCommandBuffer.CreateEntity(archetype);
								entityCommandBuffer.SetComponent(e, new RentersUpdated(nativeArray[i]));
							}
							nativeArray.Dispose();
						}
					},
					new DebugUI.Button
					{
						displayName = "Fix property rent errors",
						action = delegate
						{
							NativeArray<Entity> nativeArray = GetEntityQuery(ComponentType.ReadOnly<PropertyRenter>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>()).ToEntityArray(Allocator.Temp);
							List<Entity> list2 = new List<Entity>();
							EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
							for (int i = 0; i < nativeArray.Length; i++)
							{
								PropertyRenter componentData = base.EntityManager.GetComponentData<PropertyRenter>(nativeArray[i]);
								if (!list2.Contains(componentData.m_Property) && base.EntityManager.TryGetBuffer(componentData.m_Property, isReadOnly: false, out DynamicBuffer<Renter> buffer))
								{
									bool flag = false;
									for (int j = 0; j < buffer.Length; j++)
									{
										if (buffer[j].m_Renter.Index == nativeArray[i].Index)
										{
											flag = true;
										}
									}
									if (!flag)
									{
										UnityEngine.Debug.LogWarning($"destroy invalid renter :{nativeArray[i].Index} of building:{componentData.m_Property.Index}");
										list2.Add(componentData.m_Property);
										entityCommandBuffer.AddComponent<Deleted>(nativeArray[i]);
									}
									if (!base.EntityManager.HasComponent<ResidentialProperty>(componentData.m_Property) && !base.EntityManager.HasComponent<Game.Buildings.Park>(componentData.m_Property) && buffer.Length > 1)
									{
										UnityEngine.Debug.LogWarning($"destroy one of the two company renter :{buffer[buffer.Length - 1].m_Renter.Index} of building:{componentData.m_Property.Index}");
										list2.Add(componentData.m_Property);
										entityCommandBuffer.AddComponent<Deleted>(buffer[buffer.Length - 1].m_Renter);
										buffer.RemoveAt(buffer.Length - 1);
									}
								}
							}
							nativeArray.Dispose();
						}
					},
					new DebugUI.Button
					{
						displayName = "Fix invalid Enabled Effects",
						action = delegate
						{
							NativeArray<Entity> nativeArray = GetEntityQuery(ComponentType.ReadOnly<EnabledEffect>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>()).ToEntityArray(Allocator.Temp);
							EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
							for (int i = 0; i < nativeArray.Length; i++)
							{
								prefab = base.EntityManager.GetComponentData<PrefabRef>(nativeArray[i]).m_Prefab;
								DynamicBuffer<EnabledEffect> buffer = base.EntityManager.GetBuffer<EnabledEffect>(nativeArray[i]);
								if (buffer.Length != 0)
								{
									if (!base.EntityManager.HasBuffer<Effect>(prefab))
									{
										UnityEngine.Debug.LogWarning($"Entity without effect but have EnabledEffect, entity:{nativeArray[i].Index}");
									}
									else
									{
										DynamicBuffer<Effect> buffer2 = base.EntityManager.GetBuffer<Effect>(prefab);
										for (int j = 0; j < buffer.Length; j++)
										{
											if (buffer[j].m_EffectIndex >= buffer2.Length)
											{
												UnityEngine.Debug.LogWarning($"destroyed building with invalid effect, building:{nativeArray[i].Index}");
												entityCommandBuffer.AddComponent<Deleted>(nativeArray[i]);
												break;
											}
										}
									}
								}
							}
							nativeArray.Dispose();
						}
					}
				})
			};
			if (GameManager.instance.gameMode.IsEditor())
			{
				list.Add(new DebugUI.Container("Objects lighting state", new ObservableList<DebugUI.Widget>
				{
					new DebugUI.FloatField
					{
						displayName = "X",
						getter = () => m_RenderingSystem.editorBuildingStateOverride.x,
						setter = delegate(float value)
						{
							float4 editorBuildingStateOverride = m_RenderingSystem.editorBuildingStateOverride;
							editorBuildingStateOverride.x = value;
							m_RenderingSystem.editorBuildingStateOverride = editorBuildingStateOverride;
						},
						min = () => 0f,
						max = () => 1f
					},
					new DebugUI.FloatField
					{
						displayName = "Y",
						getter = () => m_RenderingSystem.editorBuildingStateOverride.x,
						setter = delegate(float value)
						{
							float4 editorBuildingStateOverride = m_RenderingSystem.editorBuildingStateOverride;
							editorBuildingStateOverride.y = value;
							m_RenderingSystem.editorBuildingStateOverride = editorBuildingStateOverride;
						},
						min = () => 0f,
						max = () => 1f
					}
				}));
				list.Add(new DebugUI.BoolField
				{
					displayName = "Bypass editor value limits",
					getter = () => EditorGenerator.sBypassValueLimits,
					setter = delegate(bool value)
					{
						EditorGenerator.sBypassValueLimits = value;
					}
				});
			}
			return list;
		}
		return null;
	}
```

- `private static BuildVirtualTexturingDebugUI(Unity.Entities.World world) : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private static List<DebugUI.Widget> BuildVirtualTexturingDebugUI(World world)
	{
		TextureStreamingSystem tss = world.GetExistingSystemManaged<TextureStreamingSystem>();
		ManagedBatchSystem mbs = world.GetExistingSystemManaged<ManagedBatchSystem>();
		int num = tss.tileSize + 16;
		long tileSizeInBytes = num * num;
		tileSizeInBytes += tileSizeInBytes / 4;
		DebugUI.Foldout foldout = new DebugUI.Foldout
		{
			displayName = "Memory"
		};
		foldout.children.Add(new DebugUI.Value
		{
			displayName = "Atlas CPU Cache Size",
			getter = () => FormatUtils.FormatBytes(tss.atlasDataSize)
		});
		foldout.children.Add(new DebugUI.Value
		{
			displayName = "Data Size",
			getter = () => FormatUtils.FormatBytes(tss.dataSize)
		});
		DebugUI.Foldout foldout2 = new DebugUI.Foldout
		{
			displayName = "Atlas"
		};
		foldout2.children.Add(new DebugUI.Value
		{
			displayName = "Atlas Blocks Stack 0",
			getter = delegate
			{
				int totalNbBlocks = tss.GetTotalNbBlocks(0);
				int nbReservedBlocks = tss.GetNbReservedBlocks(0);
				float num2 = (float)nbReservedBlocks * 100f / (float)totalNbBlocks;
				return nbReservedBlocks + " / " + totalNbBlocks + " (" + num2 + " %)";
			}
		});
		foldout2.children.Add(new DebugUI.Value
		{
			displayName = "Atlas Blocks Stack 1",
			getter = delegate
			{
				int totalNbBlocks = tss.GetTotalNbBlocks(1);
				int nbReservedBlocks = tss.GetNbReservedBlocks(1);
				float num2 = (float)nbReservedBlocks * 100f / (float)totalNbBlocks;
				return nbReservedBlocks + " / " + totalNbBlocks + " (" + num2 + " %)";
			}
		});
		DebugUI.Foldout foldout3 = new DebugUI.Foldout
		{
			displayName = "Material Loading"
		};
		foldout3.children.Add(new DebugUI.Value
		{
			displayName = "Nb VT Material Assets",
			getter = () => tss.VTMaterialsCountAssetsCount
		});
		foldout3.children.Add(new DebugUI.Value
		{
			displayName = "Nb VT Material Duplicates",
			getter = () => tss.VTMaterialsAssetsDuplicatesCount
		});
		foldout3.children.Add(new DebugUI.Value
		{
			displayName = "Nb VT Materials Left To Load",
			getter = () => tss.VTMaterialsLeftToLoadCount
		});
		foldout3.children.Add(new DebugUI.Value
		{
			displayName = "Nb VT Materials Loaded per Frame (config)",
			getter = () => tss.virtualTexturingConfig.nbVTMaterialsToStartAsyncLoadingPerFrame
		});
		foldout3.children.Add(new DebugUI.Value
		{
			displayName = "Load progression",
			getter = () => tss.VTMaterialAssetsProgression * 100f + " %"
		});
		foldout3.children.Add(new DebugUI.Value
		{
			displayName = "Nb VT Materials Duplicates To Init",
			getter = () => tss.VTMaterialsDuplicatesToProcessCount
		});
		foldout3.children.Add(new DebugUI.Value
		{
			displayName = "Nb VT Materials Duplicates Inited per Frame (config)",
			getter = () => tss.virtualTexturingConfig.nbVTMaterialsToStartAsyncDuplicateInitPerFrame
		});
		foldout3.children.Add(new DebugUI.Value
		{
			displayName = "Duplicate progression",
			getter = () => tss.VTMaterialDuplicatesProgression * 100f + " %"
		});
		DebugUI.Foldout foldout4 = new DebugUI.Foldout
		{
			displayName = "Tile Loading Stats"
		};
		foldout4.children.Add(new DebugUI.Value
		{
			displayName = "Nb High Mip CPU Cache Tiles",
			getter = delegate
			{
				long b = tss.tilesFilledFromCPUCacheCount * tileSizeInBytes;
				return tss.tilesFilledFromCPUCacheCount + "(" + FormatUtils.FormatBytes(b) + ")";
			}
		});
		foldout4.children.Add(new DebugUI.Value
		{
			displayName = "Nb Per Surface Async Tile Read",
			getter = delegate
			{
				long b = tss.perSurfaceAsyncTileReadCount * tileSizeInBytes;
				return tss.perSurfaceAsyncTileReadCount + " (" + FormatUtils.FormatBytes(b) + ")";
			}
		});
		foldout4.children.Add(new DebugUI.Value
		{
			displayName = "Nb Per Texture Async Tile Read",
			getter = delegate
			{
				long b = tss.perTextureAsyncTileReadCount * tileSizeInBytes;
				return tss.perTextureAsyncTileReadCount + " (" + FormatUtils.FormatBytes(b) + ")";
			}
		});
		foldout4.children.Add(new DebugUI.Value
		{
			displayName = "Nb Mid Mip Async Tile Read",
			getter = delegate
			{
				long b = tss.midMipAsyncTextureReadCount * tileSizeInBytes;
				return tss.midMipAsyncTextureReadCount + " (" + FormatUtils.FormatBytes(b) + ")";
			}
		});
		DebugUI.Foldout foldout5 = new DebugUI.Foldout
		{
			displayName = "Textures Requester"
		};
		foldout5.children.Add(new DebugUI.Value
		{
			displayName = "Stack count",
			getter = () => mbs.VTTextureRequester.stacksCount
		});
		foldout5.children.Add(new DebugUI.Value
		{
			displayName = "Registered count",
			getter = () => mbs.VTTextureRequester.registeredCount
		});
		foldout5.children.Add(new DebugUI.Value
		{
			displayName = "Requested this frame",
			getter = () => mbs.VTTextureRequester.requestCount
		});
		return new List<DebugUI.Widget>
		{
			new DebugUI.Value
			{
				displayName = "Mip Bias",
				getter = () => tss.mipBias
			},
			new DebugUI.Value
			{
				displayName = "Tile Size",
				getter = () => tss.tileSize
			},
			new DebugUI.Value
			{
				displayName = "Working Set Bias",
				getter = () => tss.workingSetLodBias,
				formatString = "{0:F1}"
			},
			new DebugUI.Value
			{
				displayName = "Nd Mid Mip Levels",
				getter = () => tss.midMipLevelsCount
			},
			new DebugUI.Value
			{
				displayName = "Nb BC7 SRGB Entries",
				getter = () => tss.bc7SrgbEntriesCount
			},
			new DebugUI.Value
			{
				displayName = "Nb BC7 UNorm Entries",
				getter = () => tss.bc7UNormEntriesCount
			},
			new DebugUI.Value
			{
				displayName = "Nb other Entries",
				getter = () => tss.otherEntriesCount
			},
			new DebugUI.Value
			{
				displayName = "Nb requests busy/available",
				getter = () => tss.busyRequestsCount + "/" + tss.availableRequestsCount
			},
			foldout3,
			foldout,
			foldout2,
			foldout4,
			foldout5,
			new DebugUI.Button
			{
				displayName = "Reload",
				action = delegate
				{
					(World.DefaultGameObjectInjectionWorld?.GetExistingSystemManaged<ManagedBatchSystem>())?.ReloadVT();
				}
			}
		};
	}
```

- `private BulldozeToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private void BulldozeToolSystemUI(DebugUI.Container container)
	{
		BulldozeToolSystem bts = GetTool<BulldozeToolSystem>();
		container.children.Add(new DebugUI.BoolField
		{
			displayName = "Allow gameplay manipulation",
			getter = () => bts.allowManipulation,
			setter = delegate(bool value)
			{
				bts.allowManipulation = value;
			}
		});
		container.children.Add(new DebugUI.BoolField
		{
			displayName = "Bypass confirmation",
			getter = () => bts.debugBypassBulldozeConfirmation,
			setter = delegate(bool value)
			{
				bts.debugBypassBulldozeConfirmation = value;
			}
		});
	}
```

- `private CacheGameRenderingDebugUISystems() : System.Void`  

```csharp
private void CacheGameRenderingDebugUISystems()
	{
		m_PreCullingSystem = base.World.GetOrCreateSystemManaged<PreCullingSystem>();
		m_EffectControlSystem = base.World.GetOrCreateSystemManaged<EffectControlSystem>();
		m_ProceduralSkeletonSystem = base.World.GetOrCreateSystemManaged<ProceduralSkeletonSystem>();
		m_ProceduralEmissiveSystem = base.World.GetOrCreateSystemManaged<ProceduralEmissiveSystem>();
		m_BatchManagerSystem = base.World.GetOrCreateSystemManaged<BatchManagerSystem>();
		m_AreaBatchSystem = base.World.GetOrCreateSystemManaged<AreaBatchSystem>();
		m_BatchMeshSystem = base.World.GetOrCreateSystemManaged<BatchMeshSystem>();
		m_AnimatedSystem = base.World.GetOrCreateSystemManaged<AnimatedSystem>();
		m_ManagedBatchSystem = base.World.GetOrCreateSystemManaged<ManagedBatchSystem>();
		m_VegetationRenderSystem = base.World.GetOrCreateSystemManaged<VegetationRenderSystem>();
		m_TerrainMaterialSystem = base.World.GetOrCreateSystemManaged<TerrainMaterialSystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
	}
```

- `private CalculateCustomers() : System.Void`  

```csharp
private void CalculateCustomers()
	{
		EntityManager entityManager = base.World.EntityManager;
		ILog logger = LogManager.GetLogger("customers");
		NativeArray<Entity> nativeArray = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<ServiceAvailable>(), ComponentType.ReadOnly<PropertyRenter>()).ToEntityArray(Allocator.Temp);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity entity = nativeArray[i];
			Entity prefab = entityManager.GetComponentData<PrefabRef>(entity).m_Prefab;
			Entity property = entityManager.GetComponentData<PropertyRenter>(entity).m_Property;
			entityManager.GetComponentData<PrefabRef>(property);
			Building componentData = entityManager.GetComponentData<Building>(property);
			DynamicBuffer<ResourceAvailability> buffer = entityManager.GetBuffer<ResourceAvailability>(componentData.m_RoadEdge, isReadOnly: true);
			ServiceAvailable componentData2 = entityManager.GetComponentData<ServiceAvailable>(entity);
			ServiceCompanyData componentData3 = entityManager.GetComponentData<ServiceCompanyData>(prefab);
			float num = 1f / NetUtils.GetAvailability(buffer, AvailableResource.Workplaces, componentData.m_CurvePosition);
			float num2 = 1f / NetUtils.GetAvailability(buffer, AvailableResource.EducatedCitizens, componentData.m_CurvePosition);
			float num3 = 1f / NetUtils.GetAvailability(buffer, AvailableResource.UneducatedCitizens, componentData.m_CurvePosition);
			float num4 = 1f / NetUtils.GetAvailability(buffer, AvailableResource.Services, componentData.m_CurvePosition);
			float num5 = 1f / NetUtils.GetAvailability(buffer, AvailableResource.Attractiveness, componentData.m_CurvePosition);
			float num6 = math.saturate(1f - (float)componentData2.m_ServiceAvailable / (float)componentData3.m_MaxService);
			logger.InfoFormat("{0},{1},{2},{3},{4},{5}", num6, num, num2, num3, num4, num5);
		}
		UnityEngine.Debug.Log("Done");
	}
```

- `private CalculateEligible() : System.Void`  

```csharp
private void CalculateEligible()
	{
		EntityQuery entityQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<Household>(), ComponentType.ReadOnly<PropertyRenter>(), ComponentType.ReadOnly<HouseholdCitizen>(), ComponentType.Exclude<TouristHousehold>(), ComponentType.Exclude<CommuterHousehold>(), ComponentType.Exclude<MovingAway>());
		EntityQuery entityQuery2 = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		EntityQuery entityQuery3 = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		EntityQuery entityQuery4 = GetEntityQuery(ComponentType.ReadOnly<EducationParameterData>());
		TimeData singleton = entityQuery2.GetSingleton<TimeData>();
		EconomyParameterData economyParameters = entityQuery3.GetSingleton<EconomyParameterData>();
		EducationParameterData educationParameterData = entityQuery4.GetSingleton<EducationParameterData>();
		NativeArray<Entity> nativeArray = entityQuery.ToEntityArray(Allocator.Temp);
		ComponentLookup<HealthProblem> healthProblems = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<Game.Citizens.Student> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<Citizen> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<Worker> componentLookup3 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentLookup, ref base.CheckedStateRef);
		BufferLookup<ServiceFee> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_ServiceFee_RO_BufferLookup, ref base.CheckedStateRef);
		BufferLookup<CityModifier> bufferLookup2 = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef);
		Entity city = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<CitySystem>().City;
		uint frameIndex = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<SimulationSystem>().frameIndex;
		DynamicBuffer<ServiceFee> fees = bufferLookup[city];
		DynamicBuffer<CityModifier> dynamicBuffer = bufferLookup2[city];
		float num = 0f;
		float num2 = 0f;
		float num3 = 0f;
		float num4 = 0f;
		float num5 = 0f;
		float num6 = 0f;
		float num7 = 0f;
		float num8 = 0f;
		float num9 = 0f;
		float num10 = 0f;
		float num11 = 0f;
		float num12 = 0f;
		float num13 = 0f;
		float num14 = 0f;
		float num15 = 0f;
		float num16 = 0f;
		float num17 = 0f;
		float num18 = 0f;
		float num19 = 0f;
		float num20 = 0f;
		float num21 = 0f;
		float num22 = 0f;
		float num23 = 0f;
		for (int i = 0; i < nativeArray.Length; i++)
		{
			DynamicBuffer<HouseholdCitizen> buffer = base.EntityManager.GetBuffer<HouseholdCitizen>(nativeArray[i], isReadOnly: true);
			for (int j = 0; j < buffer.Length; j++)
			{
				Entity citizen = buffer[j].m_Citizen;
				if (CitizenUtils.IsDead(citizen, ref healthProblems))
				{
					continue;
				}
				Citizen citizen2 = componentLookup2[citizen];
				CitizenAge age = citizen2.GetAge();
				if (componentLookup.HasComponent(citizen))
				{
					switch (componentLookup[citizen].m_Level)
					{
					case 1:
						num8 += 1f;
						num += 1f;
						break;
					case 2:
						num9 += 1f;
						num2 += 1f;
						break;
					case 3:
						num10 += 1f;
						num3 += 1f;
						break;
					case 4:
						num11 += 1f;
						num4 += 1f;
						break;
					}
					continue;
				}
				if (age == CitizenAge.Child)
				{
					num += 1f;
					num5 += 1f;
					continue;
				}
				bool flag = componentLookup3.HasComponent(citizen);
				if (citizen2.GetFailedEducationCount() >= 3)
				{
					continue;
				}
				SchoolData schoolData = default(SchoolData);
				float num24 = citizen2.GetPseudoRandom(CitizenPseudoRandom.StudyWillingness).NextFloat();
				switch (citizen2.GetEducationLevel())
				{
				case 1:
				{
					float fee = ServiceFeeSystem.GetFee(PlayerResource.SecondaryEducation, fees);
					float enteringProbability = ApplyToSchoolSystem.GetEnteringProbability(age, flag, 2, citizen2.m_WellBeing, num24, dynamicBuffer, ref educationParameterData);
					float dropoutProbability = GraduationSystem.GetDropoutProbability(citizen2, 2, 500f, fee, 0, frameIndex, ref economyParameters, schoolData, dynamicBuffer, 1f, singleton);
					num2 += enteringProbability * (1f - dropoutProbability);
					num15 += dropoutProbability;
					num12 += enteringProbability;
					num6 += 1f;
					break;
				}
				case 2:
				{
					float fee = ServiceFeeSystem.GetFee(PlayerResource.HigherEducation, fees);
					float enteringProbability = ApplyToSchoolSystem.GetEnteringProbability(age, flag, 4, citizen2.m_WellBeing, num24, dynamicBuffer, ref educationParameterData);
					float dropoutProbability = GraduationSystem.GetDropoutProbability(citizen2, 4, 500f, fee, 0, frameIndex, ref economyParameters, schoolData, dynamicBuffer, 1f, singleton);
					num4 += enteringProbability * dropoutProbability;
					num17 += dropoutProbability;
					num14 += enteringProbability;
					enteringProbability = ApplyToSchoolSystem.GetEnteringProbability(age, flag, 3, citizen2.m_WellBeing, num24, dynamicBuffer, ref educationParameterData);
					dropoutProbability = GraduationSystem.GetDropoutProbability(citizen2, 3, 500f, fee, 0, frameIndex, ref economyParameters, schoolData, dynamicBuffer, 1f, singleton);
					num3 += enteringProbability * (1f - dropoutProbability);
					num16 += dropoutProbability;
					num13 += enteringProbability;
					num7 += 1f;
					switch (age)
					{
					case CitizenAge.Teen:
						num20 += 1f;
						break;
					case CitizenAge.Adult:
						num21 += 1f;
						break;
					default:
						num23 += 1f;
						break;
					}
					if (flag)
					{
						num22 += 1f;
					}
					num19 += (float)(int)citizen2.m_WellBeing;
					num18 += num24;
					break;
				}
				}
			}
		}
		num6 = math.max(num6, 0.1f);
		num7 = math.max(num7, 0.1f);
		UnityEngine.Debug.Log($"Elementary: eligible {num} students {num8} total {num5}");
		UnityEngine.Debug.Log($"High school: eligible {num2} students {num9} total {num6} enter {num12} drop {num15}");
		UnityEngine.Debug.Log($"College eligible {num3} students {num10} total {num7} enter {num13 / num7} drop {num16 / num7}");
		UnityEngine.Debug.Log($"University eligible {num4} students {num11} total {num7} enter {num14 / num7} drop {num17 / num7}");
		UnityEngine.Debug.Log($"Highest teens {num20} adults {num21} elders {num23} workers {num22} wellb {num19 / num7} willi {num18 / num7}");
	}
```

- `private CalculateStudentsFromOC() : System.Void`  

```csharp
private void CalculateStudentsFromOC()
	{
		EntityQuery entityQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<Game.Citizens.Student>(), ComponentType.ReadOnly<Citizen>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		ComponentLookup<Citizen> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef);
		NativeArray<Entity> nativeArray = entityQuery.ToEntityArray(Allocator.Temp);
		int num = 0;
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity entity = nativeArray[i];
			if ((componentLookup[entity].m_State & CitizenFlags.Commuter) != CitizenFlags.None)
			{
				num++;
			}
		}
		UnityEngine.Debug.Log($"Students from OC: {num}");
	}
```

- `private CleanupObsoleteEntities() : System.Void`  

```csharp
private void CleanupObsoleteEntities()
	{
		NativeArray<ArchetypeChunk> nativeArray = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Deleted>()).ToArchetypeChunkArray(Allocator.TempJob);
		NativeParallelHashMap<Entity, int> nativeParallelHashMap = new NativeParallelHashMap<Entity, int>(100, Allocator.Temp);
		NativeList<Entity> nativeList = new NativeList<Entity>(100, Allocator.Temp);
		NativeList<Entity> nativeList2 = new NativeList<Entity>(100, Allocator.Temp);
		EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<PrefabRef> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		CompleteDependency();
		for (int i = 0; i < nativeArray.Length; i++)
		{
			ArchetypeChunk archetypeChunk = nativeArray[i];
			NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
			NativeArray<PrefabRef> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle);
			for (int j = 0; j < nativeArray3.Length; j++)
			{
				Entity prefab = nativeArray3[j].m_Prefab;
				if (base.EntityManager.HasEnabledComponent<PrefabData>(prefab))
				{
					continue;
				}
				Entity value = nativeArray2[j];
				if (base.EntityManager.TryGetBuffer(value, isReadOnly: true, out DynamicBuffer<ConnectedEdge> buffer))
				{
					Entity entity = Entity.Null;
					float num = float.MinValue;
					for (int k = 0; k < buffer.Length; k++)
					{
						Entity edge = buffer[k].m_Edge;
						Entity prefab2 = base.EntityManager.GetComponentData<PrefabRef>(edge).m_Prefab;
						Game.Net.Edge componentData = base.EntityManager.GetComponentData<Game.Net.Edge>(edge);
						if (base.EntityManager.HasEnabledComponent<PrefabData>(prefab2) && !base.EntityManager.HasComponent<Deleted>(prefab2) && (componentData.m_Start == value || componentData.m_End == value))
						{
							NetData componentData2 = base.EntityManager.GetComponentData<NetData>(prefab2);
							if (componentData2.m_NodePriority > num)
							{
								entity = prefab2;
								num = componentData2.m_NodePriority;
							}
						}
					}
					if (entity != Entity.Null)
					{
						base.EntityManager.SetComponentData(value, new PrefabRef(entity));
						nativeList2.Add(in value);
						continue;
					}
				}
				if (nativeParallelHashMap.TryGetValue(prefab, out var item))
				{
					nativeParallelHashMap[prefab] = item + 1;
				}
				else
				{
					nativeParallelHashMap.Add(prefab, 1);
				}
				nativeList.Add(in value);
			}
		}
		nativeArray.Dispose();
		base.EntityManager.AddComponent<Deleted>(nativeList.AsArray());
		base.EntityManager.AddComponent<Updated>(nativeList2.AsArray());
		nativeList.Dispose();
		NativeParallelHashMap<Entity, int>.Enumerator enumerator = nativeParallelHashMap.GetEnumerator();
		while (enumerator.MoveNext())
		{
			PrefabID obsoleteID = m_PrefabSystem.GetObsoleteID(enumerator.Current.Key);
			UnityEngine.Debug.Log($"{obsoleteID}: Removed {enumerator.Current.Value} instances");
		}
		enumerator.Dispose();
		nativeParallelHashMap.Dispose();
	}
```

- `private ClearSelection() : System.Void`  

```csharp
private void ClearSelection()
	{
		m_ToolSystem.selected = Entity.Null;
	}
```

- `private CreateDebugBlitPass() : System.Void`  

```csharp
private void CreateDebugBlitPass()
	{
		if (m_DebugBlitVolume == null && m_DebugBlitPass == null)
		{
			m_DebugBlitVolume = new GameObject("DebugBlitVolume");
			UnityEngine.Object.DontDestroyOnLoad(m_DebugBlitVolume);
			CustomPassVolume customPassVolume = m_DebugBlitVolume.AddComponent<CustomPassVolume>();
			customPassVolume.injectionPoint = CustomPassInjectionPoint.AfterPostProcess;
			customPassVolume.priority = -100f;
			m_DebugBlitPass = (DebugCustomPass)customPassVolume.AddPassOfType<DebugCustomPass>();
			m_DebugBlitPass.name = "DebugBlit";
		}
	}
```

- `private CreateDebugClass(System.Type type) : System.Object`  

```csharp
private object CreateDebugClass(Type type)
	{
		if (!type.IsAbstract && !typeof(ComponentSystemBase).IsAssignableFrom(type))
		{
			object obj = Activator.CreateInstance(type);
			m_DebugClasses.Add(obj);
			return obj;
		}
		return null;
	}
```

- `private CreateEventUI() : UnityEngine.Rendering.DebugUI+Foldout`  

```csharp
private DebugUI.Foldout CreateEventUI()
	{
		DebugUI.Foldout foldout = new DebugUI.Foldout
		{
			displayName = "Start event"
		};
		if (!m_EventQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray = m_EventQuery.ToEntityArray(Allocator.TempJob);
			try
			{
				for (int i = 0; i < nativeArray.Length; i++)
				{
					Entity entity = nativeArray[i];
					EventPrefab prefab = m_PrefabSystem.GetPrefab<EventPrefab>(entity);
					foldout.children.Add(new DebugUI.Button
					{
						displayName = prefab.name,
						action = delegate
						{
							StartEvent(entity);
						}
					});
				}
			}
			finally
			{
				nativeArray.Dispose();
			}
		}
		foldout.children.Add(new DebugUI.Value
		{
			displayName = "Danger Level",
			getter = () => (m_CitySystem.City != Entity.Null && base.EntityManager.TryGetComponent<Game.City.DangerLevel>(m_CitySystem.City, out var component)) ? ((object)component.m_DangerLevel) : ((object)0f)
		});
		return foldout;
	}
```

- `private CreateToolUI() : UnityEngine.Rendering.DebugUI+Container`  

```csharp
private DebugUI.Container CreateToolUI()
	{
		DebugUI.Container container = new DebugUI.Container();
		ToolBaseSystem activeTool = m_ToolSystem.activeTool;
		if (activeTool is DefaultToolSystem)
		{
			DefaultToolSystemUI(container);
		}
		else if (activeTool is BulldozeToolSystem)
		{
			BulldozeToolSystemUI(container);
		}
		else if (activeTool is NetToolSystem)
		{
			NetToolSystemUI(container);
		}
		else if (activeTool is ObjectToolSystem)
		{
			ObjectToolSystemUI(container);
		}
		else if (activeTool is ZoneToolSystem)
		{
			ZoneToolSystemUI(container);
		}
		else if (activeTool is AreaToolSystem)
		{
			AreaToolSystemUI(container);
		}
		else if (activeTool is RouteToolSystem)
		{
			RouteToolSystemUI(container);
		}
		else if (activeTool is UpgradeToolSystem)
		{
			UpgradeToolSystemUI(container);
		}
		else if (activeTool is TerrainToolSystem)
		{
			TerrainToolSystemUI(container);
		}
		container.children.Add(new DebugUI.BoolField
		{
			displayName = "Bypass validation results",
			getter = () => m_ToolSystem.ignoreErrors,
			setter = delegate(bool value)
			{
				m_ToolSystem.ignoreErrors = value;
			}
		});
		ToolBrushUI(container, m_ToolSystem.activeTool);
		ToolSnapUI(container, m_ToolSystem.activeTool);
		return container;
	}
```

- `private static CreateVolumeParameterWidget(System.String name, UnityEngine.Rendering.VolumeParameter param, System.Func<System.Boolean> isHiddenCallback = null) : UnityEngine.Rendering.DebugUI+Widget`  

```csharp
private static DebugUI.Widget CreateVolumeParameterWidget(string name, VolumeParameter param, Func<bool> isHiddenCallback = null)
	{
		if (param == null)
		{
			return new DebugUI.Value
			{
				displayName = name,
				getter = () => "-"
			};
		}
		Type parameterType = param.GetType();
		if (parameterType == typeof(ColorParameter))
		{
			ColorParameter p = (ColorParameter)param;
			return new DebugUI.ColorField
			{
				displayName = name,
				hdr = p.hdr,
				showAlpha = p.showAlpha,
				getter = () => p.value,
				setter = delegate(UnityEngine.Color value)
				{
					p.value = value;
				},
				isHiddenCallback = isHiddenCallback
			};
		}
		if (parameterType == typeof(BoolParameter))
		{
			BoolParameter p2 = (BoolParameter)param;
			return new DebugUI.BoolField
			{
				displayName = name,
				getter = () => p2.value,
				setter = delegate(bool value)
				{
					p2.value = value;
				},
				isHiddenCallback = isHiddenCallback
			};
		}
		Type[] genericTypeArguments = parameterType.GetTypeInfo().BaseType.GenericTypeArguments;
		if (genericTypeArguments.Length != 0 && genericTypeArguments[0].IsArray)
		{
			return new DebugUI.ObjectListField
			{
				displayName = name,
				getter = () => (UnityEngine.Object[])parameterType.GetProperty("value").GetValue(param, null),
				type = parameterType
			};
		}
		PropertyInfo property = param.GetType().GetProperty("value");
		MethodInfo method = property.PropertyType.GetMethod("ToString", Type.EmptyTypes);
		if (method == null || method.DeclaringType == typeof(object) || method.DeclaringType == typeof(UnityEngine.Object))
		{
			PropertyInfo nameProp = property.PropertyType.GetProperty("name");
			if (nameProp == null)
			{
				return new DebugUI.Value
				{
					displayName = name,
					getter = () => "Debug view not supported"
				};
			}
			return new DebugUI.Value
			{
				displayName = name,
				getter = delegate
				{
					object value = property.GetValue(param);
					return (value == null || value.Equals(null)) ? "None" : (nameProp.GetValue(value) ?? "None");
				},
				isHiddenCallback = isHiddenCallback
			};
		}
		return new DebugUI.Value
		{
			displayName = name,
			getter = delegate
			{
				object value = property.GetValue(param);
				return (value != null) ? value.ToString() : "None";
			},
			isHiddenCallback = isHiddenCallback
		};
	}
```

- `private DefaultToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private void DefaultToolSystemUI(DebugUI.Container container)
	{
		if (m_ToolSystem.actionMode.IsEditor())
		{
			container.children.Add(new DebugUI.Button
			{
				displayName = "Select start tiles",
				action = delegate
				{
					SelectMapTile();
				}
			});
		}
		if (m_ToolSystem.selected == Entity.Null)
		{
			container.children.Add(new DebugUI.Value
			{
				displayName = "Selected",
				getter = () => "None"
			});
			PolicyUI(container, m_CitySystem.City);
		}
		else
		{
			Entity entity = m_ToolSystem.selected;
			if (base.EntityManager.HasComponent<PrefabRef>(entity))
			{
				PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(entity);
				string prefabName = m_PrefabSystem.GetPrefabName(componentData.m_Prefab);
				container.children.Add(new DebugUI.Value
				{
					displayName = "Selected",
					getter = () => prefabName
				});
				container.children.Add(new DebugUI.Value
				{
					displayName = "Entity Id",
					getter = () => $"({entity.Index})"
				});
				if (base.EntityManager.HasEnabledComponent<PrefabData>(componentData.m_Prefab))
				{
					BuildingMoveUI(container, entity, componentData.m_Prefab);
					BuildingUpgradeUI(container, componentData.m_Prefab);
					LevelUpUI(container, entity, componentData.m_Prefab);
					ServiceDistrictUI(container, entity);
					PolicyUI(container, entity);
				}
			}
			else
			{
				container.children.Add(new DebugUI.Value
				{
					displayName = "Selected",
					getter = () => $"({entity.Index})"
				});
			}
		}
		if (!m_DebugQuery.IsEmptyIgnoreFilter)
		{
			container.children.Add(new DebugUI.Button
			{
				displayName = "Clear debug selection",
				action = delegate
				{
					base.EntityManager.RemoveComponent<Game.Tools.Debug>(m_DebugQuery);
				}
			});
		}
		DefaultToolSystem dts = (DefaultToolSystem)m_ToolSystem.activeTool;
		container.children.Add(new DebugUI.BoolField
		{
			displayName = "Allow gameplay manipulation",
			getter = () => dts.allowManipulation,
			setter = delegate(bool value)
			{
				dts.allowManipulation = value;
			}
		});
		container.children.Add(new DebugUI.BoolField
		{
			displayName = "Debug toggle",
			getter = () => dts.debugSelect,
			setter = delegate(bool value)
			{
				dts.debugSelect = value;
			}
		});
		void SelectMapTile()
		{
			SelectionToolSystem tool = GetTool<SelectionToolSystem>();
			tool.selectionType = SelectionType.MapTiles;
			tool.selectionOwner = Entity.Null;
			m_ToolSystem.activeTool = tool;
		}
	}
```

- `private DisposeDebugClasses() : System.Void`  

```csharp
private void DisposeDebugClasses()
	{
		foreach (object item in m_DebugClasses)
		{
			if (item is IDisposable disposable)
			{
				disposable.Dispose();
			}
		}
		m_DebugClasses.Clear();
	}
```

- `private EditorDate() : System.String`  

```csharp
private string EditorDate()
	{
		return m_TimeSystem.GetCurrentDateTime().Hour + ":" + m_TimeSystem.GetCurrentDateTime().Minute.ToString("D2") + ", Month " + m_TimeSystem.GetCurrentDateTime().Day;
	}
```

- `private EnableNotification(Unity.Entities.Entity entity, System.Boolean enabled) : System.Void`  

```csharp
private void EnableNotification(Entity entity, bool enabled)
	{
		base.EntityManager.SetComponentEnabled<NotificationIconDisplayData>(entity, enabled);
		base.World.GetOrCreateSystemManaged<IconClusterSystem>().RecalculateClusters();
	}
```

- `private ExecuteMethod(System.Reflection.MethodInfo method, System.Object target, Game.Debug.DebugTabAttribute attribute) : System.Void`  

```csharp
private void ExecuteMethod(MethodInfo method, object target, DebugTabAttribute attribute)
	{
		ParameterInfo[] parameters = method.GetParameters();
		List<DebugUI.Widget> list = null;
		if (parameters.Length == 0)
		{
			if (target != null)
			{
				list = method.Invoke<object, List<DebugUI.Widget>>(target, Array.Empty<object>());
			}
			else if (typeof(ComponentSystemBase).IsAssignableFrom(method.DeclaringType))
			{
				ComponentSystemBase orCreateSystemManaged = base.World.GetOrCreateSystemManaged(method.DeclaringType);
				list = method.Invoke<ComponentSystemBase, List<DebugUI.Widget>>(orCreateSystemManaged, Array.Empty<object>());
			}
			else
			{
				list = method.Invoke<List<DebugUI.Widget>>(Array.Empty<object>());
			}
		}
		else if (parameters.Length == 1)
		{
			list = ((target == null) ? method.Invoke<List<DebugUI.Widget>>(new object[1] { base.World }) : method.Invoke<object, List<DebugUI.Widget>>(target, new object[1] { base.World }));
		}
		if (list != null)
		{
			AddPanel(attribute.name, list, attribute.priority);
		}
	}
```

- `private ExportHeightMap() : System.Void`  

```csharp
private void ExportHeightMap()
	{
		NativeSlice<byte> nativeSlice = new NativeSlice<ushort>(m_TerrainSystem.GetHeightData(waitForPending: true).heights).SliceConvert<byte>();
		byte[] array = new byte[nativeSlice.Length];
		nativeSlice.CopyTo(array);
		File.WriteAllBytes(EnvPath.kUserDataPath + "/TerrainExport.raw", array);
	}
```

- `private FollowSelectedCitizen() : System.Void`  

```csharp
private void FollowSelectedCitizen()
	{
		if (m_ToolSystem.selected != Entity.Null && base.EntityManager.HasComponent<Citizen>(m_ToolSystem.selected))
		{
			World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<LifePathEventSystem>().FollowCitizen(m_ToolSystem.selected);
		}
	}
```

- `public FullWithGarbage() : System.Void`  

```csharp
public void FullWithGarbage()
	{
		EntityManager entityManager = World.DefaultGameObjectInjectionWorld.EntityManager;
		GarbageParameterData singleton = m_GarbageParameterQuery.GetSingleton<GarbageParameterData>();
		if (entityManager.TryGetComponent<GarbageProducer>(m_ToolSystem.selected, out var component))
		{
			component.m_Garbage = singleton.m_MaxGarbageAccumulation;
			entityManager.SetComponentData(m_ToolSystem.selected, component);
		}
	}
```

- `private GetAnimBuffer() : System.String`  

```csharp
private string GetAnimBuffer()
	{
		m_AnimatedSystem.GetAnimStats(out var allocatedSize, out var bufferSize, out var count);
		return $"{FormatUtils.FormatBytes(allocatedSize)} / {FormatUtils.FormatBytes(bufferSize)} ({count})";
	}
```

- `private GetAreaBuffer() : System.String`  

```csharp
private string GetAreaBuffer()
	{
		m_AreaBatchSystem.GetAreaStats(out var allocatedSize, out var bufferSize, out var count);
		return $"{FormatUtils.FormatBytes(allocatedSize)} / {FormatUtils.FormatBytes(bufferSize)} ({count})";
	}
```

- `private GetArrayFoldout(System.Array record1, System.Array record2) : UnityEngine.Rendering.DebugUI+Foldout`  

```csharp
private DebugUI.Foldout GetArrayFoldout(Array record1, Array record2)
	{
		DebugUI.Foldout foldout = new DebugUI.Foldout
		{
			displayName = "Change Buffers Data"
		};
		for (int i = 0; i < record1.Length; i++)
		{
			object value = record1.GetValue(i);
			object value2 = record2.GetValue(i);
			DebugUI.Foldout fieldValueFoldout = GetFieldValueFoldout(value, value2);
			fieldValueFoldout.displayName = "Element " + i;
			foldout.children.Add(fieldValueFoldout);
		}
		return foldout;
	}
```

- `private GetBatchAllocation() : System.String`  

```csharp
private string GetBatchAllocation()
	{
		JobHandle dependencies;
		NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData> nativeBatchInstances = m_BatchManagerSystem.GetNativeBatchInstances(readOnly: true, out dependencies);
		dependencies.Complete();
		nativeBatchInstances.GetMemoryStats(out var allocatedSize, out var bufferSize);
		return FormatUtils.FormatBytes(allocatedSize) + " / " + FormatUtils.FormatBytes(bufferSize);
	}
```

- `private GetBatchGroups() : System.String`  

```csharp
private string GetBatchGroups()
	{
		JobHandle dependencies;
		NativeBatchGroups<CullingData, GroupData, BatchData, InstanceData> nativeBatchGroups = m_BatchManagerSystem.GetNativeBatchGroups(readOnly: true, out dependencies);
		JobHandle dependencies2;
		NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData> nativeBatchInstances = m_BatchManagerSystem.GetNativeBatchInstances(readOnly: true, out dependencies2);
		dependencies.Complete();
		dependencies2.Complete();
		return $"{nativeBatchInstances.GetActiveGroupCount()} / {m_ManagedBatchSystem.groupCount} ({nativeBatchGroups.GetGroupCount()})";
	}
```

- `private GetBatchMaterials() : System.String`  

```csharp
private string GetBatchMaterials()
	{
		return m_ManagedBatchSystem.materialCount.ToString();
	}
```

- `private GetBatchMeshes() : System.String`  

```csharp
private string GetBatchMeshes()
	{
		long totalSizeInMemory = (long)m_BatchMeshSystem.totalSizeInMemory;
		long memoryBudget = (long)m_BatchMeshSystem.memoryBudget;
		return $"{FormatUtils.FormatBytes(totalSizeInMemory)} / {FormatUtils.FormatBytes(memoryBudget)} ({m_BatchMeshSystem.loadedMeshCount})";
	}
```

- `private GetBatchRenderers() : System.String`  

```csharp
private string GetBatchRenderers()
	{
		ManagedBatches<OptionalProperties> managedBatches = m_BatchManagerSystem.GetManagedBatches();
		return $"{managedBatches.RendererCount} / {m_ManagedBatchSystem.batchCount} ({managedBatches.BatchCount})";
	}
```

- `private GetBatchUpload() : System.String`  

```csharp
private string GetBatchUpload()
	{
		m_BatchManagerSystem.GetManagedBatches().GetMemoryStats(out var allocatedSize, out var bufferSize);
		return FormatUtils.FormatBytes(allocatedSize) + " / " + FormatUtils.FormatBytes(bufferSize);
	}
```

- `private GetBoneBuffer() : System.String`  

```csharp
private string GetBoneBuffer()
	{
		m_AnimatedSystem.GetBoneStats(out var allocatedSize, out var bufferSize, out var count);
		return $"{FormatUtils.FormatBytes(allocatedSize)} / {FormatUtils.FormatBytes(bufferSize)} ({count})";
	}
```

- `private GetEffectCulling() : System.String`  

```csharp
private string GetEffectCulling()
	{
		JobHandle dependencies;
		NativeList<EnabledEffectData> enabledData = m_EffectControlSystem.GetEnabledData(readOnly: true, out dependencies);
		dependencies.Complete();
		return $"{enabledData.Length}";
	}
```

- `private GetEntityCulling() : System.String`  

```csharp
private string GetEntityCulling()
	{
		JobHandle dependencies;
		NativeList<PreCullingData> cullingData = m_PreCullingSystem.GetCullingData(readOnly: true, out dependencies);
		int num = GetEntityQuery(ComponentType.ReadOnly<CullingInfo>()).CalculateEntityCount();
		dependencies.Complete();
		return $"{cullingData.Length} / {num}";
	}
```

- `private GetFieldValueFoldout(System.Object object1, System.Object object2) : UnityEngine.Rendering.DebugUI+Foldout`  

```csharp
private DebugUI.Foldout GetFieldValueFoldout(object object1, object object2)
	{
		Type type = object1.GetType();
		DebugUI.Foldout foldout = new DebugUI.Foldout
		{
			displayName = "Value:"
		};
		if (type.IsPrimitive || type == typeof(string))
		{
			if (object1.Equals(object2))
			{
				return foldout;
			}
			DebugUI.Value primitiveUIValueObject = GetPrimitiveUIValueObject(object1, object2);
			primitiveUIValueObject.displayName = $"{object1}";
			foldout.children.Add(primitiveUIValueObject);
		}
		else
		{
			FieldInfo[] fields = type.GetFields(BindingFlags.Instance | BindingFlags.Public | BindingFlags.NonPublic);
			foreach (FieldInfo fieldInfo in fields)
			{
				string name = fieldInfo.Name;
				object value = fieldInfo.GetValue(object1);
				object obj = null;
				if (object2 != null)
				{
					obj = fieldInfo.GetValue(object2);
					if (value.GetHashCode().Equals(obj.GetHashCode()))
					{
						continue;
					}
				}
				DebugUI.Foldout fieldValueFoldout = GetFieldValueFoldout(value, obj);
				fieldValueFoldout.displayName = name ?? "";
				foldout.children.Add(fieldValueFoldout);
			}
		}
		return foldout;
	}
```

- `private GetIndexBuffer() : System.String`  

```csharp
private string GetIndexBuffer()
	{
		m_AnimatedSystem.GetIndexStats(out var allocatedSize, out var bufferSize, out var count);
		return $"{FormatUtils.FormatBytes(allocatedSize)} / {FormatUtils.FormatBytes(bufferSize)} ({count})";
	}
```

- `private GetMetaBuffer() : System.String`  

```csharp
private string GetMetaBuffer()
	{
		m_AnimatedSystem.GetMetaStats(out var allocatedSize, out var bufferSize, out var count);
		return $"{FormatUtils.FormatBytes(allocatedSize)} / {FormatUtils.FormatBytes(bufferSize)} ({count})";
	}
```

- `private GetPrimitiveUIValueObject(System.Object object1, System.Object object2) : UnityEngine.Rendering.DebugUI+Value`  

```csharp
private DebugUI.Value GetPrimitiveUIValueObject(object object1, object object2)
	{
		return new DebugUI.Value
		{
			displayName = $"{GetValue(object1)}",
			getter = () => GetValue(object2)
		};
		static object GetValue(object obj)
		{
			if (obj == null)
			{
				return string.Empty;
			}
			if (!obj.GetType().IsEnum)
			{
				return obj;
			}
			return Enum.GetName(obj.GetType(), obj);
		}
	}
```

- `private GetProceduralEmissiveBuffer() : System.String`  

```csharp
private string GetProceduralEmissiveBuffer()
	{
		m_ProceduralEmissiveSystem.GetMemoryStats(out var allocatedSize, out var bufferSize, out var _, out var _, out var allocationCount);
		return $"{FormatUtils.FormatBytes(allocatedSize)} / {FormatUtils.FormatBytes(bufferSize)} ({allocationCount})";
	}
```

- `private GetProceduralEmissiveUpload() : System.String`  

```csharp
private string GetProceduralEmissiveUpload()
	{
		m_ProceduralEmissiveSystem.GetMemoryStats(out var _, out var _, out var currentUpload, out var uploadSize, out var _);
		return FormatUtils.FormatBytes(currentUpload) + " / " + FormatUtils.FormatBytes(uploadSize);
	}
```

- `private GetProceduralSkeletonBuffer() : System.String`  

```csharp
private string GetProceduralSkeletonBuffer()
	{
		m_ProceduralSkeletonSystem.GetMemoryStats(out var allocatedSize, out var bufferSize, out var _, out var _, out var allocationCount);
		return $"{FormatUtils.FormatBytes(allocatedSize)} / {FormatUtils.FormatBytes(bufferSize)} ({allocationCount})";
	}
```

- `private GetProceduralSkeletonUpload() : System.String`  

```csharp
private string GetProceduralSkeletonUpload()
	{
		m_ProceduralSkeletonSystem.GetMemoryStats(out var _, out var _, out var currentUpload, out var uploadSize, out var _);
		return FormatUtils.FormatBytes(currentUpload) + " / " + FormatUtils.FormatBytes(uploadSize);
	}
```

- `private GetRecordFoldout(Game.Prefabs.Modes.ModePrefab+ModeDebugUILogInfo record) : UnityEngine.Rendering.DebugUI+Foldout`  

```csharp
private DebugUI.Foldout GetRecordFoldout(ModePrefab.ModeDebugUILogInfo record)
	{
		DebugUI.Foldout foldout = new DebugUI.Foldout
		{
			displayName = $"{record}"
		};
		if (record == null || record.m_ValueBefore == null)
		{
			return foldout;
		}
		Type type = record.m_ValueBefore.GetType();
		if (record.m_ValueBefore is Array array)
		{
			if (record.m_ValueAfter != null && record.m_ValueAfter is Array array2 && array.Length == array2.Length)
			{
				foldout = GetArrayFoldout(array, array2);
			}
		}
		else
		{
			string name = type.Name;
			foldout = GetFieldValueFoldout(record.m_ValueBefore, record.m_ValueAfter);
			foldout.displayName = name ?? "";
		}
		return foldout;
	}
```

- `private GetShapeBuffer() : System.String`  

```csharp
private string GetShapeBuffer()
	{
		m_BatchMeshSystem.GetShapeStats(out var allocatedSize, out var bufferSize, out var count);
		return $"{FormatUtils.FormatBytes(allocatedSize)} / {FormatUtils.FormatBytes(bufferSize)} ({count})";
	}
```

- `private GetTool<T>() : T`  

```csharp
private T GetTool<T>();
```

- `private GetWaterSpeedValues() : System.Int32[]`  

```csharp
private int[] GetWaterSpeedValues()
	{
		m_DebugWaterSpeedValues[^1] = m_WaterSystem.MaxSpeed;
		return m_DebugWaterSpeedValues;
	}
```

- `private GiveMaxResources() : System.Void`  

```csharp
private void GiveMaxResources()
	{
		Entity entity = m_ToolSystem.selected;
		if (base.EntityManager.TryGetBuffer(m_ToolSystem.selected, isReadOnly: true, out DynamicBuffer<Renter> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				Entity renter = buffer[i].m_Renter;
				if (base.EntityManager.HasComponent<CompanyData>(renter))
				{
					entity = renter;
				}
			}
		}
		if (!base.EntityManager.TryGetComponent<PrefabRef>(entity, out var component) || !base.EntityManager.TryGetBuffer(entity, isReadOnly: false, out DynamicBuffer<Game.Economy.Resources> buffer2))
		{
			return;
		}
		Entity prefab = component.m_Prefab;
		int totalStorageUsed = EconomyUtils.GetTotalStorageUsed(buffer2);
		if (base.EntityManager.TryGetComponent<IndustrialProcessData>(prefab, out var component2) && base.EntityManager.TryGetComponent<StorageLimitData>(prefab, out var component3) && base.EntityManager.TryGetComponent<PropertyRenter>(entity, out var component4) && base.EntityManager.TryGetComponent<PrefabRef>(component4.m_Property, out var component5))
		{
			int num = component3.m_Limit;
			if (base.EntityManager.HasComponent<Game.Companies.StorageCompany>(entity))
			{
				SpawnableBuildingData componentData = base.EntityManager.GetComponentData<SpawnableBuildingData>(component5.m_Prefab);
				BuildingData componentData2 = base.EntityManager.GetComponentData<BuildingData>(component5.m_Prefab);
				num = component3.GetAdjustedLimitForWarehouse(componentData, componentData2);
			}
			EconomyUtils.AddResources(component2.m_Output.m_Resource, num - totalStorageUsed, buffer2);
		}
	}
```

- `private HappinessFactors() : System.Void`  

```csharp
private void HappinessFactors()
	{
		CitizenHappinessSystem orCreateSystemManaged = base.World.GetOrCreateSystemManaged<CitizenHappinessSystem>();
		Entity singletonEntity = GetEntityQuery(ComponentType.ReadOnly<HappinessFactorParameterData>()).GetSingletonEntity();
		DynamicBuffer<HappinessFactorParameterData> buffer = base.EntityManager.GetBuffer<HappinessFactorParameterData>(singletonEntity, isReadOnly: true);
		ComponentLookup<Locked> locked = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentLookup, ref base.CheckedStateRef);
		for (int i = 0; i < 25; i++)
		{
			float3 happinessFactor = orCreateSystemManaged.GetHappinessFactor((CitizenHappinessSystem.HappinessFactor)i, buffer, ref locked);
			UnityEngine.Debug.Log($"{(CitizenHappinessSystem.HappinessFactor)i}: {happinessFactor.x} ({happinessFactor.y}+{happinessFactor.z})");
		}
	}
```

- `private InfoviewUI() : UnityEngine.Rendering.DebugUI+Widget`  

```csharp
private DebugUI.Widget InfoviewUI()
	{
		if (!m_InfoviewQuery.IsEmptyIgnoreFilter)
		{
			DebugUI.Container container = new DebugUI.Container
			{
				displayName = "Infoviews"
			};
			DebugUI.Button button = new DebugUI.Button
			{
				displayName = "Infoview: " + ((m_ToolSystem.infoview != null) ? m_ToolSystem.infoview.name : "None") + " >>"
			};
			button.action = delegate
			{
				m_ToolSystem.infoview = SelectNext(m_InfoviewQuery, m_ToolSystem.infoview);
				Rebuild(BuildSimulationDebugUI);
			};
			container.children.Add(button);
			DebugUI.Foldout foldout = new DebugUI.Foldout
			{
				displayName = "Infomodes"
			};
			List<InfomodeInfo> infoviewInfomodes = m_ToolSystem.GetInfoviewInfomodes();
			if (infoviewInfomodes != null)
			{
				foreach (InfomodeInfo infomode in infoviewInfomodes)
				{
					foldout.children.Add(new DebugUI.BoolField
					{
						displayName = infomode.m_Mode.name,
						getter = () => m_ToolSystem.IsInfomodeActive(infomode.m_Mode),
						setter = delegate(bool val)
						{
							m_ToolSystem.SetInfomodeActive(infomode.m_Mode, val, infomode.m_Priority);
						}
					});
				}
				container.children.Add(foldout);
			}
			return container;
		}
		return new DebugUI.Button
		{
			displayName = "No infoviews",
			action = delegate
			{
			}
		};
	}
```

- `private InitializeRenderingDebugUI() : System.Void`  

```csharp
private void InitializeRenderingDebugUI()
	{
		if (!m_RenderingDebugUIInitialized)
		{
			CreateDebugBlitPass();
			CacheGameRenderingDebugUISystems();
		}
		m_RenderingDebugUIInitialized = true;
	}
```

- `private LevelUpUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Void`  

```csharp
private void LevelUpUI(DebugUI.Container container, Entity entity, Entity prefab)
	{
		if (base.EntityManager.HasComponent<SpawnableBuildingData>(prefab))
		{
			PrefabBase prefab2 = m_PrefabSystem.GetPrefab<PrefabBase>(prefab);
			container.children.Add(new DebugUI.Button
			{
				displayName = "Level up " + prefab2.name,
				action = delegate
				{
					LevelUp();
				}
			});
			container.children.Add(new DebugUI.Button
			{
				displayName = "Abandon " + prefab2.name,
				action = delegate
				{
					Abandon();
				}
			});
		}
		void Abandon()
		{
			m_BuildingUpkeepSystem.DebugLevelDown(entity, GetComponentLookup<BuildingCondition>(), GetComponentLookup<SpawnableBuildingData>(isReadOnly: true), GetComponentLookup<PrefabRef>(isReadOnly: true), GetComponentLookup<ZoneData>(isReadOnly: true), GetComponentLookup<BuildingPropertyData>(isReadOnly: true));
		}
		void LevelUp()
		{
			m_BuildingUpkeepSystem.DebugLevelUp(entity, GetComponentLookup<BuildingCondition>(), GetComponentLookup<SpawnableBuildingData>(isReadOnly: true), GetComponentLookup<PrefabRef>(isReadOnly: true), GetComponentLookup<ZoneData>(isReadOnly: true), GetComponentLookup<BuildingPropertyData>(isReadOnly: true));
		}
	}
```

- `private LoadGame() : System.Void`  

```csharp
private async void LoadGame()
	{
		LoadGameSystem orCreateSystemManaged = base.World.GetOrCreateSystemManaged<LoadGameSystem>();
		orCreateSystemManaged.dataDescriptor = new AsyncReadDescriptor("DebugSave", EnvPath.kUserDataPath + "/DebugSave.SaveGameData");
		orCreateSystemManaged.context = new Context(Colossal.Serialization.Entities.Purpose.LoadGame, Version.current, Colossal.Hash128.Empty);
		await orCreateSystemManaged.RunOnce();
	}
```

- `public MaxHouseholdsWealth() : System.Void`  

```csharp
public void MaxHouseholdsWealth()
	{
		NativeArray<Entity> nativeArray = m_HouseholdGroup.ToEntityArray(Allocator.Temp);
		EntityManager entityManager = base.World.EntityManager;
		for (int i = 0; i < nativeArray.Length; i++)
		{
			DynamicBuffer<Game.Economy.Resources> buffer = entityManager.GetBuffer<Game.Economy.Resources>(nativeArray[i]);
			EconomyUtils.SetResources(Resource.Money, buffer, int.MaxValue);
			Household componentData = entityManager.GetComponentData<Household>(nativeArray[i]);
			componentData.m_Resources = int.MaxValue;
			componentData.m_ConsumptionPerDay = 0;
			entityManager.SetComponentData(nativeArray[i], componentData);
		}
	}
```

- `private NetToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private void NetToolSystemUI(DebugUI.Container container)
	{
		NetToolSystem nts = GetTool<NetToolSystem>();
		if (nts.GetPrefab() == null)
		{
			nts.prefab = SelectNext(m_NetQuery, nts.prefab);
		}
		container.children.Add(new DebugUI.Value
		{
			displayName = "Type",
			getter = () => nts.GetPrefab().name
		});
		container.children.Add(new DebugUI.Button
		{
			displayName = "Select next",
			action = delegate
			{
				nts.prefab = SelectNext(m_NetQuery, nts.prefab);
			}
		});
		container.children.Add(new DebugUI.EnumField
		{
			displayName = "Mode",
			getter = () => (int)nts.mode,
			setter = delegate(int value)
			{
				nts.mode = (NetToolSystem.Mode)value;
			},
			onValueChanged = RebuildSimulationDebugUI,
			autoEnum = typeof(NetToolSystem.Mode),
			getIndex = () => (int)nts.mode,
			setIndex = delegate(int value)
			{
				nts.mode = (NetToolSystem.Mode)value;
			}
		});
		Bounds1 elevationLimits = default(Bounds1);
		if (nts.prefab != null && m_PrefabSystem.TryGetComponentData<PlaceableNetData>(nts.prefab, out var component))
		{
			elevationLimits = component.m_ElevationRange;
			if (component.m_UndergroundPrefab != Entity.Null)
			{
				NetPrefab prefab = m_PrefabSystem.GetPrefab<NetPrefab>(component.m_UndergroundPrefab);
				if (m_PrefabSystem.TryGetComponentData<PlaceableNetData>(prefab, out component))
				{
					elevationLimits |= component.m_ElevationRange;
				}
			}
		}
		if (elevationLimits.max > elevationLimits.min)
		{
			container.children.Add(new DebugUI.FloatField
			{
				displayName = "Elevation Step",
				getter = () => nts.elevationStep,
				setter = delegate(float value)
				{
					if (value > 7.5f)
					{
						nts.elevationStep = 10f;
					}
					else if (value > 3.75f)
					{
						nts.elevationStep = 5f;
					}
					else if (value > 1.875f)
					{
						nts.elevationStep = 2.5f;
					}
					else
					{
						nts.elevationStep = 1.25f;
					}
				},
				min = () => 1.25f,
				max = () => 10f
			});
			container.children.Add(new DebugUI.FloatField
			{
				displayName = "Elevation",
				getter = () => nts.elevation,
				setter = delegate(float value)
				{
					nts.elevation = math.round(value / nts.elevationStep) * nts.elevationStep;
				},
				min = () => elevationLimits.min,
				max = () => elevationLimits.max
			});
		}
		container.children.Add(new DebugUI.BoolField
		{
			displayName = "Parallel Road",
			getter = () => nts.parallelCount > 0,
			setter = delegate(bool value)
			{
				nts.parallelCount = (value ? 1 : 0);
			}
		});
	}
```

- `private ObjectToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private void ObjectToolSystemUI(DebugUI.Container container)
	{
		ObjectToolSystem ots = GetTool<ObjectToolSystem>();
		if (ots.GetPrefab() == null)
		{
			ots.mode = ObjectToolSystem.Mode.Create;
			ots.prefab = SelectNext(m_ObjectQuery, ots.prefab);
		}
		container.children.Add(new DebugUI.Value
		{
			displayName = "Type",
			getter = () => ots.GetPrefab().name
		});
		container.children.Add(new DebugUI.Button
		{
			displayName = "Select next",
			action = delegate
			{
				ots.prefab = SelectNext(m_ObjectQuery, ots.prefab);
			}
		});
		if (!ots.allowAge)
		{
			return;
		}
		for (int num = 0; num < 4; num++)
		{
			Game.Tools.AgeMask age = (Game.Tools.AgeMask)(1 << num);
			container.children.Add(new DebugUI.BoolField
			{
				displayName = age.ToString(),
				getter = () => (ots.ageMask & age) != 0,
				setter = delegate(bool value)
				{
					ots.ageMask = (Game.Tools.AgeMask)(((uint)ots.ageMask & (uint)(byte)(~(int)age)) | (uint)(value ? age : ((Game.Tools.AgeMask)0)));
				}
			});
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		base.Enabled = false;
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_AirPollutionSystem = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_NoisePollutionSystem = base.World.GetOrCreateSystemManaged<NoisePollutionSystem>();
		m_TelecomCoverageSystem = base.World.GetOrCreateSystemManaged<TelecomCoverageSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ZoneSpawnSystem = base.World.GetOrCreateSystemManaged<ZoneSpawnSystem>();
		m_AreaSpawnSystem = base.World.GetOrCreateSystemManaged<AreaSpawnSystem>();
		m_BuildingUpkeepSystem = base.World.GetOrCreateSystemManaged<BuildingUpkeepSystem>();
		m_HouseholdFindPropertySystem = base.World.GetOrCreateSystemManaged<HouseholdFindPropertySystem>();
		m_GraduationSystem = base.World.GetOrCreateSystemManaged<GraduationSystem>();
		m_CrimeCheckSystem = base.World.GetOrCreateSystemManaged<CrimeCheckSystem>();
		m_ApplyToSchoolSystem = base.World.GetOrCreateSystemManaged<ApplyToSchoolSystem>();
		m_FindSchoolSystem = base.World.GetOrCreateSystemManaged<FindSchoolSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_SelectedInfoUISystem = base.World.GetOrCreateSystemManaged<SelectedInfoUISystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_DebugUISystem = base.World.GetOrCreateSystemManaged<DebugUISystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_SnowSystem = base.World.GetOrCreateSystemManaged<SnowSystem>();
		m_PlanetarySystem = base.World.GetOrCreateSystemManaged<PlanetarySystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_ClimateRenderSystem = base.World.GetOrCreateSystemManaged<ClimateRenderSystem>();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_ElectricityFlowSystem = base.World.GetOrCreateSystemManaged<ElectricityFlowSystem>();
		m_AdjustElectricityConsumptionSystem = base.World.GetOrCreateSystemManaged<AdjustElectricityConsumptionSystem>();
		m_WaterPipeFlowSystem = base.World.GetOrCreateSystemManaged<WaterPipeFlowSystem>();
		m_DispatchWaterSystem = base.World.GetOrCreateSystemManaged<DispatchWaterSystem>();
		m_TripNeededSystem = base.World.GetOrCreateSystemManaged<TripNeededSystem>();
		m_LifePathEventSystem = base.World.GetOrCreateSystemManaged<LifePathEventSystem>();
		m_BirthSystem = base.World.GetOrCreateSystemManaged<BirthSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_UnlockAllSystem = base.World.GetOrCreateSystemManaged<UnlockAllSystem>();
		m_SignatureBuildingUISystem = base.World.GetOrCreateSystemManaged<SignatureBuildingUISystem>();
		m_DebugQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Tools.Debug>());
		m_PolicyQuery = GetEntityQuery(ComponentType.ReadOnly<PolicyData>());
		m_PolicyEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Modify>());
		m_NetQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<NetData>(), ComponentType.ReadOnly<NetGeometryData>());
		m_ObjectQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<ObjectData>(), ComponentType.ReadOnly<ObjectGeometryData>(), ComponentType.ReadOnly<PlaceableObjectData>());
		m_ZoneQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<ZoneData>());
		m_AreaQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<AreaData>());
		m_RouteQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<RouteData>());
		m_TerraformingQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<TerraformingData>());
		m_InfoviewQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<InfoviewData>());
		m_ThemeQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<ThemeData>());
		m_ExtractorParameterQuery = GetEntityQuery(ComponentType.ReadOnly<ExtractorParameterData>());
		m_HealthcareParameterQuery = GetEntityQuery(ComponentType.ReadOnly<HealthcareParameterData>());
		m_ParkParameterQuery = GetEntityQuery(ComponentType.ReadOnly<ParkParameterData>());
		m_EducationParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EducationParameterData>());
		m_TelecomParameterQuery = GetEntityQuery(ComponentType.ReadOnly<TelecomParameterData>());
		m_GarbageParameterQuery = GetEntityQuery(ComponentType.ReadOnly<GarbageParameterData>());
		m_PoliceParameterQuery = GetEntityQuery(ComponentType.ReadOnly<PoliceConfigurationData>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_DemandParameterQuery = GetEntityQuery(ComponentType.ReadOnly<DemandParameterData>());
		m_PollutionParameterQuery = GetEntityQuery(ComponentType.ReadOnly<PollutionParameterData>());
		m_CitizenHappinessParameterQuery = GetEntityQuery(ComponentType.ReadOnly<CitizenHappinessParameterData>());
		m_LandValueQuery = GetEntityQuery(ComponentType.ReadWrite<LandValue>());
		m_RenterQuery = GetEntityQuery(ComponentType.ReadWrite<PropertyRenter>());
		m_ServiceQuery = GetEntityQuery(ComponentType.ReadWrite<ServiceAvailable>(), ComponentType.ReadWrite<PropertyRenter>());
		m_TradeCostQuery = GetEntityQuery(ComponentType.ReadWrite<TradeCost>(), ComponentType.Exclude<Game.Objects.OutsideConnection>());
		m_TransferQuery = GetEntityQuery(ComponentType.ReadWrite<StorageTransferRequest>());
		m_TripNeededQuery = GetEntityQuery(ComponentType.ReadWrite<TripNeeded>());
		m_EventQuery = GetEntityQuery(ComponentType.ReadOnly<EventData>());
		m_SelectableQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<PrefabRef>() }
		});
		m_HouseholdGroup = GetEntityQuery(ComponentType.ReadOnly<Household>(), ComponentType.Exclude<Deleted>());
		m_CompanyGroup = GetEntityQuery(ComponentType.ReadOnly<CompanyData>(), ComponentType.Exclude<Deleted>());
		m_HouseholdMemberGroup = GetEntityQuery(ComponentType.ReadOnly<HouseholdMember>(), ComponentType.Exclude<Deleted>());
		m_AtmosphereQuery = GetEntityQuery(ComponentType.ReadOnly<AtmosphereData>());
		m_BiomeQuery = GetEntityQuery(ComponentType.ReadOnly<BiomeData>());
		m_IconQuery = GetEntityQuery(ComponentType.ReadOnly<Icon>(), ComponentType.Exclude<Deleted>());
		m_SignatureBuildingQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<SignatureBuildingData>(),
				ComponentType.ReadOnly<UIObjectData>()
			}
		});
		Type[] allTypesDerivedFromAsArray = ReflectionUtils.GetAllTypesDerivedFromAsArray<ToolBaseSystem>();
		m_ToolSystems = new ToolBaseSystem[allTypesDerivedFromAsArray.Length];
		m_ToolSystemNames = new GUIContent[allTypesDerivedFromAsArray.Length];
		for (int i = 0; i < allTypesDerivedFromAsArray.Length; i++)
		{
			Type type = allTypesDerivedFromAsArray[i];
			m_ToolSystems[i] = (ToolBaseSystem)base.World.GetOrCreateSystemManaged(type);
			m_ToolSystemNames[i] = new GUIContent(m_ToolSystems[i].toolID);
		}
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		CoreUtils.Destroy(m_DebugBlitVolume);
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		if (base.Enabled)
		{
			Restart();
		}
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		if (base.Enabled && mode == GameMode.MainMenu)
		{
			Restart();
		}
	}
```

- `private OnSelectionChanged(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Mathematics.float3 position) : System.Void`  

```csharp
private void OnSelectionChanged(Entity entity, Entity prefab, float3 position)
	{
		m_LastSelectionPosition = position;
		Rebuild(BuildSimulationDebugUI);
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		SelectedInfoUISystem selectedInfoUISystem = m_SelectedInfoUISystem;
		selectedInfoUISystem.eventSelectionChanged = (Action<Entity, Entity, float3>)Delegate.Combine(selectedInfoUISystem.eventSelectionChanged, new Action<Entity, Entity, float3>(OnSelectionChanged));
		RegisterDebug();
		m_LastToolPrefab = m_ToolSystem.activePrefab;
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		UnregisterDebug();
		SelectedInfoUISystem selectedInfoUISystem = m_SelectedInfoUISystem;
		selectedInfoUISystem.eventSelectionChanged = (Action<Entity, Entity, float3>)Delegate.Remove(selectedInfoUISystem.eventSelectionChanged, new Action<Entity, Entity, float3>(OnSelectionChanged));
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_FastForwardClimateTime)
		{
			m_ClimateSystem.currentDate.overrideValue += base.CheckedStateRef.WorldUnmanaged.Time.DeltaTime * 0.001f;
			m_ClimateSystem.currentDate.overrideValue = Mathf.Repeat(m_ClimateSystem.currentDate.overrideValue, 1f);
		}
		if (m_ToolSystem.activePrefab != m_LastToolPrefab)
		{
			m_LastToolPrefab = m_ToolSystem.activePrefab;
			Rebuild(BuildSimulationDebugUI);
		}
	}
```

- `private OverridableProperty<T>(System.String displayName, System.Func<T> getter, System.Single min = 0, System.Single max = 1, System.Single incStep = 0,001) : UnityEngine.Rendering.DebugUI+Container`  

```csharp
private UnityEngine.Rendering.DebugUI+Container OverridableProperty<T>(System.String displayName, System.Func<T> getter, System.Single min, System.Single max, System.Single incStep);
```

- `private PolicyUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void PolicyUI(DebugUI.Container container, Entity entity)
	{
		if (!base.EntityManager.HasComponent<Policy>(entity))
		{
			return;
		}
		DebugUI.Container container2 = new DebugUI.Foldout
		{
			displayName = "Policies"
		};
		base.EntityManager.GetBuffer<Policy>(entity, isReadOnly: true);
		bool flag = base.EntityManager.HasComponent<District>(entity);
		bool flag2 = m_CitySystem.City == entity;
		NativeArray<ArchetypeChunk> nativeArray = m_PolicyQuery.ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<DistrictOptionData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_DistrictOptionData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<DistrictModifierData> bufferTypeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_DistrictModifierData_RO_BufferTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<CityOptionData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CityOptionData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<CityModifierData> bufferTypeHandle2 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_CityModifierData_RO_BufferTypeHandle, ref base.CheckedStateRef);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				if ((flag && !archetypeChunk.Has(ref typeHandle) && !archetypeChunk.Has(ref bufferTypeHandle)) || (flag2 && !archetypeChunk.Has(ref typeHandle2) && !archetypeChunk.Has(ref bufferTypeHandle2)) || (!flag2 && (archetypeChunk.Has(ref typeHandle2) || archetypeChunk.Has(ref bufferTypeHandle2))))
				{
					continue;
				}
				NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					Entity policyEntity = nativeArray2[j];
					PolicyPrefab prefab = m_PrefabSystem.GetPrefab<PolicyPrefab>(policyEntity);
					container2.children.Add(new DebugUI.BoolField
					{
						displayName = prefab.name,
						getter = () => TryGetPolicy(entity, policyEntity, out var policy) && (policy.m_Flags & PolicyFlags.Active) != 0,
						setter = delegate
						{
							bool flag3 = false;
							if (TryGetPolicy(entity, policyEntity, out policy))
							{
								flag3 = (policy.m_Flags & PolicyFlags.Active) != 0;
							}
							else
							{
								flag3 = false;
								if (base.EntityManager.HasComponent<PolicySliderData>(policyEntity))
								{
									base.EntityManager.GetComponentData<PolicySliderData>(policyEntity);
								}
							}
							EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
							Entity e = entityCommandBuffer.CreateEntity(m_PolicyEventArchetype);
							entityCommandBuffer.SetComponent(e, new Modify(entity, policyEntity, !flag3, policy.m_Adjustment));
						}
					});
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
		container.children.Add(container2);
	}
```

- `private PrintCommuterDistribute() : System.Void`  

```csharp
private void PrintCommuterDistribute()
	{
		int[] array = new int[4];
		NativeArray<Entity> nativeArray = GetEntityQuery(ComponentType.ReadOnly<CommuterHousehold>()).ToEntityArray(Allocator.Temp);
		EntityManager entityManager = base.World.EntityManager;
		for (int i = 0; i < nativeArray.Length; i++)
		{
			CommuterHousehold componentData = entityManager.GetComponentData<CommuterHousehold>(nativeArray[i]);
			if (componentData.m_OriginalFrom != Entity.Null && entityManager.TryGetComponent<PrefabRef>(componentData.m_OriginalFrom, out var component) && entityManager.TryGetComponent<OutsideConnectionData>(component.m_Prefab, out var component2))
			{
				if ((component2.m_Type & OutsideConnectionTransferType.Road) != OutsideConnectionTransferType.None)
				{
					array[0]++;
				}
				if ((component2.m_Type & OutsideConnectionTransferType.Air) != OutsideConnectionTransferType.None)
				{
					array[1]++;
				}
				if ((component2.m_Type & OutsideConnectionTransferType.Train) != OutsideConnectionTransferType.None)
				{
					array[2]++;
				}
				if ((component2.m_Type & OutsideConnectionTransferType.Ship) != OutsideConnectionTransferType.None)
				{
					array[3]++;
				}
			}
		}
		UnityEngine.Debug.Log($"{nativeArray.Length} commuter households distribution:");
		UnityEngine.Debug.Log($"Road:{array[0]}");
		UnityEngine.Debug.Log($"Air:{array[1]}");
		UnityEngine.Debug.Log($"Train:{array[2]}");
		UnityEngine.Debug.Log($"Ship:{array[3]}");
	}
```

- `private PrintNullHouseholds() : System.Void`  

```csharp
private void PrintNullHouseholds()
	{
		NativeArray<Entity> nativeArray = m_HouseholdMemberGroup.ToEntityArray(Allocator.Temp);
		EntityManager entityManager = base.World.EntityManager;
		for (int i = 0; i < nativeArray.Length; i++)
		{
			HouseholdMember componentData = entityManager.GetComponentData<HouseholdMember>(nativeArray[i]);
			if (componentData.m_Household == Entity.Null)
			{
				UnityEngine.Debug.Log("Null: " + nativeArray[i].ToString());
			}
			else if (!entityManager.Exists(componentData.m_Household))
			{
				string text = nativeArray[i].ToString();
				Entity household = componentData.m_Household;
				UnityEngine.Debug.Log("!Exists: " + text + " -> " + household.ToString());
			}
		}
	}
```

- `private RadioSelection<T>(System.String displayName, System.Func<T> getter, System.Action<T> setter, UnityEngine.GUIContent[] names, T[] values, System.Action onValueChanged = null) : UnityEngine.Rendering.DebugUI+Widget`  

```csharp
private UnityEngine.Rendering.DebugUI+Widget RadioSelection<T>(System.String displayName, System.Func<T> getter, System.Action<T> setter, UnityEngine.GUIContent[] names, T[] values, System.Action onValueChanged);
```

- `public static Rebuild(System.Func<Unity.Entities.World, System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>> method) : System.Void`  

```csharp
private static void Rebuild(Delegate method)
	{
		try
		{
			DebugSystem debugSystem = World.DefaultGameObjectInjectionWorld?.GetExistingSystemManaged<DebugSystem>();
			if (debugSystem != null)
			{
				if (!method.Method.TryGetAttribute<DebugTabAttribute>(out var attribute))
				{
					throw new ArgumentException(method.Method.Name + " is missing the DebugTabAttribute");
				}
				debugSystem.ExecuteMethod(method.Method, method.Target, attribute);
			}
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception, "Failed to register '" + method.Method.Name + "' Debug UI");
		}
	}
```

- `public static Rebuild(System.Func<System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>> method) : System.Void`  

```csharp
private static void Rebuild(Delegate method)
	{
		try
		{
			DebugSystem debugSystem = World.DefaultGameObjectInjectionWorld?.GetExistingSystemManaged<DebugSystem>();
			if (debugSystem != null)
			{
				if (!method.Method.TryGetAttribute<DebugTabAttribute>(out var attribute))
				{
					throw new ArgumentException(method.Method.Name + " is missing the DebugTabAttribute");
				}
				debugSystem.ExecuteMethod(method.Method, method.Target, attribute);
			}
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception, "Failed to register '" + method.Method.Name + "' Debug UI");
		}
	}
```

- `private static Rebuild(System.Delegate method) : System.Void`  

```csharp
private static void Rebuild(Delegate method)
	{
		try
		{
			DebugSystem debugSystem = World.DefaultGameObjectInjectionWorld?.GetExistingSystemManaged<DebugSystem>();
			if (debugSystem != null)
			{
				if (!method.Method.TryGetAttribute<DebugTabAttribute>(out var attribute))
				{
					throw new ArgumentException(method.Method.Name + " is missing the DebugTabAttribute");
				}
				debugSystem.ExecuteMethod(method.Method, method.Target, attribute);
			}
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception, "Failed to register '" + method.Method.Name + "' Debug UI");
		}
	}
```

- `private RebuildSimulationDebugUI<T>(UnityEngine.Rendering.DebugUI+Field<T> field, T value) : System.Void`  

```csharp
private System.Void RebuildSimulationDebugUI<T>(UnityEngine.Rendering.DebugUI+Field<T> field, T value);
```

- `private RefreshGameplayModeDebug() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private List<DebugUI.Widget> RefreshGameplayModeDebug()
	{
		GameModeSystem gms = base.World.GetOrCreateSystemManaged<GameModeSystem>();
		PrefabSystem orCreateSystemManaged = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		EntityManager entityManager = World.DefaultGameObjectInjectionWorld.EntityManager;
		List<(string name, ModeSetting mode)> modeSettings = new List<(string, ModeSetting)>();
		NativeArray<Entity> nativeArray = GetEntityQuery(ComponentType.ReadOnly<GameModeSettingData>()).ToEntityArray(Allocator.TempJob);
		foreach (Entity item2 in nativeArray)
		{
			ModeSetting prefab = m_PrefabSystem.GetPrefab<ModeSetting>(item2);
			modeSettings.Add((orCreateSystemManaged.GetPrefabName(item2), prefab));
		}
		nativeArray.Dispose();
		List<DebugUI.Widget> list = new List<DebugUI.Widget>
		{
			new DebugUI.EnumField
			{
				displayName = "Select next mode",
				getter = () => selectedModeIndex,
				setter = delegate(int num)
				{
					selectedModeIndex = num;
				},
				enumNames = modeSettings.Select(((string name, ModeSetting mode) x) => new GUIContent(x.name)).ToArray(),
				enumValues = Enumerable.Range(0, modeSettings.Count).ToArray(),
				onValueChanged = delegate(DebugUI.Field<int> w, int v)
				{
					ModeSetting item = modeSettings[v].mode;
					gms.overrideMode = item.prefab.name;
				},
				getIndex = () => selectedModeIndex,
				setIndex = delegate
				{
				}
			}
		};
		if (gms.modeSetting == null)
		{
			list.Add(new DebugUI.Value
			{
				displayName = "Current mode: ",
				getter = () => "Normal"
			});
			return list;
		}
		list.Add(new DebugUI.Value
		{
			displayName = "Current mode: ",
			getter = () => gms.modeSetting.prefab.name
		});
		Entity singletonEntity = entityManager.CreateEntityQuery(ComponentType.ReadOnly<ModeSettingData>()).GetSingletonEntity();
		DebugUI.Foldout foldout = new DebugUI.Foldout
		{
			displayName = $"Mode setting entity: {singletonEntity}"
		};
		ModeSettingData componentData = entityManager.GetComponentData<ModeSettingData>(singletonEntity);
		DebugUI.Foldout fieldValueFoldout = GetFieldValueFoldout(componentData, null);
		foldout.children.Add(fieldValueFoldout);
		list.Add(foldout);
		List<ModePrefab> modePrefabs = gms.modeSetting.m_ModePrefabs;
		if (modePrefabs == null)
		{
			return list;
		}
		foreach (ModePrefab item3 in modePrefabs)
		{
			if (item3 == null)
			{
				continue;
			}
			Dictionary<Entity, List<ModePrefab.ModeDebugUILogInfo>> modeDebugUILogs = item3.modeDebugUILogs;
			if (modeDebugUILogs == null)
			{
				continue;
			}
			DebugUI.Foldout foldout2 = new DebugUI.Foldout
			{
				displayName = $"{item3.name} : {modeDebugUILogs.Count} prefab(s) "
			};
			foreach (KeyValuePair<Entity, List<ModePrefab.ModeDebugUILogInfo>> item4 in modeDebugUILogs)
			{
				List<ModePrefab.ModeDebugUILogInfo> value = item4.Value;
				Entity key = item4.Key;
				DebugUI.Foldout foldout3 = new DebugUI.Foldout
				{
					displayName = orCreateSystemManaged.GetPrefabName(key) + " : " + key.ToString()
				};
				List<DebugUI.Foldout> list2 = new List<DebugUI.Foldout>();
				foreach (ModePrefab.ModeDebugUILogInfo item5 in value)
				{
					DebugUI.Foldout recordFoldout = GetRecordFoldout(item5);
					foldout3.children.Add(recordFoldout);
				}
				list2.Add(foldout3);
				list2.Sort((DebugUI.Foldout a, DebugUI.Foldout b) => string.Compare(a.displayName, b.displayName));
				foreach (DebugUI.Foldout item6 in list2)
				{
					foldout2.children.Add(item6);
				}
			}
			list.Add(foldout2);
		}
		return list;
	}
```

- `private RefreshNotifications() : System.Void`  

```csharp
private void RefreshNotifications()
	{
		Dictionary<Entity, int> dictionary = new Dictionary<Entity, int>();
		NativeArray<ArchetypeChunk> nativeArray = m_IconQuery.ToArchetypeChunkArray(Allocator.TempJob);
		ComponentTypeHandle<PrefabRef> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		CompleteDependency();
		for (int i = 0; i < nativeArray.Length; i++)
		{
			NativeArray<PrefabRef> nativeArray2 = nativeArray[i].GetNativeArray(ref typeHandle);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				Entity prefab = nativeArray2[j].m_Prefab;
				if (dictionary.TryGetValue(prefab, out var value))
				{
					dictionary[prefab] = value + 1;
				}
				else
				{
					dictionary.Add(prefab, 1);
				}
			}
		}
		nativeArray.Dispose();
		if (m_Notifications == null)
		{
			m_Notifications = new List<NotificationInfo>(dictionary.Count);
		}
		else
		{
			m_Notifications.Clear();
		}
		foreach (KeyValuePair<Entity, int> item in dictionary)
		{
			m_Notifications.Add(new NotificationInfo
			{
				m_Prefab = item.Key,
				m_Instances = item.Value
			});
		}
		m_Notifications.Sort();
	}
```

- `private RegisterDebug() : System.Void`  

```csharp
private void RegisterDebug()
	{
		foreach (Type item in ReflectionUtils.GetAllConcreteTypesWithAttribute<DebugContainerAttribute>())
		{
			object target = CreateDebugClass(item);
			foreach (var item2 in item.GetAllMethodsWithAttribute<DebugTabAttribute>())
			{
				try
				{
					ExecuteMethod(item2.info, target, item2.attribute);
				}
				catch (Exception exception)
				{
					COSystemBase.baseLog.Error(exception, "Failed to register '" + item2.attribute.name + "' Debug UI");
				}
			}
		}
		Rebuild(BuildSimulationDebugUI);
		DebugManager.instance.RegisterData(this);
	}
```

- `private ReloadWaterSources() : System.Void`  

```csharp
private void ReloadWaterSources()
	{
		EntityQuery entityQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<Game.Simulation.WaterSourceData>());
		base.EntityManager.DestroyEntity(entityQuery);
		Entity singletonEntity = __query_1508003740_0.GetSingletonEntity();
		WaterSystem.WaterSource[] waterSources = m_PrefabSystem.GetPrefab<TerrainPropertiesPrefab>(singletonEntity).m_WaterSources;
		for (int i = 0; i < waterSources.Length; i++)
		{
			WaterSystem.WaterSource waterSource = waterSources[i];
			float3 @float = new float3(waterSource.position.x, 0f, waterSource.position.y);
			Game.Simulation.WaterSourceData waterSourceData = new Game.Simulation.WaterSourceData
			{
				m_Amount = waterSource.amount,
				m_ConstantDepth = waterSource.constantDepth,
				m_Radius = waterSource.radius,
				m_Polluted = waterSource.pollution
			};
			if (waterSourceData.m_ConstantDepth != 2 && waterSourceData.m_ConstantDepth != 3)
			{
				waterSourceData.m_Multiplier = WaterSystem.CalculateSourceMultiplier(waterSourceData, @float);
			}
			else
			{
				waterSourceData.m_Multiplier = waterSource.floodheight;
			}
			Entity entity = base.EntityManager.CreateEntity();
			base.EntityManager.AddComponentData(entity, waterSourceData);
			base.EntityManager.AddComponentData(entity, new Game.Objects.Transform
			{
				m_Position = @float,
				m_Rotation = quaternion.identity
			});
		}
	}
```

- `private RemoveAllHomeless() : System.Void`  

```csharp
private void RemoveAllHomeless()
	{
		EntityQuery entityQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<HomelessHousehold>());
		base.EntityManager.AddComponent<Deleted>(entityQuery);
	}
```

- `private RemoveAllTourist() : System.Void`  

```csharp
private void RemoveAllTourist()
	{
		EntityQuery entityQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<TouristHousehold>());
		base.EntityManager.AddComponent<Deleted>(entityQuery);
	}
```

- `private RemoveResidentsAndVehicles() : System.Void`  

```csharp
private void RemoveResidentsAndVehicles()
	{
		EntityQuery entityQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<Game.Creatures.Resident>());
		base.EntityManager.AddComponent<Deleted>(entityQuery);
		EntityQuery entityQuery2 = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<Vehicle>());
		base.EntityManager.AddComponent<Deleted>(entityQuery2);
	}
```

- `private ResetCommercialStorage() : System.Void`  

```csharp
private void ResetCommercialStorage()
	{
		NativeArray<Entity> nativeArray = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<CommercialCompany>()).ToEntityArray(Allocator.Temp);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			base.EntityManager.RemoveComponent<Game.Economy.Resources>(nativeArray[i]);
			base.EntityManager.AddComponent<Game.Economy.Resources>(nativeArray[i]);
		}
		nativeArray.Dispose();
	}
```

- `public ResetCompanyMoney() : System.Void`  

```csharp
public void ResetCompanyMoney()
	{
		NativeArray<Entity> nativeArray = m_CompanyGroup.ToEntityArray(Allocator.Temp);
		EntityManager entityManager = base.World.EntityManager;
		for (int i = 0; i < nativeArray.Length; i++)
		{
			DynamicBuffer<Game.Economy.Resources> buffer = entityManager.GetBuffer<Game.Economy.Resources>(nativeArray[i]);
			EconomyUtils.SetResources(Resource.Money, buffer, 0);
		}
	}
```

- `private ResetCrimeAccumulation() : System.Void`  

```csharp
private void ResetCrimeAccumulation()
	{
		NativeArray<Entity> nativeArray = GetEntityQuery(ComponentType.ReadOnly<CrimeProducer>()).ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			CrimeProducer componentData = base.EntityManager.GetComponentData<CrimeProducer>(nativeArray[i]);
			componentData.m_Crime = 0f;
			base.EntityManager.SetComponentData(nativeArray[i], componentData);
		}
		nativeArray.Dispose();
	}
```

- `public ResetHouseholdsWealth() : System.Void`  

```csharp
public void ResetHouseholdsWealth()
	{
		NativeArray<Entity> nativeArray = m_HouseholdGroup.ToEntityArray(Allocator.Temp);
		EntityManager entityManager = base.World.EntityManager;
		for (int i = 0; i < nativeArray.Length; i++)
		{
			DynamicBuffer<Game.Economy.Resources> buffer = entityManager.GetBuffer<Game.Economy.Resources>(nativeArray[i]);
			EconomyUtils.SetResources(Resource.Money, buffer, 0);
			Household componentData = entityManager.GetComponentData<Household>(nativeArray[i]);
			componentData.m_Resources = 0;
			componentData.m_ConsumptionPerDay = 0;
			entityManager.SetComponentData(nativeArray[i], componentData);
		}
	}
```

- `public ResetLandvalue() : System.Void`  

```csharp
public void ResetLandvalue()
	{
		EntityManager entityManager = World.DefaultGameObjectInjectionWorld.EntityManager;
		LandValue componentData = default(LandValue);
		componentData.m_LandValue = 0f;
		componentData.m_Weight = 0f;
		NativeArray<Entity> nativeArray = m_LandValueQuery.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			entityManager.SetComponentData(nativeArray[i], componentData);
		}
		nativeArray.Dispose();
	}
```

- `public ResetPollution() : System.Void`  

```csharp
public void ResetPollution()
	{
		GroundPollutionSystem orCreateSystemManaged = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		AirPollutionSystem orCreateSystemManaged2 = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		JobHandle dependencies;
		CellMapData<GroundPollution> data = orCreateSystemManaged.GetData(readOnly: false, out dependencies);
		JobHandle dependencies2;
		CellMapData<AirPollution> data2 = orCreateSystemManaged2.GetData(readOnly: false, out dependencies2);
		dependencies.Complete();
		for (int i = 0; i < data.m_TextureSize.x * data.m_TextureSize.y; i++)
		{
			data.m_Buffer[i] = default(GroundPollution);
		}
		dependencies2.Complete();
		for (int j = 0; j < data2.m_TextureSize.x * data2.m_TextureSize.y; j++)
		{
			data2.m_Buffer[j] = default(AirPollution);
		}
	}
```

- `public ResetRents() : System.Void`  

```csharp
public void ResetRents()
	{
		EntityManager entityManager = World.DefaultGameObjectInjectionWorld.EntityManager;
		NativeArray<Entity> nativeArray = m_RenterQuery.ToEntityArray(Allocator.TempJob);
		m_GroundPollutionSystem.GetMap(readOnly: true, out var dependencies);
		m_AirPollutionSystem.GetMap(readOnly: true, out var dependencies2);
		m_NoisePollutionSystem.GetMap(readOnly: true, out var dependencies3);
		m_TelecomCoverageSystem.GetData(readOnly: true, out var dependencies4);
		base.World.GetOrCreateSystemManaged<TaxSystem>().GetTaxRates();
		dependencies.Complete();
		dependencies2.Complete();
		dependencies3.Complete();
		dependencies4.Complete();
		float2 @float = new float2(0f, 0f);
		float num = 0f;
		float num2 = 0f;
		float num3 = 0f;
		float num4 = 0f;
		float num5 = 0f;
		float num6 = 0f;
		float2 float2 = new float2(0f, 0f);
		float num7 = 0f;
		float num8 = 0f;
		float num9 = 0f;
		float num10 = 0f;
		float num11 = 0f;
		float num12 = 0f;
		float2 float3 = new float2(0f, 0f);
		float num13 = 0f;
		float num14 = 0f;
		float num15 = 0f;
		float num16 = 0f;
		EconomyParameterData economyParameters = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>();
		m_DemandParameterQuery.GetSingleton<DemandParameterData>();
		ResourcePrefabs prefabs = m_ResourceSystem.GetPrefabs();
		ComponentLookup<ResourceData> datas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity entity = nativeArray[i];
			Entity prefab = base.EntityManager.GetComponentData<PrefabRef>(entity).m_Prefab;
			Entity property = base.EntityManager.GetComponentData<PropertyRenter>(entity).m_Property;
			Entity prefab2 = base.EntityManager.GetComponentData<PrefabRef>(property).m_Prefab;
			BuildingData componentData = base.EntityManager.GetComponentData<BuildingData>(prefab2);
			int num17 = componentData.m_LotSize.x * componentData.m_LotSize.y;
			if (base.EntityManager.HasComponent<IndustrialProcessData>(prefab) && base.EntityManager.HasComponent<WorkProvider>(entity))
			{
				int maxWorkers = base.EntityManager.GetComponentData<WorkProvider>(entity).m_MaxWorkers;
				IndustrialProcessData componentData2 = base.EntityManager.GetComponentData<IndustrialProcessData>(prefab);
				WorkplaceData componentData3 = base.EntityManager.GetComponentData<WorkplaceData>(prefab);
				SpawnableBuildingData componentData4 = base.EntityManager.GetComponentData<SpawnableBuildingData>(prefab2);
				base.EntityManager.GetBuffer<Employee>(entity, isReadOnly: true);
				float num18 = 1f;
				if (base.EntityManager.TryGetBuffer(property, isReadOnly: true, out DynamicBuffer<Efficiency> buffer))
				{
					num18 = BuildingUtils.GetEfficiency(buffer);
				}
				DynamicBuffer<TradeCost> buffer2;
				BuyingCompany component;
				if (base.EntityManager.HasComponent<ServiceAvailable>(entity))
				{
					ServiceAvailable componentData5 = base.EntityManager.GetComponentData<ServiceAvailable>(entity);
					base.EntityManager.GetComponentData<ServiceCompanyData>(prefab);
					base.EntityManager.GetBuffer<TradeCost>(entity, isReadOnly: true);
					@float.x += (float)num17 * componentData5.m_MeanPriority;
					@float.y += num17;
					num3 += (float)EconomyUtils.GetCompanyProductionPerDay(num18, maxWorkers, componentData4.m_Level, isIndustrial: false, componentData3, componentData2, prefabs, ref datas, ref economyParameters);
					num4 += (float)EconomyUtils.CalculateTotalWage(maxWorkers, componentData3.m_Complexity, componentData4.m_Level, economyParameters);
					num6 += (float)num17 * num18;
				}
				else if (EconomyUtils.GetWeight(componentData2.m_Output.m_Resource, prefabs, ref datas) > 0f && entityManager.TryGetBuffer(entity, isReadOnly: true, out buffer2) && entityManager.TryGetComponent<BuyingCompany>(entity, out component))
				{
					int companyProductionPerDay = EconomyUtils.GetCompanyProductionPerDay(num18, maxWorkers, componentData4.m_Level, isIndustrial: true, componentData3, componentData2, prefabs, ref datas, ref economyParameters);
					int num19 = EconomyUtils.CalculateTotalWage(maxWorkers, componentData3.m_Complexity, componentData4.m_Level, economyParameters);
					float2.y += num17;
					num7 += (float)companyProductionPerDay;
					num8 += (float)num19;
					num10 += (float)num17 * component.m_MeanInputTripLength;
					num12 += (float)num17 * num18;
					float weight = EconomyUtils.GetWeight(componentData2.m_Input1.m_Resource, prefabs, ref datas);
					float weight2 = EconomyUtils.GetWeight(componentData2.m_Input2.m_Resource, prefabs, ref datas);
					num9 += (float)(num17 * (EconomyUtils.GetTransportCost(component.m_MeanInputTripLength, componentData2.m_Input1.m_Resource, companyProductionPerDay * componentData2.m_Input1.m_Amount, weight) + EconomyUtils.GetTransportCost(component.m_MeanInputTripLength, componentData2.m_Input2.m_Resource, companyProductionPerDay * componentData2.m_Input2.m_Amount, weight2)));
				}
				else if (entityManager.TryGetBuffer(entity, isReadOnly: true, out buffer2) && entityManager.TryGetComponent<BuyingCompany>(entity, out component))
				{
					int companyProductionPerDay2 = EconomyUtils.GetCompanyProductionPerDay(num18, maxWorkers, componentData4.m_Level, isIndustrial: true, componentData3, componentData2, prefabs, ref datas, ref economyParameters);
					int num20 = EconomyUtils.CalculateTotalWage(maxWorkers, componentData3.m_Complexity, componentData4.m_Level, economyParameters);
					float3.y += num17;
					num13 += (float)companyProductionPerDay2;
					num14 += (float)num20;
					num16 += (float)num17 * num18;
				}
			}
			Entity roadEdge = entityManager.GetComponentData<Building>(property).m_RoadEdge;
			float landValueBase = 0f;
			if (entityManager.HasComponent<LandValue>(roadEdge))
			{
				landValueBase = entityManager.GetComponentData<LandValue>(roadEdge).m_LandValue;
			}
			PropertyRenter componentData6 = entityManager.GetComponentData<PropertyRenter>(nativeArray[i]);
			if (entityManager.TryGetComponent<PrefabRef>(componentData6.m_Property, out var component2))
			{
				Entity prefab3 = component2.m_Prefab;
				if (entityManager.TryGetComponent<BuildingPropertyData>(prefab3, out var component3) && entityManager.TryGetComponent<SpawnableBuildingData>(prefab3, out var component4))
				{
					Game.Zones.AreaType areaType = entityManager.GetComponentData<ZoneData>(component4.m_ZonePrefab).m_AreaType;
					int level = component4.m_Level;
					int rentPricePerRenter = PropertyUtils.GetRentPricePerRenter(component3, level, num17, landValueBase, areaType, ref economyParameters);
					componentData6.m_Rent = rentPricePerRenter;
				}
				entityManager.SetComponentData(nativeArray[i], componentData6);
			}
		}
		nativeArray.Dispose();
		UnityEngine.Debug.Log(@float.y + " service averages:");
		UnityEngine.Debug.Log("ServiceAvailable " + 100f * @float.x / @float.y);
		UnityEngine.Debug.Log("Profit per cell " + num / @float.y);
		UnityEngine.Debug.Log("Profit per unit " + num2 / @float.y);
		UnityEngine.Debug.Log("Productivity per cell " + num3 / @float.y);
		UnityEngine.Debug.Log("Wage per cell " + num4 / @float.y);
		UnityEngine.Debug.Log("Profitable " + 100f * num5 / @float.y);
		UnityEngine.Debug.Log("Efficiency " + 100f * num6 / @float.y);
		UnityEngine.Debug.Log(float2.y + " industrial averages:");
		UnityEngine.Debug.Log("Profit per cell" + float2.x / float2.y);
		UnityEngine.Debug.Log("Transport cost " + num9 / float2.y);
		UnityEngine.Debug.Log("Productivity per cell " + num7 / float2.y);
		UnityEngine.Debug.Log("Wage per cell " + num8 / float2.y);
		UnityEngine.Debug.Log("Trip " + num10 / float2.y);
		UnityEngine.Debug.Log("Profitable " + 100f * num11 / float2.y);
		UnityEngine.Debug.Log("Efficiency " + 100f * num12 / float2.y);
		UnityEngine.Debug.Log(float3.y + " office averages:");
		UnityEngine.Debug.Log("Profit per cell " + float3.x / float3.y);
		UnityEngine.Debug.Log("Productivity per cell " + num13 / float3.y);
		UnityEngine.Debug.Log("Wage per cell " + num14 / float3.y);
		UnityEngine.Debug.Log("Profitable " + 100f * num15 / float3.y);
		UnityEngine.Debug.Log("Efficiency " + 100f * num16 / float3.y);
	}
```

- `private ResetServices() : System.Void`  

```csharp
private void ResetServices()
	{
		NativeArray<Entity> nativeArray = m_ServiceQuery.ToEntityArray(Allocator.TempJob);
		NativeArray<ResetServiceData> nativeArray2 = new NativeArray<ResetServiceData>(EconomyUtils.GetResourceIndex(Resource.Last), Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity entity = nativeArray[i];
			Entity prefab = base.EntityManager.GetComponentData<PrefabRef>(entity).m_Prefab;
			Entity property = base.EntityManager.GetComponentData<PropertyRenter>(entity).m_Property;
			Entity prefab2 = base.EntityManager.GetComponentData<PrefabRef>(property).m_Prefab;
			SpawnableBuildingData componentData = base.EntityManager.GetComponentData<SpawnableBuildingData>(prefab2);
			IndustrialProcessData componentData2 = base.EntityManager.GetComponentData<IndustrialProcessData>(prefab);
			ServiceAvailable componentData3 = base.EntityManager.GetComponentData<ServiceAvailable>(entity);
			DynamicBuffer<Efficiency> buffer = base.EntityManager.GetBuffer<Efficiency>(property, isReadOnly: true);
			DynamicBuffer<Employee> buffer2 = base.EntityManager.GetBuffer<Employee>(entity, isReadOnly: true);
			WorkProvider componentData4 = base.EntityManager.GetComponentData<WorkProvider>(entity);
			ResetServiceData value = nativeArray2[EconomyUtils.GetResourceIndex(componentData2.m_Output.m_Resource)];
			value.count++;
			value.meanPriority += componentData3.m_MeanPriority;
			value.serviceAvailable += componentData3.m_ServiceAvailable;
			if (componentData3.m_ServiceAvailable <= 500)
			{
				value.overworked++;
			}
			if (componentData3.m_ServiceAvailable >= 4500)
			{
				value.underworked++;
			}
			if (componentData3.m_ServiceAvailable >= 2400 && componentData3.m_ServiceAvailable <= 2600)
			{
				value.middle++;
			}
			value.efficiency += BuildingUtils.GetEfficiency(buffer);
			value.workers += buffer2.Length;
			value.maxWorkers += componentData4.m_MaxWorkers;
			value.level += componentData.m_Level;
			nativeArray2[EconomyUtils.GetResourceIndex(componentData2.m_Output.m_Resource)] = value;
			base.EntityManager.SetComponentData(nativeArray[i], new ServiceAvailable
			{
				m_MeanPriority = 0.5f,
				m_ServiceAvailable = 2500
			});
		}
		for (int j = 0; j < nativeArray2.Length; j++)
		{
			ResetServiceData resetServiceData = nativeArray2[j];
			if (resetServiceData.count > 0)
			{
				UnityEngine.Debug.Log($"{EconomyUtils.GetName(EconomyUtils.GetResource(j))}: n = {resetServiceData.count}, mean = {resetServiceData.meanPriority / (float)resetServiceData.count}, service = {resetServiceData.serviceAvailable / resetServiceData.count}, eff = {resetServiceData.efficiency / (float)resetServiceData.count}, wrkrs = {resetServiceData.workers / resetServiceData.count}/{resetServiceData.maxWorkers / resetServiceData.count} o/m/u: {(float)resetServiceData.overworked / (float)resetServiceData.count}|{(float)resetServiceData.middle / (float)resetServiceData.count}|{(float)resetServiceData.underworked / (float)resetServiceData.count} lvl {(float)resetServiceData.level / (float)resetServiceData.count}");
			}
		}
		nativeArray2.Dispose();
	}
```

- `private ResetStorages() : System.Void`  

```csharp
private void ResetStorages()
	{
		EntityQuery entityQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<Game.Companies.StorageCompany>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Game.Economy.Resources>(), ComponentType.Exclude<Game.Prefabs.ProcessingCompany>(), ComponentType.Exclude<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Game.Buildings.CargoTransportStation>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		base.EntityManager.AddComponent<Deleted>(entityQuery);
		EntityQuery entityQuery2 = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<StorageProperty>(), ComponentType.Exclude<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Game.Buildings.CargoTransportStation>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		base.EntityManager.AddComponent<Deleted>(entityQuery2);
	}
```

- `private ResetTradeCosts() : System.Void`  

```csharp
private void ResetTradeCosts()
	{
		NativeArray<Entity> nativeArray = m_TradeCostQuery.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			base.EntityManager.GetBuffer<TradeCost>(nativeArray[i]).Clear();
		}
	}
```

- `private ResetTransfers() : System.Void`  

```csharp
private void ResetTransfers()
	{
		NativeArray<Entity> nativeArray = m_TransferQuery.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			base.EntityManager.GetBuffer<StorageTransferRequest>(nativeArray[i]).Clear();
		}
	}
```

- `private ResetTripNeeded() : System.Void`  

```csharp
private void ResetTripNeeded()
	{
		NativeArray<Entity> nativeArray = m_TripNeededQuery.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			base.EntityManager.GetBuffer<TripNeeded>(nativeArray[i]).Clear();
		}
	}
```

- `public Restart() : System.Void`  

```csharp
public void Restart()
	{
		OnStopRunning();
		OnStartRunning();
	}
```

- `private RouteToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private void RouteToolSystemUI(DebugUI.Container container)
	{
		RouteToolSystem rts = GetTool<RouteToolSystem>();
		if (rts.GetPrefab() == null)
		{
			rts.prefab = SelectNext(m_RouteQuery, rts.prefab);
		}
		container.children.Add(new DebugUI.Value
		{
			displayName = "Type",
			getter = () => rts.GetPrefab().name
		});
		container.children.Add(new DebugUI.Button
		{
			displayName = "Select next",
			action = delegate
			{
				rts.prefab = SelectNext(m_RouteQuery, rts.prefab);
			}
		});
	}
```

- `private SaveGame() : System.Void`  

```csharp
private async void SaveGame()
	{
		SaveGameSystem orCreateSystemManaged = base.World.GetOrCreateSystemManaged<SaveGameSystem>();
		orCreateSystemManaged.stream = LongFile.OpenWrite(EnvPath.kUserDataPath + "/DebugSave.SaveGameData");
		orCreateSystemManaged.context = new Context(Colossal.Serialization.Entities.Purpose.SaveGame, Version.current, Colossal.Hash128.Empty);
		await orCreateSystemManaged.RunOnce();
	}
```

- `public SelectEntity(System.String searchTerm) : System.Void`  

```csharp
private void SelectEntity(Entity entity)
	{
		m_ToolSystem.selected = entity;
	}
```

- `private SelectEntity(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void SelectEntity(Entity entity)
	{
		m_ToolSystem.selected = entity;
	}
```

- `private SelectNext<T>(Unity.Entities.EntityQuery group, T current) : T`  

```csharp
private T SelectNext<T>(Unity.Entities.EntityQuery group, T current);
```

- `private SelectNext(Unity.Entities.EntityQuery group, Unity.Entities.Entity current) : Unity.Entities.Entity`  

```csharp
private Entity SelectNext(EntityQuery group, Entity current)
	{
		NativeArray<ArchetypeChunk> nativeArray = group.ToArchetypeChunkArray(Allocator.TempJob);
		EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		bool flag = false;
		for (int i = 0; i < 2; i++)
		{
			for (int j = 0; j < nativeArray.Length; j++)
			{
				NativeArray<Entity> nativeArray2 = nativeArray[j].GetNativeArray(entityTypeHandle);
				for (int k = 0; k < nativeArray2.Length; k++)
				{
					if (flag)
					{
						nativeArray.Dispose();
						return nativeArray2[k];
					}
					flag = nativeArray2[k] == current;
				}
			}
			flag = true;
		}
		nativeArray.Dispose();
		return current;
	}
```

- `private ServiceDistrictUI(UnityEngine.Rendering.DebugUI+Container container, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void ServiceDistrictUI(DebugUI.Container container, Entity entity)
	{
		if (base.EntityManager.HasComponent<ServiceDistrict>(entity))
		{
			container.children.Add(new DebugUI.Button
			{
				displayName = "Select districts",
				action = delegate
				{
					SelectDistricts();
				}
			});
		}
		void SelectDistricts()
		{
			SelectionToolSystem tool = GetTool<SelectionToolSystem>();
			tool.selectionType = SelectionType.ServiceDistrict;
			tool.selectionOwner = entity;
			m_ToolSystem.activeTool = tool;
		}
	}
```

- `private StartEvent(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void StartEvent(Entity entity)
	{
		EventData componentData = base.EntityManager.GetComponentData<EventData>(entity);
		EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
		Entity entity2 = entityCommandBuffer.CreateEntity(componentData.m_Archetype);
		entityCommandBuffer.SetComponent(entity2, new PrefabRef(entity));
		Entity selected = m_ToolSystem.selected;
		if (selected != Entity.Null)
		{
			entityCommandBuffer.SetBuffer<TargetElement>(entity2).Add(new TargetElement(selected));
		}
	}
```

- `private TerrainToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private void TerrainToolSystemUI(DebugUI.Container container)
	{
		TerrainToolSystem tts = GetTool<TerrainToolSystem>();
		if (tts.GetPrefab() == null)
		{
			tts.SetPrefab(SelectNext(m_TerraformingQuery, tts.prefab));
		}
		container.children.Add(new DebugUI.Value
		{
			displayName = "Type",
			getter = () => tts.GetPrefab().name
		});
		container.children.Add(new DebugUI.Button
		{
			displayName = "Select next",
			action = delegate
			{
				tts.SetPrefab(SelectNext(m_TerraformingQuery, tts.prefab));
			}
		});
	}
```

- `private ToggleSelection(System.String displayName, System.Func<System.Boolean> getter, System.Action<System.Boolean> setter, System.Action<UnityEngine.Rendering.DebugUI+Field<System.Int32>, System.Int32> onValueChanged = null) : UnityEngine.Rendering.DebugUI+EnumField`  

```csharp
private DebugUI.EnumField ToggleSelection(string displayName, Func<bool> getter, Action<bool> setter, Action<DebugUI.Field<int>, int> onValueChanged = null)
	{
		return new DebugUI.EnumField
		{
			displayName = displayName,
			getter = () => getter() ? 1 : 0,
			setter = delegate(int value)
			{
				setter(value != 0);
			},
			autoEnum = typeof(ToggleEnum),
			onValueChanged = onValueChanged,
			getIndex = () => getter() ? 1 : 0,
			setIndex = delegate
			{
			}
		};
	}
```

- `private ToolBrushUI(UnityEngine.Rendering.DebugUI+Container container, Game.Tools.ToolBaseSystem tool) : System.Void`  

```csharp
private void ToolBrushUI(DebugUI.Container container, ToolBaseSystem tool)
	{
		if (tool.brushing)
		{
			container.children.Add(new DebugUI.FloatField
			{
				displayName = "Brush Size",
				getter = () => tool.brushSize,
				setter = delegate(float value)
				{
					tool.brushSize = value;
				},
				min = () => 10f,
				max = () => 1000f
			});
			container.children.Add(new DebugUI.FloatField
			{
				displayName = "Brush angle",
				getter = () => tool.brushAngle,
				setter = delegate(float value)
				{
					tool.brushAngle = value;
				},
				min = () => 0f,
				max = () => 360f
			});
			container.children.Add(new DebugUI.FloatField
			{
				displayName = "Brush strength",
				getter = () => tool.brushStrength,
				setter = delegate(float value)
				{
					tool.brushStrength = value;
				},
				min = () => 0.01f,
				max = () => 1f
			});
		}
	}
```

- `private ToolSnapUI(UnityEngine.Rendering.DebugUI+Container container, Game.Tools.ToolBaseSystem tool) : System.Void`  

```csharp
private void ToolSnapUI(DebugUI.Container container, ToolBaseSystem tool)
	{
		tool.GetAvailableSnapMask(out var onMask, out var offMask);
		Snap num = onMask & offMask;
		if ((num & Snap.ExistingGeometry) != Snap.None)
		{
			BitToggle(container, "Snap existing geometry", tool, Snap.ExistingGeometry);
		}
		if ((num & Snap.NearbyGeometry) != Snap.None)
		{
			BitToggle(container, "Snap nearby geometry", tool, Snap.NearbyGeometry);
		}
		if ((num & Snap.StraightDirection) != Snap.None)
		{
			BitToggle(container, "Snap 90 degree angles", tool, Snap.StraightDirection);
		}
		if ((num & Snap.CellLength) != Snap.None)
		{
			BitToggle(container, "Snap cell length", tool, Snap.CellLength);
		}
		if ((num & Snap.GuideLines) != Snap.None)
		{
			BitToggle(container, "Snap guide lines", tool, Snap.GuideLines);
		}
		if ((num & Snap.NetSide) != Snap.None)
		{
			BitToggle(container, "Snap road side", tool, Snap.NetSide);
		}
		if ((num & Snap.NetArea) != Snap.None)
		{
			BitToggle(container, "Snap on road", tool, Snap.NetArea);
		}
		if ((num & Snap.OwnerSide) != Snap.None)
		{
			BitToggle(container, "Snap main object", tool, Snap.OwnerSide);
		}
		if ((num & Snap.ObjectSide) != Snap.None)
		{
			BitToggle(container, "Snap building side", tool, Snap.ObjectSide);
		}
		if ((num & Snap.NetMiddle) != Snap.None)
		{
			BitToggle(container, "Snap to road", tool, Snap.NetMiddle);
		}
		if ((num & Snap.Shoreline) != Snap.None)
		{
			BitToggle(container, "Snap to shoreline", tool, Snap.Shoreline);
		}
		if ((num & Snap.NetNode) != Snap.None)
		{
			BitToggle(container, "Snap road intersection", tool, Snap.NetNode);
		}
		if ((num & Snap.ZoneGrid) != Snap.None)
		{
			BitToggle(container, "Snap zone grid", tool, Snap.ZoneGrid);
		}
		if ((num & Snap.ObjectSurface) != Snap.None)
		{
			BitToggle(container, "Snap object surface", tool, Snap.ObjectSurface);
		}
		if ((num & Snap.Upright) != Snap.None)
		{
			BitToggle(container, "Snap upright", tool, Snap.Upright);
		}
		if ((num & Snap.LotGrid) != Snap.None)
		{
			BitToggle(container, "Snap lot grid", tool, Snap.LotGrid);
		}
		if ((num & Snap.AutoParent) != Snap.None)
		{
			BitToggle(container, "Automatic parenting", tool, Snap.AutoParent);
		}
	}
```

- `private TriggerTestLifeEvent() : System.Void`  

```csharp
private void TriggerTestLifeEvent()
	{
		EntityQuery entityQuery = World.DefaultGameObjectInjectionWorld.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<Followed>(), ComponentType.ReadOnly<Citizen>());
		NativeQueue<TriggerAction> nativeQueue = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<TriggerSystem>().CreateActionBuffer();
		foreach (Entity item in entityQuery.ToEntityArray(Allocator.Temp))
		{
			nativeQueue.Enqueue(new TriggerAction(TriggerType.CitizenFailedSchool, Entity.Null, item, item));
		}
	}
```

- `private TryFindSelectableEntity(System.Int32 index, Unity.Entities.Entity& entity) : System.Boolean`  

```csharp
private bool TryFindSelectableEntity(int index, out Entity entity)
	{
		entity = Entity.Null;
		NativeArray<Entity> nativeArray = m_SelectableQuery.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (nativeArray[i].Index == index)
			{
				entity = nativeArray[i];
				break;
			}
		}
		nativeArray.Dispose();
		return entity != Entity.Null;
	}
```

- `private TryGetPolicy(Unity.Entities.Entity entity, Unity.Entities.Entity policyType, Game.Policies.Policy& policy) : System.Boolean`  

```csharp
private bool TryGetPolicy(Entity entity, Entity policyType, out Policy policy)
	{
		DynamicBuffer<Policy> buffer = base.EntityManager.GetBuffer<Policy>(entity, isReadOnly: true);
		for (int i = 0; i < buffer.Length; i++)
		{
			if (buffer[i].m_Policy == policyType)
			{
				policy = buffer[i];
				return true;
			}
		}
		policy = default(Policy);
		return false;
	}
```

- `private UnityEngine.Rendering.IDebugData.GetReset() : System.Action`  

```csharp
private System.Action UnityEngine.Rendering.IDebugData.GetReset();
```

- `private UnregisterDebug() : System.Void`  

```csharp
private void UnregisterDebug()
	{
		foreach (KeyValuePair<string, List<DebugUI.Widget>> item in m_Panels)
		{
			UnregisterDebugItems(item.Key, item.Value);
		}
		DisposeDebugClasses();
		DebugManager.instance.UnregisterData(this);
	}
```

- `private UnregisterDebugItems(System.String panelName, System.Collections.Generic.IEnumerable<UnityEngine.Rendering.DebugUI+Widget> items) : System.Void`  

```csharp
private void UnregisterDebugItems(string panelName, IEnumerable<DebugUI.Widget> items)
	{
		DebugManager.instance.GetPanel(panelName)?.children.Remove(items);
	}
```

- `private UpgradeToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private void UpgradeToolSystemUI(DebugUI.Container container)
	{
		UpgradeToolSystem uts = GetTool<UpgradeToolSystem>();
		InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		if (m_ToolSystem.selected != Entity.Null)
		{
			Entity entity = m_ToolSystem.selected;
			PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(entity);
			PrefabBase prefabBase = m_PrefabSystem.GetPrefab<PrefabBase>(componentData);
			container.children.Add(new DebugUI.Value
			{
				displayName = "Selected",
				getter = () => prefabBase.name
			});
			container.children.Add(new DebugUI.Value
			{
				displayName = "Entity Id",
				getter = () => $"({entity.Index})"
			});
		}
		if (uts.prefab != null)
		{
			container.children.Add(new DebugUI.Value
			{
				displayName = "Upgrade",
				getter = () => uts.prefab.name
			});
		}
	}
```

- `private ZoneToolSystemUI(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
private void ZoneToolSystemUI(DebugUI.Container container)
	{
		ZoneToolSystem zts = GetTool<ZoneToolSystem>();
		if (zts.GetPrefab() == null)
		{
			zts.prefab = SelectNext(m_ZoneQuery, zts.prefab);
		}
		container.children.Add(new DebugUI.Value
		{
			displayName = "Type",
			getter = () => zts.GetPrefab().name
		});
		container.children.Add(new DebugUI.Button
		{
			displayName = "Select next",
			action = delegate
			{
				zts.prefab = SelectNext(m_ZoneQuery, zts.prefab);
			}
		});
		container.children.Add(new DebugUI.EnumField
		{
			displayName = "Mode",
			getter = () => (int)zts.mode,
			setter = delegate(int value)
			{
				zts.mode = (ZoneToolSystem.Mode)value;
			},
			onValueChanged = RebuildSimulationDebugUI,
			autoEnum = typeof(ZoneToolSystem.Mode),
			getIndex = () => (int)zts.mode,
			setIndex = delegate(int value)
			{
				zts.mode = (ZoneToolSystem.Mode)value;
			}
		});
		container.children.Add(new DebugUI.BoolField
		{
			displayName = "Overwrite existing zone",
			getter = () => zts.overwrite,
			setter = delegate(bool value)
			{
				zts.overwrite = value;
			}
		});
	}
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

