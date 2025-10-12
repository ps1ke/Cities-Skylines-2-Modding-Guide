# Game.Audio.Radio.Radio+RuntimeSegment

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `public Game.Audio.Radio.Radio+SegmentType type`  
- `public System.String[] tags`  
- `public System.Int32 clipsCap`  
- `private System.Int32 m_CapCount`  
- `private System.Int32 m_CurrentClipId`  
- `private System.Boolean <isSetUp>k__BackingField`  
- `private System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AudioAsset> m_Clips`  
- `private System.Double <durationMs>k__BackingField`  

## Properties

- `public Colossal.IO.AssetDatabase.AudioAsset currentClip { get }`  
- `public System.Boolean isSetUp { get; private set }`  
- `public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AudioAsset> clips { get; set }`  
- `public System.Double durationMs { get; private set }`  

## Constructors

- `public RuntimeSegment()`  

## Methods

- `public GoToNextClip() : System.Boolean`  
- `public GoToPreviousClip() : System.Boolean`  
- `public Reset() : System.Void`  
- `public Setup(Game.Audio.Radio.Radio+OnDemandClips clipsCallback = null) : System.Void`  

