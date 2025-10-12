# Colossal.PSI.Common.IModsUploadSupport+ModOperationResult

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public System.Boolean m_Success`  
- `public Colossal.PSI.Common.IModsUploadSupport+ModError m_Error`  
- `public Colossal.PSI.Common.IModsUploadSupport+ModInfo m_ModInfo`  

## Methods

- `public Clear() : System.Void`  
- `public static Failure(Colossal.PSI.Common.IModsUploadSupport+ModError error, Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : Colossal.PSI.Common.IModsUploadSupport+ModOperationResult`  
- `public static Failure(System.String category, System.String subCategory, System.String details, System.String raw, Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : Colossal.PSI.Common.IModsUploadSupport+ModOperationResult`  
- `public static Success(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : Colossal.PSI.Common.IModsUploadSupport+ModOperationResult`  

