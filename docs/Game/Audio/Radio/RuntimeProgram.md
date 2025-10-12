# Game.Audio.Radio.Radio+RuntimeProgram

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Fields

- `public System.String name`  
- `public System.String description`  
- `public System.Int32 startTime`  
- `public System.Int32 endTime`  
- `public System.Boolean loopProgram`  
- `public System.Boolean active`  
- `public System.Boolean hasEnded`  
- `private System.Int32 m_CurrentSegmentId`  
- `private System.Collections.Generic.List<Game.Audio.Radio.Radio+RuntimeSegment> m_Segments`  

## Properties

- `public System.Int32 duration { get }`  
- `public Game.Audio.Radio.Radio+RuntimeSegment currentSegment { get }`  
- `public System.Collections.Generic.IReadOnlyList<Game.Audio.Radio.Radio+RuntimeSegment> segments { get; set }`  

## Constructors

- `public RuntimeProgram()`  

## Methods

- `public BuildRuntimeSegments(Game.Audio.Radio.Radio+Program program, System.String path) : System.Void`  
- `private GetClips(System.Int32 count, System.Func<System.Int32, System.Int32> rand, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AudioAsset> clips) : Colossal.IO.AssetDatabase.AudioAsset[]`  
- `public GoToNextSegment() : System.Boolean`  
- `public Reset() : System.Void`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.Audio.Radio.Radio+RuntimeProgram+<>c`  
- `Game.Audio.Radio.Radio+RuntimeProgram+<>c__DisplayClass19_0`  
- `Game.Audio.Radio.Radio+RuntimeProgram+<>c__DisplayClass19_1`  

