# Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Fields

- `public System.Int32 m_Hash`  
- `public UnityEngine.Material m_Material`  
- `public System.Boolean m_SupportsVT`  
- `public System.Int32 m_MipBiasOverride`  
- `public Colossal.IO.AssetDatabase.MaterialStackProperties[] m_Stacks`  

## Properties

- `public System.Boolean hasMipBiasOverride { get }`  

## Constructors

- `public MaterialDescription()`  

## Methods

- `public GetLayerIndexInStack(System.Int32 stackConfigIndex, System.String textureName) : System.Int32`  
- `public GetStackConfigIndex(System.String propName) : System.Int32`  
- `public IsValid() : System.Boolean`  

