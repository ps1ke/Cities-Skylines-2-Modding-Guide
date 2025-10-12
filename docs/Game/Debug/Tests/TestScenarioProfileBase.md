# Game.Debug.Tests.TestScenarioProfileBase

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class abstract public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

## Fields

- `protected Colossal.IO.AssetDatabase.ILocalAssetDatabase m_TransientDatabase`  
- `protected Game.Simulation.SimulationSystem m_SimulationSystem`  
- `protected Game.Simulation.CitySystem m_CitySystem`  
- `protected Game.Debug.Tests.TestScenarioProfileBase+ManuallyCollectedData m_ManuallyCollectedData`  
- `protected static Game.Debug.Tests.TestScenarioProfileBase+GraphicsQualitySetting[] QualityLevels`  
- `protected static Game.Debug.Tests.TestScenarioProfileBase+CameraDistance[] CameraDistances`  
- `protected static Game.Debug.Tests.TestScenarioProfileBase+SimulationSpeed[] SimulationSpeeds`  
- `protected static const System.String kTestResources`  
- `protected static const System.String kResourcesGroupName`  
- `protected static const System.Int32 kMapLoadTimeout`  

## Constructors

- `protected TestScenarioProfileBase()`  

## Methods

- `protected abstract GetIsMemoryCollector() : System.Boolean`  
- `private GetPerformanceTestDescription(System.String settingsName) : System.Collections.Generic.List<Game.Debug.Tests.TestScenarioProfileBase+PerformanceTestDescription>`  
- `protected abstract GetProfilerStatInfos() : Game.Debug.Tests.TestScenarioProfileBase+StatInfo[]`  
- `private static GetRecorderFrameStats(Unity.Profiling.ProfilerRecorder recorder) : Game.Debug.Tests.TestScenarioProfileBase+PerformanceStatValues`  
- `protected abstract GetRunName(System.String saveName, Game.Debug.Tests.TestScenarioProfileBase+TestConditions testConditions) : System.String`  
- `protected abstract GetSampleCount() : System.Int32`  
- `protected abstract GetTestConditions() : Game.Debug.Tests.TestScenarioProfileBase+TestConditions[]`  
- `protected abstract GetTestSettingsName() : System.String`  
- `protected InitializeDatabase() : System.Void`  
- `protected InitStatString(System.Text.StringBuilder runStringBuilder, Game.Debug.Tests.TestScenarioProfileBase+StatInfo[] stats) : System.Void`  
- `protected OnAddAsset(System.String path) : System.IO.Stream`  
- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  
- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  
- `protected virtual RunTestMethods(System.Threading.CancellationToken cts) : System.Threading.Tasks.Task`  
- `private SetTestConditions(System.String saveName, Game.CameraController cameraController, Game.Debug.Tests.TestScenarioProfileBase+TestConditions testConditions, System.Threading.CancellationToken cts) : System.Threading.Tasks.Task`  
- `protected TestEnd(System.String testName) : System.Void`  
- `protected TestStart(System.String testName) : System.Void`  
- `protected WriteLoadingReport(System.Double loadingTimeMS, System.Boolean res) : System.Void`  
- `protected WriteReport(System.String runName, Game.Debug.Tests.TestScenarioProfileBase+StatInfo[] stats, System.Int32 sampleCount, System.Text.StringBuilder runStringBuilder, System.Int32 averagePopulation) : System.Void`  

## Nested types

- `Game.Debug.Tests.TestScenarioProfileBase+ManuallyCollectedData`  
- `Game.Debug.Tests.TestScenarioProfileBase+CameraInfo`  
- `Game.Debug.Tests.TestScenarioProfileBase+CameraDistance`  
- `Game.Debug.Tests.TestScenarioProfileBase+SimulationSpeed`  
- `Game.Debug.Tests.TestScenarioProfileBase+GraphicsQualitySetting`  
- `Game.Debug.Tests.TestScenarioProfileBase+StatInfo`  
- `Game.Debug.Tests.TestScenarioProfileBase+PerformanceTestDescription`  
- `Game.Debug.Tests.TestScenarioProfileBase+PerformanceTestCollection`  
- `Game.Debug.Tests.TestScenarioProfileBase+TestConditions`  
- `Game.Debug.Tests.TestScenarioProfileBase+PerformanceStatValues`  
- `Game.Debug.Tests.TestScenarioProfileBase+<>c__DisplayClass36_0`  
- `Game.Debug.Tests.TestScenarioProfileBase+<>c__DisplayClass37_0`  
- `Game.Debug.Tests.TestScenarioProfileBase+<OnPrepare>d__34`  
- `Game.Debug.Tests.TestScenarioProfileBase+<RunTestMethods>d__37`  
- `Game.Debug.Tests.TestScenarioProfileBase+<SetTestConditions>d__38`  

