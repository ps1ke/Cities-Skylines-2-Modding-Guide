# Game.Prefabs.ColorVariation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct ColorVariation : Unity.Entities.IBufferElementData
{
    public Game.Rendering.ColorSet m_ColorSet;
    public Game.Rendering.ColorGroupID m_GroupID;
    public Game.Rendering.ColorSyncFlags m_SyncFlags;
    public Game.Rendering.ColorSourceType m_ColorSourceType;
    public System.Byte m_Probability;
    public System.SByte m_ExternalChannel0;
    public System.SByte m_ExternalChannel1;
    public System.SByte m_ExternalChannel2;
    public System.Byte m_HueRange;
    public System.Byte m_SaturationRange;
    public System.Byte m_ValueRange;
    public System.Byte m_AlphaRange0;
    public System.Byte m_AlphaRange1;
    public System.Byte m_AlphaRange2;

    public System.Boolean hasExternalChannels { get; }
    public System.Boolean hasVariationRanges { get; }
    public System.Boolean hasAlphaRanges { get; }

    public System.Int32 GetExternalChannelIndex(System.Int32 colorIndex);
    public System.Void SetExternalChannelIndex(System.Int32 colorIndex, System.Int32 channelIndex);
}
```


## Fields

- `public Game.Rendering.ColorSet m_ColorSet`  

```csharp
public Game.Rendering.ColorSet m_ColorSet;
```

- `public Game.Rendering.ColorGroupID m_GroupID`  

```csharp
public Game.Rendering.ColorGroupID m_GroupID;
```

- `public Game.Rendering.ColorSyncFlags m_SyncFlags`  

```csharp
public Game.Rendering.ColorSyncFlags m_SyncFlags;
```

- `public Game.Rendering.ColorSourceType m_ColorSourceType`  

```csharp
public Game.Rendering.ColorSourceType m_ColorSourceType;
```

- `public System.Byte m_Probability`  

```csharp
public System.Byte m_Probability;
```

- `public System.SByte m_ExternalChannel0`  

```csharp
public System.SByte m_ExternalChannel0;
```

- `public System.SByte m_ExternalChannel1`  

```csharp
public System.SByte m_ExternalChannel1;
```

- `public System.SByte m_ExternalChannel2`  

```csharp
public System.SByte m_ExternalChannel2;
```

- `public System.Byte m_HueRange`  

```csharp
public System.Byte m_HueRange;
```

- `public System.Byte m_SaturationRange`  

```csharp
public System.Byte m_SaturationRange;
```

- `public System.Byte m_ValueRange`  

```csharp
public System.Byte m_ValueRange;
```

- `public System.Byte m_AlphaRange0`  

```csharp
public System.Byte m_AlphaRange0;
```

- `public System.Byte m_AlphaRange1`  

```csharp
public System.Byte m_AlphaRange1;
```

- `public System.Byte m_AlphaRange2`  

```csharp
public System.Byte m_AlphaRange2;
```


## Properties

- `public System.Boolean hasExternalChannels { get }`  

```csharp
public System.Boolean hasExternalChannels { get; }
```

- `public System.Boolean hasVariationRanges { get }`  

```csharp
public System.Boolean hasVariationRanges { get; }
```

- `public System.Boolean hasAlphaRanges { get }`  

```csharp
public System.Boolean hasAlphaRanges { get; }
```


## Methods

- `public GetExternalChannelIndex(System.Int32 colorIndex) : System.Int32`  

```csharp
public int GetExternalChannelIndex(int colorIndex)
	{
		return colorIndex switch
		{
			0 => m_ExternalChannel0, 
			1 => m_ExternalChannel1, 
			2 => m_ExternalChannel2, 
			_ => -1, 
		};
	}
```

- `public SetExternalChannelIndex(System.Int32 colorIndex, System.Int32 channelIndex) : System.Void`  

```csharp
public void SetExternalChannelIndex(int colorIndex, int channelIndex)
	{
		switch (colorIndex)
		{
		case 0:
			m_ExternalChannel0 = (sbyte)channelIndex;
			break;
		case 1:
			m_ExternalChannel1 = (sbyte)channelIndex;
			break;
		case 2:
			m_ExternalChannel2 = (sbyte)channelIndex;
			break;
		}
	}
```


