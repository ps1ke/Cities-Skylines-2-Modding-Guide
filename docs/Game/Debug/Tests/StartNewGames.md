# Game.Debug.Tests.StartNewGames

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Code

```csharp
public class StartNewGames : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    private static const System.String kCityName;

    public StartNewGames();

    private System.Threading.Tasks.Task Execute(Game.Assets.MapMetadata mapMeta);
    protected virtual System.Threading.Tasks.Task OnPrepare();
    private System.Threading.Tasks.Task TestAllMaps();
}
```


## Fields

- `private static const System.String kCityName`  

```csharp
private static const System.String kCityName;
```


## Constructors

- `public StartNewGames()`  

```csharp
public StartNewGames();
```


## Methods

- `private Execute(Game.Assets.MapMetadata mapMeta) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task Execute(Game.Assets.MapMetadata mapMeta);
```

- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnPrepare();
```

- `private TestAllMaps() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task TestAllMaps();
```


## Nested types

- `Game.Debug.Tests.StartNewGames+<>c`  
- `Game.Debug.Tests.StartNewGames+<Execute>d__3`  
- `Game.Debug.Tests.StartNewGames+<TestAllMaps>d__2`  

