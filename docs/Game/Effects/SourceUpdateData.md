# Game.Effects.SourceUpdateData

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Collections.NativeQueue<Game.Effects.SourceUpdateInfo> m_SourceUpdateQueue`  

## Constructors

- `public SourceUpdateData(Unity.Collections.NativeQueue<Game.Effects.SourceUpdateInfo> sourceUpdateQueue)`  

## Methods

- `public Add(Unity.Entities.Entity entity, Game.Objects.Transform transform) : System.Void`  
- `public Add(Game.Effects.SourceInfo sourceInfo) : System.Void`  
- `public AddSnap() : System.Void`  
- `public AddTemp(Unity.Entities.Entity prefab, Game.Objects.Transform transform) : System.Void`  
- `public Remove(Unity.Entities.Entity entity) : System.Void`  
- `public Remove(Game.Effects.SourceInfo sourceInfo) : System.Void`  
- `public WrongPrefab(Game.Effects.SourceInfo sourceInfo) : System.Void`  

