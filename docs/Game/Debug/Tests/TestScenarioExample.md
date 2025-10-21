# Game.Debug.Tests.TestScenarioExample

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

## Code

```csharp
public class TestScenarioExample : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    public TestScenarioExample();

    protected virtual System.Threading.Tasks.Task OnCleanup();
    protected virtual System.Threading.Tasks.Task OnPrepare();
    private System.Void TestCleanup();
    private System.Threading.Tasks.Task TestExampleAsync();
    private System.Void TestExampleVoid();
    private System.Void TestPrepare();
}
```


## Constructors

- `public TestScenarioExample()`  

```csharp
public TestScenarioExample();
```


## Methods

- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnCleanup();
```

- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnPrepare();
```

- `private TestCleanup() : System.Void`  

```csharp
private System.Void TestCleanup();
```

- `private TestExampleAsync() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task TestExampleAsync();
```

- `private TestExampleVoid() : System.Void`  

```csharp
private System.Void TestExampleVoid();
```

- `private TestPrepare() : System.Void`  

```csharp
private System.Void TestPrepare();
```


## Nested types

- `Game.Debug.Tests.TestScenarioExample+<OnCleanup>d__1`  
- `Game.Debug.Tests.TestScenarioExample+<OnPrepare>d__0`  
- `Game.Debug.Tests.TestScenarioExample+<TestExampleAsync>d__5`  

