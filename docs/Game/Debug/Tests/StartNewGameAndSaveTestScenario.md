# Game.Debug.Tests.StartNewGameAndSaveTestScenario

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Code

```csharp
public class StartNewGameAndSaveTestScenario : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    private static const System.String kCityName;

    public StartNewGameAndSaveTestScenario();

    private System.Threading.Tasks.Task Execute(Colossal.IO.AssetDatabase.ILocalAssetDatabase database);
    protected virtual System.Threading.Tasks.Task OnPrepare();
    private System.Threading.Tasks.Task StartNewGameAndSaveTestGdk();
    private System.Threading.Tasks.Task StartNewGameAndSaveTestVanilla();
}
```


## Fields

- `private static const System.String kCityName`  

```csharp
private static const System.String kCityName;
```


## Constructors

- `public StartNewGameAndSaveTestScenario()`  

```csharp
public StartNewGameAndSaveTestScenario();
```


## Methods

- `private Execute(Colossal.IO.AssetDatabase.ILocalAssetDatabase database) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task Execute(Colossal.IO.AssetDatabase.ILocalAssetDatabase database);
```

- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnPrepare();
```

- `private StartNewGameAndSaveTestGdk() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task StartNewGameAndSaveTestGdk();
```

- `private StartNewGameAndSaveTestVanilla() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task StartNewGameAndSaveTestVanilla();
```


## Nested types

- `Game.Debug.Tests.StartNewGameAndSaveTestScenario+<Execute>d__4`  

