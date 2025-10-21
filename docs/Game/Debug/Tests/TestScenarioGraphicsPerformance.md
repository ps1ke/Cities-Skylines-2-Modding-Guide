# Game.Debug.Tests.TestScenarioGraphicsPerformance

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Game.Debug.Tests.TestScenarioProfileBase`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Code

```csharp
public class TestScenarioGraphicsPerformance : Game.Debug.Tests.TestScenarioProfileBase, Colossal.TestFramework.ITestStep
{
    private Game.Debug.Tests.TestScenarioProfileBase+TestConditions[] m_TestConditionsArray;
    private Game.Debug.Tests.TestScenarioProfileBase+StatInfo[] m_ProfilerStatInfos;
    private static const System.Int32 kNumberOfSamples;

    public TestScenarioGraphicsPerformance();

    protected virtual System.Boolean GetIsMemoryCollector();
    protected virtual Game.Debug.Tests.TestScenarioProfileBase+StatInfo[] GetProfilerStatInfos();
    protected virtual System.String GetRunName(System.String saveName, Game.Debug.Tests.TestScenarioProfileBase+TestConditions testConditions);
    protected virtual System.Int32 GetSampleCount();
    protected virtual Game.Debug.Tests.TestScenarioProfileBase+TestConditions[] GetTestConditions();
    protected virtual System.String GetTestSettingsName();
}
```


## Fields

- `private Game.Debug.Tests.TestScenarioProfileBase+TestConditions[] m_TestConditionsArray`  

```csharp
private Game.Debug.Tests.TestScenarioProfileBase+TestConditions[] m_TestConditionsArray;
```

- `private Game.Debug.Tests.TestScenarioProfileBase+StatInfo[] m_ProfilerStatInfos`  

```csharp
private Game.Debug.Tests.TestScenarioProfileBase+StatInfo[] m_ProfilerStatInfos;
```

- `private static const System.Int32 kNumberOfSamples`  

```csharp
private static const System.Int32 kNumberOfSamples;
```


## Constructors

- `public TestScenarioGraphicsPerformance()`  

```csharp
public TestScenarioGraphicsPerformance();
```


## Methods

- `protected virtual GetIsMemoryCollector() : System.Boolean`  

```csharp
protected virtual System.Boolean GetIsMemoryCollector();
```

- `protected virtual GetProfilerStatInfos() : Game.Debug.Tests.TestScenarioProfileBase+StatInfo[]`  

```csharp
protected virtual Game.Debug.Tests.TestScenarioProfileBase+StatInfo[] GetProfilerStatInfos();
```

- `protected virtual GetRunName(System.String saveName, Game.Debug.Tests.TestScenarioProfileBase+TestConditions testConditions) : System.String`  

```csharp
protected virtual System.String GetRunName(System.String saveName, Game.Debug.Tests.TestScenarioProfileBase+TestConditions testConditions);
```

- `protected virtual GetSampleCount() : System.Int32`  

```csharp
protected virtual System.Int32 GetSampleCount();
```

- `protected virtual GetTestConditions() : Game.Debug.Tests.TestScenarioProfileBase+TestConditions[]`  

```csharp
protected virtual Game.Debug.Tests.TestScenarioProfileBase+TestConditions[] GetTestConditions();
```

- `protected virtual GetTestSettingsName() : System.String`  

```csharp
protected virtual System.String GetTestSettingsName();
```


