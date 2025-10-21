# Game.Tutorials.EditorTutorialSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialSystem`  
**Implements:** `Game.Tutorials.ITutorialSystem`, `Game.Serialization.IPreDeserialize`  

## Code

```csharp
public class EditorTutorialSystem : Game.Tutorials.TutorialSystem, Game.Tutorials.ITutorialSystem, Game.Serialization.IPreDeserialize
{
    protected System.Collections.Generic.Dictionary<System.String, System.Boolean> ShownTutorials { protected get; }
    public System.Boolean tutorialEnabled { get; set; }

    public EditorTutorialSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode);
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode);
    public virtual System.Void OnResetTutorials();
}
```


## Properties

- `protected System.Collections.Generic.Dictionary<System.String, System.Boolean> ShownTutorials { protected get }`  

```csharp
protected System.Collections.Generic.Dictionary<System.String, System.Boolean> ShownTutorials { protected get; }
```

- `public System.Boolean tutorialEnabled { get; set }`  

```csharp
public System.Boolean tutorialEnabled { get; set; }
```


## Constructors

- `public EditorTutorialSystem()`  

```csharp
public EditorTutorialSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode) : System.Void`  

```csharp
protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode);
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode);
```

- `public virtual OnResetTutorials() : System.Void`  

```csharp
public virtual System.Void OnResetTutorials();
```


