# Game.Prefabs.CharacterStyle

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public class CharacterStyle : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_ShapeCount;
    public System.Int32 m_BoneCount;
    public Game.Prefabs.GenderMask m_Gender;
    public Game.Prefabs.CharacterStyle+AnimationInfo[] m_Animations;

    public System.Boolean ignoreUnlockDependencies { get; }

    public CharacterStyle();

    public System.Void CalculateRootMotion(Colossal.Animations.BoneHierarchy hierarchy, Colossal.Animations.Animation animation, Colossal.Animations.Animation restPose, System.Int32 infoIndex);
    public Colossal.IO.AssetDatabase.AnimationAsset GetAnimation(System.Int32 index);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public System.Int32 m_ShapeCount`  

```csharp
public System.Int32 m_ShapeCount;
```

- `public System.Int32 m_BoneCount`  

```csharp
public System.Int32 m_BoneCount;
```

- `public Game.Prefabs.GenderMask m_Gender`  

```csharp
public Game.Prefabs.GenderMask m_Gender;
```

- `public Game.Prefabs.CharacterStyle+AnimationInfo[] m_Animations`  

```csharp
public Game.Prefabs.CharacterStyle+AnimationInfo[] m_Animations;
```


## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```


## Constructors

- `public CharacterStyle()`  

```csharp
public CharacterStyle();
```


## Methods

- `public CalculateRootMotion(Colossal.Animations.BoneHierarchy hierarchy, Colossal.Animations.Animation animation, Colossal.Animations.Animation restPose, System.Int32 infoIndex) : System.Void`  

```csharp
public void CalculateRootMotion(BoneHierarchy hierarchy, Animation animation, Animation restPose, int infoIndex)
	{
		int num = ((animation.shapeIndices.Length <= 1) ? 1 : m_ShapeCount);
		int num2 = 0;
		if (animation.layer == Colossal.Animations.AnimationLayer.BodyLayer)
		{
			for (int i = 0; i < animation.boneIndices.Length; i++)
			{
				if (animation.boneIndices[i] == 1)
				{
					num2 = 1;
					break;
				}
			}
		}
		int[] array = new int[hierarchy.hierarchyParentIndices.Length];
		int[] array2 = new int[num];
		AnimationMotion[] array3 = new AnimationMotion[num];
		for (int j = 0; j < array.Length; j++)
		{
			array[j] = -1;
		}
		for (int k = 0; k < animation.boneIndices.Length; k++)
		{
			if (animation.boneIndices[k] < array.Length)
			{
				array[animation.boneIndices[k]] = k;
			}
		}
		if (num > 1)
		{
			for (int l = 0; l < animation.shapeIndices.Length; l++)
			{
				array2[animation.shapeIndices[l]] = l;
			}
		}
		int num3 = animation.shapeIndices.Length;
		int num4 = animation.boneIndices.Length;
		for (int m = 0; m < num; m++)
		{
			AnimationMotion animationMotion = (array3[m] = new AnimationMotion());
			int num5 = array[num2];
			int num6 = array2[m];
			Animation.ElementRaw elementRaw;
			Animation.ElementRaw elementRaw2;
			if (num5 >= 0)
			{
				int num7 = num5 * num3;
				int num8 = num7 + (animation.frameCount - 1) * num4 * num3;
				elementRaw = animation.DecodeElement(num7 + num6);
				elementRaw2 = animation.DecodeElement(num8 + num6);
			}
			else
			{
				int num9 = num2 * restPose.shapeIndices.Length;
				elementRaw = restPose.DecodeElement(num9 + m);
				elementRaw2 = elementRaw;
			}
			for (int num10 = hierarchy.hierarchyParentIndices[num2]; num10 != -1; num10 = hierarchy.hierarchyParentIndices[num10])
			{
				num5 = array[num10];
				Animation.ElementRaw elementRaw3;
				Animation.ElementRaw elementRaw4;
				if (num5 >= 0)
				{
					int num11 = num5 * num3;
					int num12 = num11 + (animation.frameCount - 1) * num4 * num3;
					elementRaw3 = animation.DecodeElement(num11 + num6);
					elementRaw4 = animation.DecodeElement(num12 + num6);
				}
				else
				{
					int num13 = num10 * restPose.shapeIndices.Length;
					elementRaw3 = restPose.DecodeElement(num13 + m);
					elementRaw4 = elementRaw3;
				}
				elementRaw.position = elementRaw3.position + math.mul(elementRaw3.rotation, elementRaw.position);
				elementRaw.rotation = math.mul((quaternion)elementRaw3.rotation, (quaternion)elementRaw.rotation).value;
				elementRaw2.position = elementRaw4.position + math.mul(elementRaw4.rotation, elementRaw2.position);
				elementRaw2.rotation = math.mul((quaternion)elementRaw4.rotation, (quaternion)elementRaw2.rotation).value;
			}
			animationMotion.startOffset = elementRaw.position;
			animationMotion.endOffset = elementRaw2.position;
			animationMotion.startRotation = math.normalize((quaternion)elementRaw.rotation);
			animationMotion.endRotation = math.normalize((quaternion)elementRaw2.rotation);
		}
		m_Animations[infoIndex].rootMotionBone = num2;
		m_Animations[infoIndex].rootMotion = array3;
	}
```

- `public GetAnimation(System.Int32 index) : Colossal.IO.AssetDatabase.AnimationAsset`  

```csharp
public AnimationAsset GetAnimation(int index)
	{
		return AssetDatabase.global.GetAsset<AnimationAsset>(m_Animations[index].animationAsset);
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		for (int i = 0; i < m_Animations.Length; i++)
		{
			AnimationInfo animationInfo = m_Animations[i];
			if (animationInfo.target != null)
			{
				prefabs.Add(animationInfo.target);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<CharacterStyleData>());
		components.Add(ComponentType.ReadWrite<AnimationClip>());
		components.Add(ComponentType.ReadWrite<Game.Prefabs.AnimationMotion>());
		components.Add(ComponentType.ReadWrite<RestPoseElement>());
	}
```


## Nested types

- `Game.Prefabs.CharacterStyle+AnimationMotion`  
- `Game.Prefabs.CharacterStyle+AnimationInfo`  

