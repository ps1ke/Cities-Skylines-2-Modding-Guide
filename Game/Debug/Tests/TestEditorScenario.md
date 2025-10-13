# Game.Debug.Tests.TestEditorScenario

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Code

```csharp
public class TestEditorScenario : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    public TestEditorScenario();

    protected virtual System.Threading.Tasks.Task OnPrepare();
    private System.Threading.Tasks.Task StartEditorAndCycleModes();
    private System.Threading.Tasks.Task StartEditorAndGoBackToMainMenu();
    private System.Threading.Tasks.Task StartEditorAndLoadSaveMapAndStartGame();
}
```


## Constructors

- `public TestEditorScenario()`  

```csharp
public TestEditorScenario();
```


## Methods

- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnPrepare();
```

- `private StartEditorAndCycleModes() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task StartEditorAndCycleModes();
```

- `private StartEditorAndGoBackToMainMenu() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task StartEditorAndGoBackToMainMenu();
```

- `private StartEditorAndLoadSaveMapAndStartGame() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task StartEditorAndLoadSaveMapAndStartGame();
```


## Nested types

- `Game.Debug.Tests.TestEditorScenario+<>c__DisplayClass3_0`  
- `Game.Debug.Tests.TestEditorScenario+<StartEditorAndCycleModes>d__2`  
- `Game.Debug.Tests.TestEditorScenario+<StartEditorAndGoBackToMainMenu>d__1`  
- `Game.Debug.Tests.TestEditorScenario+<StartEditorAndLoadSaveMapAndStartGame>d__3`  

