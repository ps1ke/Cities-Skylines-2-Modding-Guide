# Game.Settings.UserState

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`  

## Fields

- `private System.Collections.Generic.Dictionary<System.String, System.Boolean> <shownTutorials>k__BackingField`  
- `private Game.Assets.SaveGameMetadata <lastSaveGameMetadata>k__BackingField`  
- `private System.String <lastCloudTarget>k__BackingField`  
- `private System.Boolean <leftHandTraffic>k__BackingField`  
- `private System.Boolean <naturalDisasters>k__BackingField`  
- `private System.Boolean <unlockAll>k__BackingField`  
- `private System.Boolean <unlimitedMoney>k__BackingField`  
- `private System.Boolean <unlockMapTiles>k__BackingField`  
- `private System.Collections.Generic.List<System.String> <seenWhatsNew>k__BackingField`  

## Properties

- `public System.Collections.Generic.Dictionary<System.String, System.Boolean> shownTutorials { get; set }`  
- `public Game.Assets.SaveGameMetadata lastSaveGameMetadata { get; set }`  
- `public System.String lastCloudTarget { get; set }`  
- `public System.Boolean leftHandTraffic { get; set }`  
- `public System.Boolean naturalDisasters { get; set }`  
- `public System.Boolean unlockAll { get; set }`  
- `public System.Boolean unlimitedMoney { get; set }`  
- `public System.Boolean unlockMapTiles { get; set }`  
- `public System.Collections.Generic.List<System.String> seenWhatsNew { get; set }`  

## Constructors

- `public UserState()`  

## Methods

- `private GetDefaultCloudTarget() : System.String`  
- `public ResetTutorials() : System.Void`  
- `public virtual SetDefaults() : System.Void`  

