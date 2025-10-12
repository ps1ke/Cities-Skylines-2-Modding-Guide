# Game.UI.InGame.AttractivenessSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Single <baseAttractiveness>k__BackingField`  
- `private System.Single <attractiveness>k__BackingField`  
- `private System.Collections.Generic.List<Game.UI.InGame.AttractivenessSection+AttractivenessFactor> <factors>k__BackingField`  
- `private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Unity.Entities.EntityQuery m_SettingsQuery`  

## Properties

- `protected System.String group { protected get }`  
- `private System.Single baseAttractiveness { private get; private set }`  
- `private System.Single attractiveness { private get; private set }`  
- `private System.Collections.Generic.List<Game.UI.InGame.AttractivenessSection+AttractivenessFactor> factors { private get; private set }`  

## Constructors

- `public AttractivenessSection()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

## Nested types

- `Game.UI.InGame.AttractivenessSection+AttractivenessFactor`  

