# Game.Rendering.Utilities.State+Result

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Utilities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct Result
{
    public Game.Rendering.Utilities.State+ResultType type;
    public Game.Rendering.Utilities.State next;

    public System.Boolean isContinue { get; }
    public System.Boolean isStop { get; }
    public System.Boolean isTransition { get; }
    public static Game.Rendering.Utilities.State+Result Continue { get; }
    public static Game.Rendering.Utilities.State+Result Stop { get; }

    public static Game.Rendering.Utilities.State+Result TransitionTo(Game.Rendering.Utilities.State state);
}
```


## Fields

- `public Game.Rendering.Utilities.State+ResultType type`  

```csharp
public Game.Rendering.Utilities.State+ResultType type;
```

- `public Game.Rendering.Utilities.State next`  

```csharp
public Game.Rendering.Utilities.State next;
```


## Properties

- `public System.Boolean isContinue { get }`  

```csharp
public System.Boolean isContinue { get; }
```

- `public System.Boolean isStop { get }`  

```csharp
public System.Boolean isStop { get; }
```

- `public System.Boolean isTransition { get }`  

```csharp
public System.Boolean isTransition { get; }
```

- `public static Game.Rendering.Utilities.State+Result Continue { get }`  

```csharp
public static Game.Rendering.Utilities.State+Result Continue { get; }
```

- `public static Game.Rendering.Utilities.State+Result Stop { get }`  

```csharp
public static Game.Rendering.Utilities.State+Result Stop { get; }
```


## Methods

- `public static TransitionTo(Game.Rendering.Utilities.State state) : Game.Rendering.Utilities.State+Result`  

```csharp
public static Game.Rendering.Utilities.State+Result TransitionTo(Game.Rendering.Utilities.State state);
```


