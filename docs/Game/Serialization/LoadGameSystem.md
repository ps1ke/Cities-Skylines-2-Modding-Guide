# Game.Serialization.LoadGameSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Fields

- `public Game.Serialization.LoadGameSystem+EventGameLoaded onOnSaveGameLoaded`  
- `private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_TaskCompletionSource`  
- `private Colossal.IO.AssetDatabase.AsyncReadDescriptor <dataDescriptor>k__BackingField`  
- `private Game.UpdateSystem m_UpdateSystem`  
- `private Colossal.Serialization.Entities.Context m_Context`  

## Properties

- `public Colossal.IO.AssetDatabase.AsyncReadDescriptor dataDescriptor { get; set }`  
- `public Colossal.Serialization.Entities.Context context { get; set }`  

## Constructors

- `public LoadGameSystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public RunOnce() : System.Threading.Tasks.Task`  

## Nested types

- `Game.Serialization.LoadGameSystem+EventGameLoaded`  
- `Game.Serialization.LoadGameSystem+<RunOnce>d__13`  

