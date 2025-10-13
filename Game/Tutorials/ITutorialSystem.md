# Game.Tutorials.ITutorialSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ITutorialSystem
{
    public Unity.Entities.Entity activeTutorial { get; }
    public Unity.Entities.Entity activeTutorialPhase { get; }
    public Unity.Entities.Entity activeTutorialList { get; }
    public System.Boolean tutorialEnabled { get; set; }
    public Game.Tutorials.TutorialMode mode { get; set; }
    public Unity.Entities.Entity tutorialPending { get; }
    public Unity.Entities.Entity nextListTutorial { get; }
    public System.Boolean showListReminder { get; }

    public abstract System.Void CompleteCurrentTutorialPhase();
    public abstract System.Void CompleteTutorial(Unity.Entities.Entity tutorial);
    public abstract System.Void ForceTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean advisorActivation);
    public abstract System.Void SetTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase);
}
```


## Properties

- `public Unity.Entities.Entity activeTutorial { get }`  

```csharp
public Unity.Entities.Entity activeTutorial { get; }
```

- `public Unity.Entities.Entity activeTutorialPhase { get }`  

```csharp
public Unity.Entities.Entity activeTutorialPhase { get; }
```

- `public Unity.Entities.Entity activeTutorialList { get }`  

```csharp
public Unity.Entities.Entity activeTutorialList { get; }
```

- `public System.Boolean tutorialEnabled { get; set }`  

```csharp
public System.Boolean tutorialEnabled { get; set; }
```

- `public Game.Tutorials.TutorialMode mode { get; set }`  

```csharp
public Game.Tutorials.TutorialMode mode { get; set; }
```

- `public Unity.Entities.Entity tutorialPending { get }`  

```csharp
public Unity.Entities.Entity tutorialPending { get; }
```

- `public Unity.Entities.Entity nextListTutorial { get }`  

```csharp
public Unity.Entities.Entity nextListTutorial { get; }
```

- `public System.Boolean showListReminder { get }`  

```csharp
public System.Boolean showListReminder { get; }
```


## Methods

- `public abstract CompleteCurrentTutorialPhase() : System.Void`  

```csharp
public abstract System.Void CompleteCurrentTutorialPhase();
```

- `public abstract CompleteTutorial(Unity.Entities.Entity tutorial) : System.Void`  

```csharp
public abstract System.Void CompleteTutorial(Unity.Entities.Entity tutorial);
```

- `public abstract ForceTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean advisorActivation) : System.Void`  

```csharp
public abstract System.Void ForceTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean advisorActivation);
```

- `public abstract SetTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase) : System.Void`  

```csharp
public abstract System.Void SetTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase);
```


