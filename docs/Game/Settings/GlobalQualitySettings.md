# Game.Settings.GlobalQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.GlobalQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

## Fields

- `private System.Collections.Generic.List<Game.Settings.QualitySetting> m_QualitySettings`  
- `protected static readonly System.Collections.Generic.Dictionary<System.Type, Game.Settings.QualitySetting+Level> s_DefaultsMap`  

## Properties

- `public System.Collections.Generic.List<Game.Settings.QualitySetting> qualitySettings { get; set }`  
- `public System.Int32 countQualitySettings { get }`  
- `public Game.Settings.QualitySetting lastSetting { get }`  

## Constructors

- `public GlobalQualitySettings()`  

## Methods

- `public AddQualitySetting<T>(T setting) : System.Void`  
- `public EnumerateQualitySettings() : System.Collections.Generic.IEnumerable<Game.Settings.QualitySetting>`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public GetQualitySetting<T>() : T`  
- `public GetQualitySetting(System.Type type) : Game.Settings.QualitySetting`  
- `public virtual SetDefaults() : System.Void`  
- `public virtual SetLevel(Game.Settings.QualitySetting+Level quality, System.Boolean apply = True) : System.Void`  

## Nested types

- `Game.Settings.GlobalQualitySettings+<>c__DisplayClass3_0`  
- `Game.Settings.GlobalQualitySettings+<EnumerateQualitySettings>d__11`  

