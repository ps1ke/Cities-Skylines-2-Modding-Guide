# Game.Rendering.Debug.CharacterGroupRenderer

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Debug`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Code

```csharp
public class CharacterGroupRenderer : UnityEngine.MonoBehaviour
{
    public Game.Prefabs.CharacterGroup m_Prefab;
    public System.Boolean m_NoVT;
    public System.Int32 m_CharacterIndex;
    public System.Int32 m_OverlayColorIndex;
    private UnityEngine.GameObject m_Root;
    private UnityEngine.ComputeBuffer m_BoneBuffer;
    private UnityEngine.ComputeBuffer m_BoneHistoryBuffer;
    private UnityEngine.ComputeBuffer m_MetaBuffer;

    public CharacterGroupRenderer();

    private System.Void CreateRenderer();
    private UnityEngine.Color GetBlendColor(Game.Prefabs.RenderPrefab[] renderPrefabs, Game.Rendering.BlendWeight weight);
    private Game.Rendering.BlendColors GetBlendColors(Game.Prefabs.RenderPrefab[] renderPrefabs, Game.Rendering.BlendWeights weights);
    private System.Void OnDisable();
    private System.Void OnEnable();
    public System.Void Recreate();
    private System.Void ReleaseRenderer();
    public System.Void SetCharacterProperties(UnityEngine.MaterialPropertyBlock& block);
    private System.Void SetupBuffers(Game.Prefabs.CharacterGroup+Character character);
}
```


## Fields

- `public Game.Prefabs.CharacterGroup m_Prefab`  

```csharp
public Game.Prefabs.CharacterGroup m_Prefab;
```

- `public System.Boolean m_NoVT`  

```csharp
public System.Boolean m_NoVT;
```

- `public System.Int32 m_CharacterIndex`  

```csharp
public System.Int32 m_CharacterIndex;
```

- `public System.Int32 m_OverlayColorIndex`  

```csharp
public System.Int32 m_OverlayColorIndex;
```

- `private UnityEngine.GameObject m_Root`  

```csharp
private UnityEngine.GameObject m_Root;
```

- `private UnityEngine.ComputeBuffer m_BoneBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_BoneBuffer;
```

- `private UnityEngine.ComputeBuffer m_BoneHistoryBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_BoneHistoryBuffer;
```

- `private UnityEngine.ComputeBuffer m_MetaBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_MetaBuffer;
```


## Constructors

- `public CharacterGroupRenderer()`  

```csharp
public CharacterGroupRenderer();
```


## Methods

- `private CreateRenderer() : System.Void`  

```csharp
private void CreateRenderer()
	{
		if (m_Prefab != null)
		{
			m_CharacterIndex = Mathf.Clamp(m_CharacterIndex, 0, m_Prefab.m_Characters.Length - 1);
			CharacterGroup.Character character = m_Prefab.m_Characters[m_CharacterIndex];
			SetupBuffers(character);
			m_Root = new GameObject($"{m_Prefab.name} index {m_CharacterIndex}");
			m_Root.transform.parent = base.transform;
			m_Root.transform.localPosition = Vector3.zero;
			RenderPrefab[] meshPrefabs = character.m_MeshPrefabs;
			foreach (RenderPrefab renderPrefab in meshPrefabs)
			{
				GameObject obj = new GameObject(renderPrefab.name);
				obj.transform.parent = m_Root.transform;
				obj.transform.localPosition = Vector3.zero;
				obj.SetActive(value: false);
				RenderPrefabRenderer renderPrefabRenderer = obj.AddComponent<RenderPrefabRenderer>();
				renderPrefabRenderer.m_NoVT = m_NoVT;
				renderPrefabRenderer.m_Prefab = renderPrefab;
				obj.SetActive(value: true);
			}
		}
	}
```

- `private GetBlendColor(Game.Prefabs.RenderPrefab[] renderPrefabs, Game.Rendering.BlendWeight weight) : UnityEngine.Color`  

```csharp
private Color GetBlendColor(RenderPrefab[] renderPrefabs, BlendWeight weight)
	{
		Color color = Color.white;
		int num = 0;
		for (int i = 0; i < renderPrefabs.Length; i++)
		{
			if (!renderPrefabs[i].TryGet<CharacterProperties>(out var component))
			{
				continue;
			}
			CharacterOverlay[] overlays = component.m_Overlays;
			for (int j = 0; j < overlays.Length; j++)
			{
				if (overlays[j].TryGet<CharacterOverlay>(out var component2) && component2.m_Index == weight.m_Index && component2.TryGet<ColorProperties>(out var component3))
				{
					if (num == 0)
					{
						color = new Color(0f, 0f, 0f, 0f);
					}
					color += component3.GetColor(m_OverlayColorIndex, 0).linear * weight.m_Weight;
					num++;
				}
			}
		}
		if (num > 0)
		{
			return color / num;
		}
		return Color.white;
	}
```

- `private GetBlendColors(Game.Prefabs.RenderPrefab[] renderPrefabs, Game.Rendering.BlendWeights weights) : Game.Rendering.BlendColors`  

```csharp
private BlendColors GetBlendColors(RenderPrefab[] renderPrefabs, BlendWeights weights)
	{
		return new BlendColors
		{
			m_Color0 = GetBlendColor(renderPrefabs, weights.m_Weight0),
			m_Color1 = GetBlendColor(renderPrefabs, weights.m_Weight1),
			m_Color2 = GetBlendColor(renderPrefabs, weights.m_Weight2),
			m_Color3 = GetBlendColor(renderPrefabs, weights.m_Weight3),
			m_Color4 = GetBlendColor(renderPrefabs, weights.m_Weight4),
			m_Color5 = GetBlendColor(renderPrefabs, weights.m_Weight5),
			m_Color6 = GetBlendColor(renderPrefabs, weights.m_Weight6),
			m_Color7 = GetBlendColor(renderPrefabs, weights.m_Weight7)
		};
	}
```

- `private OnDisable() : System.Void`  

```csharp
private void OnDisable()
	{
		ReleaseRenderer();
	}
```

- `private OnEnable() : System.Void`  

```csharp
private void OnEnable()
	{
		CreateRenderer();
	}
```

- `public Recreate() : System.Void`  

```csharp
public void Recreate()
	{
		ReleaseRenderer();
		CreateRenderer();
	}
```

- `private ReleaseRenderer() : System.Void`  

```csharp
private void ReleaseRenderer()
	{
		if (m_Root != null)
		{
			Object.Destroy(m_Root);
		}
		if (m_BoneBuffer != null)
		{
			m_BoneBuffer.Release();
			m_BoneBuffer = null;
		}
		if (m_BoneHistoryBuffer != null)
		{
			m_BoneHistoryBuffer.Release();
			m_BoneHistoryBuffer = null;
		}
		if (m_MetaBuffer != null)
		{
			m_MetaBuffer.Release();
			m_MetaBuffer = null;
		}
	}
```

- `public SetCharacterProperties(UnityEngine.MaterialPropertyBlock& block) : System.Void`  

```csharp
public void SetCharacterProperties(ref MaterialPropertyBlock block)
	{
		if (m_BoneBuffer != null && m_MetaBuffer != null)
		{
			block.SetBuffer("boneBuffer", m_BoneBuffer);
			block.SetBuffer("boneHistoryBuffer", m_BoneHistoryBuffer);
			block.SetBuffer("metaBuffer", m_MetaBuffer);
		}
	}
```

- `private SetupBuffers(Game.Prefabs.CharacterGroup+Character character) : System.Void`  

```csharp
private unsafe void SetupBuffers(CharacterGroup.Character character)
	{
		m_BoneBuffer = new ComputeBuffer(character.m_Style.m_BoneCount, sizeof(BoneElement), ComputeBufferType.Structured);
		m_BoneHistoryBuffer = new ComputeBuffer(character.m_Style.m_BoneCount, sizeof(BoneElement), ComputeBufferType.Structured);
		m_MetaBuffer = new ComputeBuffer(1, sizeof(MetaBufferData), ComputeBufferType.Structured);
		BoneElement[] array = new BoneElement[character.m_Style.m_BoneCount];
		for (int i = 0; i < array.Length; i++)
		{
			array[i] = new BoneElement
			{
				m_Matrix = float4x4.identity
			};
		}
		BlendWeights blendWeights = RenderingUtils.GetBlendWeights(character.m_Meta.overlayWeights);
		BlendColors blendColors = GetBlendColors(character.m_MeshPrefabs, blendWeights);
		MetaBufferData[] data = new MetaBufferData[1]
		{
			new MetaBufferData
			{
				m_BoneCount = character.m_Style.m_BoneCount,
				m_ShapeCount = character.m_Style.m_ShapeCount,
				m_ShapeWeights = RenderingUtils.GetBlendWeights(character.m_Meta.shapeWeights),
				m_TextureWeights = RenderingUtils.GetBlendWeights(character.m_Meta.textureWeights),
				m_OverlayWeights = blendWeights,
				m_MaskWeights = RenderingUtils.GetBlendWeights(character.m_Meta.maskWeights),
				m_OverlayColors1 = blendColors
			}
		};
		m_BoneBuffer.SetData(array);
		m_BoneHistoryBuffer.SetData(array);
		m_MetaBuffer.SetData(data);
	}
```


