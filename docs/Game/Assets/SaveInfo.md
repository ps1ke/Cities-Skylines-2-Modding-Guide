# Game.Assets.SaveInfo

**Assembly:** `Game`  
**Namespace:** `Game.Assets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `Game.Assets.IContentPrerequisite`  

## Fields

- `private Colossal.IO.AssetDatabase.TextureAsset <preview>k__BackingField`  
- `private System.String <theme>k__BackingField`  
- `private System.String <cityName>k__BackingField`  
- `private System.Int32 <population>k__BackingField`  
- `private System.Int32 <money>k__BackingField`  
- `private System.Int32 <xp>k__BackingField`  
- `private Game.Assets.SimulationDateTime <simulationDate>k__BackingField`  
- `private System.Collections.Generic.Dictionary<System.String, System.Boolean> <options>k__BackingField`  
- `private System.String[] <contentPrerequisites>k__BackingField`  
- `private System.String <mapName>k__BackingField`  
- `private Colossal.IO.AssetDatabase.SaveGameData <saveGameData>k__BackingField`  
- `private System.String[] <modsEnabled>k__BackingField`  
- `private System.String <id>k__BackingField`  
- `private System.String <displayName>k__BackingField`  
- `private System.String <path>k__BackingField`  
- `private System.Boolean <isReadonly>k__BackingField`  
- `private System.String <cloudTarget>k__BackingField`  
- `private System.DateTime <lastModified>k__BackingField`  
- `private System.Boolean <autoSave>k__BackingField`  
- `private Game.Assets.SaveGameMetadata <metaData>k__BackingField`  
- `private System.Guid <sessionGuid>k__BackingField`  
- `private System.Boolean <locked>k__BackingField`  
- `private System.String <gameMode>k__BackingField`  

## Properties

- `public Colossal.IO.AssetDatabase.TextureAsset preview { get; set }`  
- `public System.String theme { get; set }`  
- `public System.String cityName { get; set }`  
- `public System.Int32 population { get; set }`  
- `public System.Int32 money { get; set }`  
- `public System.Int32 xp { get; set }`  
- `public Game.Assets.SimulationDateTime simulationDate { get; set }`  
- `public System.Collections.Generic.Dictionary<System.String, System.Boolean> options { get; set }`  
- `public System.String[] contentPrerequisites { get; set }`  
- `public System.String mapName { get; set }`  
- `public Colossal.IO.AssetDatabase.SaveGameData saveGameData { get; set }`  
- `public System.String[] modsEnabled { get; set }`  
- `public System.String id { get; set }`  
- `public System.String displayName { get; set }`  
- `public System.String path { get; set }`  
- `public System.Boolean isReadonly { get; set }`  
- `public System.String cloudTarget { get; set }`  
- `public System.DateTime lastModified { get; set }`  
- `public System.Boolean autoSave { get; set }`  
- `public Game.Assets.SaveGameMetadata metaData { get; set }`  
- `public System.Guid sessionGuid { get; set }`  
- `public System.Boolean locked { get; set }`  
- `public System.String gameMode { get; set }`  

## Constructors

- `public SaveInfo()`  

## Methods

- `public Copy() : Game.Assets.SaveInfo`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

