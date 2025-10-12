# Game.Tutorials.EditorTutorialSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialSystem`  
**Implements:** `Game.Tutorials.ITutorialSystem`, `Game.Serialization.IPreDeserialize`  

## Properties

- `protected System.Collections.Generic.Dictionary<System.String, System.Boolean> ShownTutorials { protected get }`  
- `public System.Boolean tutorialEnabled { get; set }`  

## Constructors

- `public EditorTutorialSystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode) : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode) : System.Void`  
- `public virtual OnResetTutorials() : System.Void`  

