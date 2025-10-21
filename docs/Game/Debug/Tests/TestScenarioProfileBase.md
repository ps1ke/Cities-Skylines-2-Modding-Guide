# Game.Debug.Tests.TestScenarioProfileBase

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class abstract public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

## Code

```csharp
public abstract class TestScenarioProfileBase : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    protected Colossal.IO.AssetDatabase.ILocalAssetDatabase m_TransientDatabase;
    protected Game.Simulation.SimulationSystem m_SimulationSystem;
    protected Game.Simulation.CitySystem m_CitySystem;
    protected Game.Debug.Tests.TestScenarioProfileBase+ManuallyCollectedData m_ManuallyCollectedData;
    protected static Game.Debug.Tests.TestScenarioProfileBase+GraphicsQualitySetting[] QualityLevels;
    protected static Game.Debug.Tests.TestScenarioProfileBase+CameraDistance[] CameraDistances;
    protected static Game.Debug.Tests.TestScenarioProfileBase+SimulationSpeed[] SimulationSpeeds;
    protected static const System.String kTestResources;
    protected static const System.String kResourcesGroupName;
    protected static const System.Int32 kMapLoadTimeout;

    protected TestScenarioProfileBase();

    protected abstract System.Boolean GetIsMemoryCollector();
    private System.Collections.Generic.List<Game.Debug.Tests.TestScenarioProfileBase+PerformanceTestDescription> GetPerformanceTestDescription(System.String settingsName);
    protected abstract Game.Debug.Tests.TestScenarioProfileBase+StatInfo[] GetProfilerStatInfos();
    private static Game.Debug.Tests.TestScenarioProfileBase+PerformanceStatValues GetRecorderFrameStats(Unity.Profiling.ProfilerRecorder recorder);
    protected abstract System.String GetRunName(System.String saveName, Game.Debug.Tests.TestScenarioProfileBase+TestConditions testConditions);
    protected abstract System.Int32 GetSampleCount();
    protected abstract Game.Debug.Tests.TestScenarioProfileBase+TestConditions[] GetTestConditions();
    protected abstract System.String GetTestSettingsName();
    protected System.Void InitializeDatabase();
    protected System.Void InitStatString(System.Text.StringBuilder runStringBuilder, Game.Debug.Tests.TestScenarioProfileBase+StatInfo[] stats);
    protected System.IO.Stream OnAddAsset(System.String path);
    protected virtual System.Threading.Tasks.Task OnCleanup();
    protected virtual System.Threading.Tasks.Task OnPrepare();
    protected virtual System.Threading.Tasks.Task RunTestMethods(System.Threading.CancellationToken cts);
    private System.Threading.Tasks.Task SetTestConditions(System.String saveName, Game.CameraController cameraController, Game.Debug.Tests.TestScenarioProfileBase+TestConditions testConditions, System.Threading.CancellationToken cts);
    protected System.Void TestEnd(System.String testName);
    protected System.Void TestStart(System.String testName);
    protected System.Void WriteLoadingReport(System.Double loadingTimeMS, System.Boolean res);
    protected System.Void WriteReport(System.String runName, Game.Debug.Tests.TestScenarioProfileBase+StatInfo[] stats, System.Int32 sampleCount, System.Text.StringBuilder runStringBuilder, System.Int32 averagePopulation);
}
```


## Fields

- `protected Colossal.IO.AssetDatabase.ILocalAssetDatabase m_TransientDatabase`  

```csharp
protected Colossal.IO.AssetDatabase.ILocalAssetDatabase m_TransientDatabase;
```

- `protected Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
protected Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `protected Game.Simulation.CitySystem m_CitySystem`  

```csharp
protected Game.Simulation.CitySystem m_CitySystem;
```

- `protected Game.Debug.Tests.TestScenarioProfileBase+ManuallyCollectedData m_ManuallyCollectedData`  

```csharp
protected Game.Debug.Tests.TestScenarioProfileBase+ManuallyCollectedData m_ManuallyCollectedData;
```

- `protected static Game.Debug.Tests.TestScenarioProfileBase+GraphicsQualitySetting[] QualityLevels`  

```csharp
protected static Game.Debug.Tests.TestScenarioProfileBase+GraphicsQualitySetting[] QualityLevels;
```

- `protected static Game.Debug.Tests.TestScenarioProfileBase+CameraDistance[] CameraDistances`  

```csharp
protected static Game.Debug.Tests.TestScenarioProfileBase+CameraDistance[] CameraDistances;
```

- `protected static Game.Debug.Tests.TestScenarioProfileBase+SimulationSpeed[] SimulationSpeeds`  

```csharp
protected static Game.Debug.Tests.TestScenarioProfileBase+SimulationSpeed[] SimulationSpeeds;
```

- `protected static const System.String kTestResources`  

```csharp
protected static const System.String kTestResources;
```

- `protected static const System.String kResourcesGroupName`  

```csharp
protected static const System.String kResourcesGroupName;
```

- `protected static const System.Int32 kMapLoadTimeout`  

```csharp
protected static const System.Int32 kMapLoadTimeout;
```


## Constructors

- `protected TestScenarioProfileBase()`  

```csharp
protected TestScenarioProfileBase();
```


## Methods

- `protected abstract GetIsMemoryCollector() : System.Boolean`  

```csharp
protected abstract System.Boolean GetIsMemoryCollector();
```

- `private GetPerformanceTestDescription(System.String settingsName) : System.Collections.Generic.List<Game.Debug.Tests.TestScenarioProfileBase+PerformanceTestDescription>`  

```csharp
private System.Collections.Generic.List<Game.Debug.Tests.TestScenarioProfileBase+PerformanceTestDescription> GetPerformanceTestDescription(System.String settingsName);
```

- `protected abstract GetProfilerStatInfos() : Game.Debug.Tests.TestScenarioProfileBase+StatInfo[]`  

```csharp
protected abstract Game.Debug.Tests.TestScenarioProfileBase+StatInfo[] GetProfilerStatInfos();
```

- `private static GetRecorderFrameStats(Unity.Profiling.ProfilerRecorder recorder) : Game.Debug.Tests.TestScenarioProfileBase+PerformanceStatValues`  

```csharp
private static Game.Debug.Tests.TestScenarioProfileBase+PerformanceStatValues GetRecorderFrameStats(Unity.Profiling.ProfilerRecorder recorder);
```

- `protected abstract GetRunName(System.String saveName, Game.Debug.Tests.TestScenarioProfileBase+TestConditions testConditions) : System.String`  

```csharp
protected abstract System.String GetRunName(System.String saveName, Game.Debug.Tests.TestScenarioProfileBase+TestConditions testConditions);
```

- `protected abstract GetSampleCount() : System.Int32`  

```csharp
protected abstract System.Int32 GetSampleCount();
```

- `protected abstract GetTestConditions() : Game.Debug.Tests.TestScenarioProfileBase+TestConditions[]`  

```csharp
protected abstract Game.Debug.Tests.TestScenarioProfileBase+TestConditions[] GetTestConditions();
```

- `protected abstract GetTestSettingsName() : System.String`  

```csharp
protected abstract System.String GetTestSettingsName();
```

- `protected InitializeDatabase() : System.Void`  

```csharp
protected System.Void InitializeDatabase();
```

- `protected InitStatString(System.Text.StringBuilder runStringBuilder, Game.Debug.Tests.TestScenarioProfileBase+StatInfo[] stats) : System.Void`  

```csharp
protected System.Void InitStatString(System.Text.StringBuilder runStringBuilder, Game.Debug.Tests.TestScenarioProfileBase+StatInfo[] stats);
```

- `protected OnAddAsset(System.String path) : System.IO.Stream`  

```csharp
protected System.IO.Stream OnAddAsset(System.String path);
```

- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnCleanup();
```

- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnPrepare();
```

- `protected virtual RunTestMethods(System.Threading.CancellationToken cts) : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task RunTestMethods(System.Threading.CancellationToken cts);
```

- `private SetTestConditions(System.String saveName, Game.CameraController cameraController, Game.Debug.Tests.TestScenarioProfileBase+TestConditions testConditions, System.Threading.CancellationToken cts) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task SetTestConditions(System.String saveName, Game.CameraController cameraController, Game.Debug.Tests.TestScenarioProfileBase+TestConditions testConditions, System.Threading.CancellationToken cts);
```

- `protected TestEnd(System.String testName) : System.Void`  

```csharp
protected System.Void TestEnd(System.String testName);
```

- `protected TestStart(System.String testName) : System.Void`  

```csharp
protected System.Void TestStart(System.String testName);
```

- `protected WriteLoadingReport(System.Double loadingTimeMS, System.Boolean res) : System.Void`  

```csharp
protected System.Void WriteLoadingReport(System.Double loadingTimeMS, System.Boolean res);
```

- `protected WriteReport(System.String runName, Game.Debug.Tests.TestScenarioProfileBase+StatInfo[] stats, System.Int32 sampleCount, System.Text.StringBuilder runStringBuilder, System.Int32 averagePopulation) : System.Void`  

```csharp
protected System.Void WriteReport(System.String runName, Game.Debug.Tests.TestScenarioProfileBase+StatInfo[] stats, System.Int32 sampleCount, System.Text.StringBuilder runStringBuilder, System.Int32 averagePopulation);
```


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

