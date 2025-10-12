# Game.Serialization.SaveGameSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Fields

- `private System.IO.Stream <stream>k__BackingField`  
- `private Unity.Collections.NativeArray<Unity.Entities.Entity> <referencedContent>k__BackingField`  
- `private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_TaskCompletionSource`  
- `private Game.UpdateSystem m_UpdateSystem`  
- `private Game.Serialization.WriteSystem m_WriteSystem`  
- `private System.Boolean m_Writing`  
- `private Colossal.Serialization.Entities.Context m_Context`  

## Properties

- `public System.IO.Stream stream { get; set }`  
- `public Colossal.Serialization.Entities.Context context { get; set }`  
- `public Unity.Collections.NativeArray<Unity.Entities.Entity> referencedContent { get; set }`  

## Constructors

- `public SaveGameSystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public RunOnce() : System.Threading.Tasks.Task`  

## Nested types

- `Game.Serialization.SaveGameSystem+<RunOnce>d__18`  

