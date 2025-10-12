# Game.Settings.AudioSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`, `SettingsUIGroupOrder`  

## Fields

- `private Game.Audio.AudioManager m_AudioManager`  
- `private Game.Audio.Radio.Radio m_Radio`  
- `private System.Single <masterVolume>k__BackingField`  
- `private System.Single <uiVolume>k__BackingField`  
- `private System.Single <menuVolume>k__BackingField`  
- `private System.Single <ingameVolume>k__BackingField`  
- `private System.Boolean <radioActive>k__BackingField`  
- `private System.Single <radioVolume>k__BackingField`  
- `private System.Single <ambienceVolume>k__BackingField`  
- `private System.Single <disastersVolume>k__BackingField`  
- `private System.Single <worldVolume>k__BackingField`  
- `private System.Single <audioGroupsVolume>k__BackingField`  
- `private System.Single <serviceBuildingsVolume>k__BackingField`  
- `private System.Int32 <clipMemoryBudget>k__BackingField`  
- `public static const System.String kName`  
- `public static const System.String kMainGroup`  
- `public static const System.String kRadioGroup`  
- `public static const System.String kAdvancedGroup`  

## Properties

- `public System.Single masterVolume { get; set }`  
- `public System.Single uiVolume { get; set }`  
- `public System.Single menuVolume { get; set }`  
- `public System.Single ingameVolume { get; set }`  
- `public System.Boolean radioActive { get; set }`  
- `public System.Single radioVolume { get; set }`  
- `public System.Single ambienceVolume { get; set }`  
- `public System.Single disastersVolume { get; set }`  
- `public System.Single worldVolume { get; set }`  
- `public System.Single audioGroupsVolume { get; set }`  
- `public System.Single serviceBuildingsVolume { get; set }`  
- `public System.Int32 clipMemoryBudget { get; set }`  

## Constructors

- `public AudioSettings()`  

## Methods

- `public virtual Apply() : System.Void`  
- `public virtual SetDefaults() : System.Void`  

