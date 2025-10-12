# Game.Rendering.WindTextureSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Fields

- `private Game.Simulation.WindSystem m_WindSystem`  
- `private UnityEngine.Texture2D m_WindTexture`  
- `private Unity.Jobs.JobHandle m_UpdateHandle`  
- `private System.Boolean m_RequireUpdate`  
- `private System.Boolean m_RequireApply`  

## Properties

- `public UnityEngine.Texture2D WindTexture { get }`  

## Constructors

- `public WindTextureSystem()`  

## Methods

- `public CompleteUpdate() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public RequireUpdate() : System.Void`  

## Nested types

- `Game.Rendering.WindTextureSystem+WindTextureJob`  

