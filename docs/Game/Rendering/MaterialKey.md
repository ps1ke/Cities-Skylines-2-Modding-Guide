# Game.Rendering.ManagedBatchSystem+MaterialKey

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IEquatable<Game.Rendering.ManagedBatchSystem+MaterialKey>`  

## Fields

- `private UnityEngine.Shader <shader>k__BackingField`  
- `private UnityEngine.Material <template>k__BackingField`  
- `private System.Int32 <decalLayerMask>k__BackingField`  
- `private System.Int32 <renderQueue>k__BackingField`  
- `private System.Collections.Generic.HashSet<System.String> <keywords>k__BackingField`  
- `private System.Collections.Generic.List<System.Int32> <vtStacks>k__BackingField`  
- `private System.Collections.Generic.Dictionary<System.Int32, System.Object> <textures>k__BackingField`  

## Properties

- `public UnityEngine.Shader shader { get; set }`  
- `public UnityEngine.Material template { get; set }`  
- `public System.Int32 decalLayerMask { get; set }`  
- `public System.Int32 renderQueue { get; set }`  
- `public System.Collections.Generic.HashSet<System.String> keywords { get; private set }`  
- `public System.Collections.Generic.List<System.Int32> vtStacks { get; private set }`  
- `public System.Collections.Generic.Dictionary<System.Int32, System.Object> textures { get; private set }`  

## Constructors

- `public MaterialKey()`  
- `public MaterialKey(Game.Rendering.ManagedBatchSystem+MaterialKey source)`  

## Methods

- `public Clear() : System.Void`  
- `public Equals(Game.Rendering.ManagedBatchSystem+MaterialKey other) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public Initialize(Colossal.IO.AssetDatabase.SurfaceAsset surface) : System.Void`  
- `public Initialize(UnityEngine.Material material) : System.Void`  

