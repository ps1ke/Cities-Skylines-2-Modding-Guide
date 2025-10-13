# Game.Debug.Tests.StartNewGameSaveLoadAndSaveOnTop

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Code

```csharp
public class StartNewGameSaveLoadAndSaveOnTop : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    private static const System.String kCityName;

    public StartNewGameSaveLoadAndSaveOnTop();

    private System.Threading.Tasks.Task Execute(Colossal.IO.AssetDatabase.ILocalAssetDatabase database);
    protected virtual System.Threading.Tasks.Task OnPrepare();
    private System.Threading.Tasks.Task StartNewGameSaveLoadAndSaveOnTopGdk();
    private System.Threading.Tasks.Task StartNewGameSaveLoadAndSaveOnTopVanilla();
}
```


## Fields

- `private static const System.String kCityName`  

```csharp
private static const System.String kCityName;
```


## Constructors

- `public StartNewGameSaveLoadAndSaveOnTop()`  

```csharp
public StartNewGameSaveLoadAndSaveOnTop();
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

- `private StartNewGameSaveLoadAndSaveOnTopGdk() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task StartNewGameSaveLoadAndSaveOnTopGdk();
```

- `private StartNewGameSaveLoadAndSaveOnTopVanilla() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task StartNewGameSaveLoadAndSaveOnTopVanilla();
```


## Nested types

- `Game.Debug.Tests.StartNewGameSaveLoadAndSaveOnTop+<Execute>d__4`  

