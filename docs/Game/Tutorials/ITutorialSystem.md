# Game.Tutorials.ITutorialSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** interface abstract public  


## Properties

- `public Unity.Entities.Entity activeTutorial { get }`  
- `public Unity.Entities.Entity activeTutorialPhase { get }`  
- `public Unity.Entities.Entity activeTutorialList { get }`  
- `public System.Boolean tutorialEnabled { get; set }`  
- `public Game.Tutorials.TutorialMode mode { get; set }`  
- `public Unity.Entities.Entity tutorialPending { get }`  
- `public Unity.Entities.Entity nextListTutorial { get }`  
- `public System.Boolean showListReminder { get }`  

## Methods

- `public abstract CompleteCurrentTutorialPhase() : System.Void`  
- `public abstract CompleteTutorial(Unity.Entities.Entity tutorial) : System.Void`  
- `public abstract ForceTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean advisorActivation) : System.Void`  
- `public abstract SetTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase) : System.Void`  

