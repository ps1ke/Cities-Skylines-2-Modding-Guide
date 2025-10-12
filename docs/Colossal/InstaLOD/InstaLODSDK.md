# Colossal.InstaLOD.InstaLODSDK

**Assembly:** `InstaLOD.Runtime`  
**Namespace:** `Colossal.InstaLOD`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `internal System.IntPtr m_Ptr`  
- `private static Colossal.InstaLOD.InstaLODSDK s_Instance`  
- `private static const System.String kAuthKey`  

## Properties

- `public static Colossal.InstaLOD.InstaLODSDK instance { get }`  
- `public System.Boolean isValid { get }`  
- `public System.Int32 version { get }`  
- `public System.Boolean isGPUComputeAvailable { get }`  
- `public System.String authorizationInfo { get }`  

## Methods

- `public AuthorizeMachine(System.String username, System.String password) : System.Boolean`  
- `public DeauthorizeMachine(System.String username, System.String password) : System.Boolean`  
- `public Dispose() : System.Void`  
- `public Optimize(Colossal.InstaLOD.InstaLODMesh input, Colossal.InstaLOD.InstaLODMesh output, Colossal.InstaLOD.OptimizeSettings settings, System.Single& deviation) : System.Boolean`  

