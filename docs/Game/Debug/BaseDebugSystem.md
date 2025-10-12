# Game.Debug.BaseDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class abstract public  

**Base:** `Game.GameSystemBase`  

## Fields

- `private System.Collections.Generic.List<Game.Debug.BaseDebugSystem+Option> <options>k__BackingField`  

## Properties

- `public System.Collections.Generic.List<Game.Debug.BaseDebugSystem+Option> options { get; private set }`  

## Constructors

- `protected BaseDebugSystem()`  

## Methods

- `protected AddOption(System.String displayName, System.Boolean defaultEnabled) : Game.Debug.BaseDebugSystem+Option`  
- `protected virtual OnCreate() : System.Void`  
- `public virtual OnDisabled(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  
- `public virtual OnEnabled(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Debug.BaseDebugSystem+Option`  

