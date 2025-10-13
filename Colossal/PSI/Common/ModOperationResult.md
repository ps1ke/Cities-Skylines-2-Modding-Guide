# Colossal.PSI.Common.IModsUploadSupport+ModOperationResult

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ModOperationResult
{
    public System.Boolean m_Success;
    public Colossal.PSI.Common.IModsUploadSupport+ModError m_Error;
    public Colossal.PSI.Common.IModsUploadSupport+ModInfo m_ModInfo;

    public System.Void Clear();
    public static Colossal.PSI.Common.IModsUploadSupport+ModOperationResult Failure(Colossal.PSI.Common.IModsUploadSupport+ModError error, Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
    public static Colossal.PSI.Common.IModsUploadSupport+ModOperationResult Failure(System.String category, System.String subCategory, System.String details, System.String raw, Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
    public static Colossal.PSI.Common.IModsUploadSupport+ModOperationResult Success(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
}
```


## Fields

- `public System.Boolean m_Success`  

```csharp
public System.Boolean m_Success;
```

- `public Colossal.PSI.Common.IModsUploadSupport+ModError m_Error`  

```csharp
public Colossal.PSI.Common.IModsUploadSupport+ModError m_Error;
```

- `public Colossal.PSI.Common.IModsUploadSupport+ModInfo m_ModInfo`  

```csharp
public Colossal.PSI.Common.IModsUploadSupport+ModInfo m_ModInfo;
```


## Methods

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `public static Failure(Colossal.PSI.Common.IModsUploadSupport+ModError error, Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : Colossal.PSI.Common.IModsUploadSupport+ModOperationResult`  

```csharp
public static Colossal.PSI.Common.IModsUploadSupport+ModOperationResult Failure(Colossal.PSI.Common.IModsUploadSupport+ModError error, Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
```

- `public static Failure(System.String category, System.String subCategory, System.String details, System.String raw, Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : Colossal.PSI.Common.IModsUploadSupport+ModOperationResult`  

```csharp
public static Colossal.PSI.Common.IModsUploadSupport+ModOperationResult Failure(System.String category, System.String subCategory, System.String details, System.String raw, Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
```

- `public static Success(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : Colossal.PSI.Common.IModsUploadSupport+ModOperationResult`  

```csharp
public static Colossal.PSI.Common.IModsUploadSupport+ModOperationResult Success(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
```


