# Colossal.Animations.IOExtensions

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Animations`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class IOExtensions
{
    public static Colossal.Animations.Animation ReadAnimation(System.IO.BinaryReader sr);
    public static Colossal.Animations.AnimationClip ReadAnimationClip(System.IO.BinaryReader sr);
    public static Colossal.Animations.Animation+Element[] ReadAnimationElements(System.IO.BinaryReader sr, System.Int32& diskDataSize);
    public static Colossal.Animations.BoneHierarchy ReadBoneHierarchy(System.IO.BinaryReader sr);
    public static Unity.Mathematics.float3 ReadFloat3(System.IO.BinaryReader sr);
    public static System.Int32[] ReadInt32Array(System.IO.BinaryReader sr);
    public static System.Void Write(System.IO.BinaryWriter sw, Colossal.Animations.AnimationClip clip);
    public static System.Void Write(System.IO.BinaryWriter sw, Colossal.Animations.BoneHierarchy v);
    public static System.Void Write(System.IO.BinaryWriter sw, System.Int32[] array);
    public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.float3 v);
    public static System.Void Write(System.IO.BinaryWriter sw, Colossal.Animations.Animation+Element[] v);
    public static System.Void Write(System.IO.BinaryWriter sw, Colossal.Animations.Animation v);
}
```


## Methods

- `public static ReadAnimation(System.IO.BinaryReader sr) : Colossal.Animations.Animation`  

```csharp
public static Colossal.Animations.Animation ReadAnimation(System.IO.BinaryReader sr);
```

- `public static ReadAnimationClip(System.IO.BinaryReader sr) : Colossal.Animations.AnimationClip`  

```csharp
public static Colossal.Animations.AnimationClip ReadAnimationClip(System.IO.BinaryReader sr);
```

- `public static ReadAnimationElements(System.IO.BinaryReader sr, System.Int32& diskDataSize) : Colossal.Animations.Animation+Element[]`  

```csharp
public static Colossal.Animations.Animation+Element[] ReadAnimationElements(System.IO.BinaryReader sr, System.Int32& diskDataSize);
```

- `public static ReadBoneHierarchy(System.IO.BinaryReader sr) : Colossal.Animations.BoneHierarchy`  

```csharp
public static Colossal.Animations.BoneHierarchy ReadBoneHierarchy(System.IO.BinaryReader sr);
```

- `public static ReadFloat3(System.IO.BinaryReader sr) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 ReadFloat3(System.IO.BinaryReader sr);
```

- `public static ReadInt32Array(System.IO.BinaryReader sr) : System.Int32[]`  

```csharp
public static System.Int32[] ReadInt32Array(System.IO.BinaryReader sr);
```

- `public static Write(System.IO.BinaryWriter sw, Colossal.Animations.AnimationClip clip) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Colossal.Animations.AnimationClip clip);
```

- `public static Write(System.IO.BinaryWriter sw, Colossal.Animations.BoneHierarchy v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Colossal.Animations.BoneHierarchy v);
```

- `public static Write(System.IO.BinaryWriter sw, System.Int32[] array) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, System.Int32[] array);
```

- `public static Write(System.IO.BinaryWriter sw, Unity.Mathematics.float3 v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.float3 v);
```

- `public static Write(System.IO.BinaryWriter sw, Colossal.Animations.Animation+Element[] v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Colossal.Animations.Animation+Element[] v);
```

- `public static Write(System.IO.BinaryWriter sw, Colossal.Animations.Animation v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Colossal.Animations.Animation v);
```


