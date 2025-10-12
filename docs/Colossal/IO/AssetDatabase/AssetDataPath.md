# Colossal.IO.AssetDatabase.AssetDataPath

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private readonly System.String m_SubPath`  
- `private readonly System.String m_AssetName`  
- `private readonly System.String m_Extension`  
- `private readonly Colossal.IO.AssetDatabase.EscapeStrategy m_EscapeStrategy`  

## Properties

- `public System.String subPath { get }`  
- `public System.String assetName { get }`  
- `public System.String extension { get }`  

## Constructors

- `private AssetDataPath(System.String subPath, System.String assetName, System.Boolean hasExtension, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy)`  

## Methods

- `public static Create(System.String assetName, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy = Filename) : Colossal.IO.AssetDatabase.AssetDataPath`  
- `public static Create(System.String assetName, System.Boolean hasExtension, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy = Filename) : Colossal.IO.AssetDatabase.AssetDataPath`  
- `public static Create(System.String subPath, System.String assetName, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy = Filename) : Colossal.IO.AssetDatabase.AssetDataPath`  
- `public static Create(System.String subPath, System.String assetName, System.Boolean hasExtension, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy = Filename) : Colossal.IO.AssetDatabase.AssetDataPath`  
- `public ToFilename(Colossal.IO.AssetDatabase.IPathEscapePolicy escapePolicy) : System.String`  
- `public ToPath(Colossal.IO.AssetDatabase.IPathEscapePolicy escapePolicy) : System.String`  
- `public virtual ToString() : System.String`  

