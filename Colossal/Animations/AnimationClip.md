# Colossal.Animations.AnimationClip

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Animations`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class AnimationClip
{
    public Colossal.Animations.BoneHierarchy m_BoneHierarchy;
    public Colossal.Animations.Animation m_Animation;

    public System.String name { get; }
    public System.Int32 boneCount { get; }

    public AnimationClip();

    public System.Int32[] GetInverseBoneIndices();
}
```


## Fields

- `public Colossal.Animations.BoneHierarchy m_BoneHierarchy`  

```csharp
public Colossal.Animations.BoneHierarchy m_BoneHierarchy;
```

- `public Colossal.Animations.Animation m_Animation`  

```csharp
public Colossal.Animations.Animation m_Animation;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Int32 boneCount { get }`  

```csharp
public System.Int32 boneCount { get; }
```


## Constructors

- `public AnimationClip()`  

```csharp
public AnimationClip();
```


## Methods

- `public GetInverseBoneIndices() : System.Int32[]`  

```csharp
public System.Int32[] GetInverseBoneIndices();
```


