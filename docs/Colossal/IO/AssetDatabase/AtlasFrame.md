# Colossal.IO.AssetDatabase.AtlasFrame

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`, `System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.AtlasFrame+Entry>`, `System.Collections.IEnumerable`  

## Fields

- `private UnityEngine.Texture2D m_Texture`  
- `private Colossal.Core.MaxRectsBinPack m_Atlas`  
- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AtlasFrame+Entry> m_Entries`  

## Properties

- `public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AtlasFrame+Entry> entries { get }`  
- `public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> freeRectangles { get }`  
- `public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> usedRectangles { get }`  
- `public UnityEngine.Texture2D texture { get }`  
- `public System.String name { get; set }`  

## Constructors

- `public AtlasFrame(System.Int32 width, System.Int32 height, System.Boolean rotations, System.Int32 page)`  
- `public AtlasFrame(UnityEngine.Texture2D texture, System.Boolean rotations, System.Int32 page, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AtlasFrame+Entry> entries, System.Collections.Generic.List<UnityEngine.Rect> usedRectangles, System.Collections.Generic.List<UnityEngine.Rect> freeRectangles)`  

## Methods

- `private CreateTexture(System.Int32 width, System.Int32 height) : UnityEngine.Texture2D`  
- `public Dispose() : System.Void`  
- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Colossal.IO.AssetDatabase.AtlasFrame+Entry>`  
- `public Grow(System.Boolean forceUniform = False) : System.Boolean`  
- `public Insert(System.String name, UnityEngine.Texture rt, UnityEngine.Rect region) : System.Void`  
- `private Reserve(System.Int32 width, System.Int32 height, UnityEngine.Rect& region) : System.Boolean`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  
- `public TryAdd(System.String name, UnityEngine.Texture target) : System.Boolean`  

## Nested types

- `Colossal.IO.AssetDatabase.AtlasFrame+Entry`  

