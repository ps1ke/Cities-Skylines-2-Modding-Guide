# Game.Rendering.Debug.RenderPrefabRenderer

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Debug`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Code

```csharp
public class RenderPrefabRenderer : UnityEngine.MonoBehaviour
{
    public System.Boolean m_NoVT;
    public Game.Prefabs.RenderPrefab m_Prefab;
    public System.Single m_WindowsLight;
    public System.Int32 m_EmissiveLight;
    public System.Int32 m_ColorIndex;
    public System.Int32 m_LODIndex;
    public System.Boolean m_Animate;
    private System.Collections.Generic.List<Game.Rendering.Debug.RenderPrefabRenderer+Instance> m_Hierarchies;
    private UnityEngine.MaterialPropertyBlock m_MaterialPropertyBlock;
    private System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Game.Rendering.Debug.RenderPrefabRenderer+AnimationState>> m_AnimationStates;
    private static const System.Boolean kRefreshPrefabDataEveryFrame;

    public System.Collections.Generic.IReadOnlyList<Game.Rendering.Debug.RenderPrefabRenderer+Instance> hierarchies { get; }

    public RenderPrefabRenderer();

    public UnityEngine.GameObject GetActiveRoot();
    private System.Void OnDisable();
    private System.Void OnDrawGizmosSelected();
    private System.Void OnEnable();
    private System.Void RegisterForAnimation(System.String boneName, UnityEngine.Transform target, Game.Prefabs.ProceduralAnimationProperties+BoneInfo boneInfo);
    private System.Void Update();
    private System.Void UpdateAnimations();
}
```


## Fields

- `public System.Boolean m_NoVT`  

```csharp
public System.Boolean m_NoVT;
```

- `public Game.Prefabs.RenderPrefab m_Prefab`  

```csharp
public Game.Prefabs.RenderPrefab m_Prefab;
```

- `public System.Single m_WindowsLight`  

```csharp
public System.Single m_WindowsLight;
```

- `public System.Int32 m_EmissiveLight`  

```csharp
public System.Int32 m_EmissiveLight;
```

- `public System.Int32 m_ColorIndex`  

```csharp
public System.Int32 m_ColorIndex;
```

- `public System.Int32 m_LODIndex`  

```csharp
public System.Int32 m_LODIndex;
```

- `public System.Boolean m_Animate`  

```csharp
public System.Boolean m_Animate;
```

- `private System.Collections.Generic.List<Game.Rendering.Debug.RenderPrefabRenderer+Instance> m_Hierarchies`  

```csharp
private System.Collections.Generic.List<Game.Rendering.Debug.RenderPrefabRenderer+Instance> m_Hierarchies;
```

- `private UnityEngine.MaterialPropertyBlock m_MaterialPropertyBlock`  

```csharp
private UnityEngine.MaterialPropertyBlock m_MaterialPropertyBlock;
```

- `private System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Game.Rendering.Debug.RenderPrefabRenderer+AnimationState>> m_AnimationStates`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Game.Rendering.Debug.RenderPrefabRenderer+AnimationState>> m_AnimationStates;
```

- `private static const System.Boolean kRefreshPrefabDataEveryFrame`  

```csharp
private static const System.Boolean kRefreshPrefabDataEveryFrame;
```


## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.Rendering.Debug.RenderPrefabRenderer+Instance> hierarchies { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Rendering.Debug.RenderPrefabRenderer+Instance> hierarchies { get; }
```


## Constructors

- `public RenderPrefabRenderer()`  

```csharp
public RenderPrefabRenderer();
```


## Methods

- `public GetActiveRoot() : UnityEngine.GameObject`  

```csharp
public GameObject GetActiveRoot()
	{
		if (m_Hierarchies != null && m_LODIndex < m_Hierarchies.Count)
		{
			return m_Hierarchies[m_LODIndex].root;
		}
		return null;
	}
```

- `private OnDisable() : System.Void`  

```csharp
private void OnDisable()
	{
		if (m_Hierarchies == null)
		{
			return;
		}
		foreach (Instance hierarchy in m_Hierarchies)
		{
			hierarchy.Dispose();
		}
	}
```

- `private OnDrawGizmosSelected() : System.Void`  

```csharp
private void OnDrawGizmosSelected()
	{
		Renderer[] componentsInChildren = GetComponentsInChildren<Renderer>();
		if (componentsInChildren != null && componentsInChildren.Length != 0)
		{
			for (int i = 0; i < componentsInChildren.Length; i++)
			{
				Bounds bounds = componentsInChildren[i].bounds;
				UnityEngine.Gizmos.matrix = Matrix4x4.identity;
				UnityEngine.Gizmos.color = Colossal.ColorUtils.NiceRandomColor(i);
				UnityEngine.Gizmos.DrawWireCube(bounds.center, bounds.extents * 2f);
			}
		}
	}
```

- `private OnEnable() : System.Void`  

```csharp
private void OnEnable()
	{
		if (!(m_Prefab != null))
		{
			return;
		}
		m_MaterialPropertyBlock = new MaterialPropertyBlock();
		m_Hierarchies = new List<Instance>();
		m_Hierarchies.Add(new Instance(this, m_Prefab, m_Prefab, !m_NoVT));
		if (m_Prefab.TryGet<LodProperties>(out var component))
		{
			RenderPrefab[] lodMeshes = component.m_LodMeshes;
			foreach (RenderPrefab prefab in lodMeshes)
			{
				Instance instance = new Instance(this, m_Prefab, prefab, !m_NoVT);
				instance.enabled = false;
				m_Hierarchies.Add(instance);
			}
		}
	}
```

- `private RegisterForAnimation(System.String boneName, UnityEngine.Transform target, Game.Prefabs.ProceduralAnimationProperties+BoneInfo boneInfo) : System.Void`  

```csharp
private void RegisterForAnimation(string boneName, Transform target, ProceduralAnimationProperties.BoneInfo boneInfo)
	{
		if (!m_AnimationStates.TryGetValue(boneName, out var value))
		{
			value = new List<AnimationState>();
			m_AnimationStates.Add(boneName, value);
		}
		if (value.FindIndex((AnimationState x) => x.target == target) == -1)
		{
			value.Add(new AnimationState(target, boneInfo));
		}
	}
```

- `private Update() : System.Void`  

```csharp
private void Update()
	{
		if (m_Animate)
		{
			UpdateAnimations();
		}
		for (int i = 0; i < m_Hierarchies.Count; i++)
		{
			m_MaterialPropertyBlock.Clear();
			Instance instance = m_Hierarchies[i];
			instance.Update();
			instance.SetWindowProperties(m_WindowsLight, ref m_MaterialPropertyBlock);
			instance.SetColorProperties(m_ColorIndex, ref m_MaterialPropertyBlock);
			instance.SetDecalProperties(ref m_MaterialPropertyBlock);
			instance.SetEmissiveProperties(m_EmissiveLight, ref m_MaterialPropertyBlock);
			instance.SetProceduralAnimationProperties(ref m_MaterialPropertyBlock);
			instance.SetCharacterProperties(ref m_MaterialPropertyBlock);
			instance.enabled = i == m_LODIndex;
		}
	}
```

- `private UpdateAnimations() : System.Void`  

```csharp
private void UpdateAnimations()
	{
		foreach (KeyValuePair<string, List<AnimationState>> animationState2 in m_AnimationStates)
		{
			AnimationState animationState = animationState2.Value[0];
			animationState.Animate();
			for (int i = 1; i < animationState2.Value.Count; i++)
			{
				animationState.Transfer(animationState2.Value[i]);
			}
		}
	}
```


## Nested types

- `Game.Rendering.Debug.RenderPrefabRenderer+Instance`  
- `Game.Rendering.Debug.RenderPrefabRenderer+ShaderIDs`  
- `Game.Rendering.Debug.RenderPrefabRenderer+AnimationState`  
- `Game.Rendering.Debug.RenderPrefabRenderer+<>c__DisplayClass19_0`  

