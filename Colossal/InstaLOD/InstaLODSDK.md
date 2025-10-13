# Colossal.InstaLOD.InstaLODSDK

**Assembly:** `InstaLOD.Runtime`  
**Namespace:** `Colossal.InstaLOD`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct InstaLODSDK
{
    internal System.IntPtr m_Ptr;
    private static Colossal.InstaLOD.InstaLODSDK s_Instance;
    private static const System.String kAuthKey;

    public static Colossal.InstaLOD.InstaLODSDK instance { get; }
    public System.Boolean isValid { get; }
    public System.Int32 version { get; }
    public System.Boolean isGPUComputeAvailable { get; }
    public System.String authorizationInfo { get; }

    public System.Boolean AuthorizeMachine(System.String username, System.String password);
    public System.Boolean DeauthorizeMachine(System.String username, System.String password);
    public System.Void Dispose();
    public System.Boolean Optimize(Colossal.InstaLOD.InstaLODMesh input, Colossal.InstaLOD.InstaLODMesh output, Colossal.InstaLOD.OptimizeSettings settings, System.Single& deviation);
}
```


## Fields

- `internal System.IntPtr m_Ptr`  

```csharp
internal System.IntPtr m_Ptr;
```

- `private static Colossal.InstaLOD.InstaLODSDK s_Instance`  

```csharp
private static Colossal.InstaLOD.InstaLODSDK s_Instance;
```

- `private static const System.String kAuthKey`  

```csharp
private static const System.String kAuthKey;
```


## Properties

- `public static Colossal.InstaLOD.InstaLODSDK instance { get }`  

```csharp
public static Colossal.InstaLOD.InstaLODSDK instance { get; }
```

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```

- `public System.Int32 version { get }`  

```csharp
public System.Int32 version { get; }
```

- `public System.Boolean isGPUComputeAvailable { get }`  

```csharp
public System.Boolean isGPUComputeAvailable { get; }
```

- `public System.String authorizationInfo { get }`  

```csharp
public System.String authorizationInfo { get; }
```


## Methods

- `public AuthorizeMachine(System.String username, System.String password) : System.Boolean`  

```csharp
public System.Boolean AuthorizeMachine(System.String username, System.String password);
```

- `public DeauthorizeMachine(System.String username, System.String password) : System.Boolean`  

```csharp
public System.Boolean DeauthorizeMachine(System.String username, System.String password);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Optimize(Colossal.InstaLOD.InstaLODMesh input, Colossal.InstaLOD.InstaLODMesh output, Colossal.InstaLOD.OptimizeSettings settings, System.Single& deviation) : System.Boolean`  

```csharp
public System.Boolean Optimize(Colossal.InstaLOD.InstaLODMesh input, Colossal.InstaLOD.InstaLODMesh output, Colossal.InstaLOD.OptimizeSettings settings, System.Single& deviation);
```


