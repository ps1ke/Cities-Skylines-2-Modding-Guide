# Game.Audio.Radio.Radio+RuntimeRadioChannel

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IComparable<Game.Audio.Radio.Radio+RuntimeRadioChannel>`, `Colossal.UI.Binding.IJsonWritable`  

## Fields

- `public System.String name`  
- `public System.String description`  
- `public System.String icon`  
- `public System.Int32 uiPriority`  
- `public System.String network`  
- `private Game.Audio.Radio.Radio+RuntimeProgram <currentProgram>k__BackingField`  
- `private Game.Audio.Radio.Radio+RuntimeProgram[] <schedule>k__BackingField`  
- `private readonly Game.Audio.Radio.Radio+RuntimeProgram kNoProgram`  

## Properties

- `public Game.Audio.Radio.Radio+RuntimeProgram currentProgram { get; private set }`  
- `public Game.Audio.Radio.Radio+RuntimeProgram[] schedule { get; private set }`  

## Constructors

- `public RuntimeRadioChannel()`  

## Methods

- `private AddRuntimeProgram(Game.Audio.Radio.Radio+Program p, System.Int32 startSecs, System.Int32 endSecs, System.Collections.Generic.List<Game.Audio.Radio.Radio+RuntimeProgram> schedule, System.String path) : System.Void`  
- `private BuildRuntimePrograms(Game.Audio.Radio.Radio+Program[] programs, System.String path) : System.Void`  
- `public CompareTo(Game.Audio.Radio.Radio+RuntimeRadioChannel other) : System.Int32`  
- `private CreateRuntimeProgram(Game.Audio.Radio.Radio+Program p, System.Int32 startSecs, System.Int32 endSecs, System.String path) : Game.Audio.Radio.Radio+RuntimeProgram`  
- `public Initialize(Game.Audio.Radio.Radio+RadioChannel radioChannel, System.String path) : System.Void`  
- `private IsValidTimestamp(System.Int32 start, System.Int32 end) : System.Boolean`  
- `private ShallowCopyRuntimeProgram(Game.Audio.Radio.Radio+RuntimeProgram p, System.Int32 startSecs, System.Int32 endSecs) : Game.Audio.Radio.Radio+RuntimeProgram`  
- `public Update(System.Int32 timeOfDaySeconds) : System.Boolean`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

