# Game.Prefabs.ColorVariation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Fields

- `public Game.Rendering.ColorSet m_ColorSet`  
- `public Game.Rendering.ColorGroupID m_GroupID`  
- `public Game.Rendering.ColorSyncFlags m_SyncFlags`  
- `public Game.Rendering.ColorSourceType m_ColorSourceType`  
- `public System.Byte m_Probability`  
- `public System.SByte m_ExternalChannel0`  
- `public System.SByte m_ExternalChannel1`  
- `public System.SByte m_ExternalChannel2`  
- `public System.Byte m_HueRange`  
- `public System.Byte m_SaturationRange`  
- `public System.Byte m_ValueRange`  
- `public System.Byte m_AlphaRange0`  
- `public System.Byte m_AlphaRange1`  
- `public System.Byte m_AlphaRange2`  

## Properties

- `public System.Boolean hasExternalChannels { get }`  
- `public System.Boolean hasVariationRanges { get }`  
- `public System.Boolean hasAlphaRanges { get }`  

## Methods

- `public GetExternalChannelIndex(System.Int32 colorIndex) : System.Int32`  
- `public SetExternalChannelIndex(System.Int32 colorIndex, System.Int32 channelIndex) : System.Void`  

