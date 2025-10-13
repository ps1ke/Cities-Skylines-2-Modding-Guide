# PDX.SDK.Internal.Service.Mods.Helpers.PlaysetAndModExtensions

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Service.Mods.Helpers`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class PlaysetAndModExtensions
{
    public static System.String GetKey(PDX.SDK.Contracts.Service.Mods.Models.IMod mod);
    public static System.String GetKey(PDX.SDK.Contracts.Service.Mods.Models.ModDetails mod);
    public static System.String GetKey(PDX.SDK.Internal.Service.Mods.Models.PlaysetSubscribedModMetaData playsetSubscribedMod);
    public static System.String GetKey(PDX.SDK.Internal.Service.Mods.Models.PlaysetWipModMetaData playsetWipMod);
    public static System.String GetKey(PDX.SDK.Internal.Service.Mods.Models.PlaysetUnmanagedModMetaData playsetUnmanagedMod);
    internal static System.String GetKey(System.Int32 id, System.String version);
    internal static System.String GetKey(PDX.SDK.Contracts.Service.Mods.Models.PlaysetSubscribedMod playsetSubscribedMod);
    internal static System.String GetKey(PDX.SDK.Internal.Service.Mods.Models.CachedPlaysetMetaData cachedPlaysetMetaData);
    internal static System.String GetKey(PDX.SDK.Internal.Service.Mods.Models.PlaysetGeneralMetaData playsetGeneralMetaData);
    public static System.String GetModKey(System.Int32 id, System.String version);
    internal static System.Boolean IsSubscribedMod(PDX.SDK.Contracts.Service.Mods.Models.IMod mod);
    internal static System.Boolean IsSubscribedMod(PDX.SDK.Contracts.Service.Mods.Models.IPlaysetMod mod);
    internal static System.Void UpdateMetaFromAddedMod(PDX.SDK.Internal.Service.Mods.Models.PlaysetGeneralMetaData playsetGeneralMetaData, System.UInt64 modSize);
    internal static System.Void UpdateMetaFromRemovedMod(PDX.SDK.Internal.Service.Mods.Models.PlaysetGeneralMetaData playsetGeneralMetaData, System.UInt64 modSize);
}
```


## Methods

- `public static GetKey(PDX.SDK.Contracts.Service.Mods.Models.IMod mod) : System.String`  

```csharp
public static System.String GetKey(PDX.SDK.Contracts.Service.Mods.Models.IMod mod);
```

- `public static GetKey(PDX.SDK.Contracts.Service.Mods.Models.ModDetails mod) : System.String`  

```csharp
public static System.String GetKey(PDX.SDK.Contracts.Service.Mods.Models.ModDetails mod);
```

- `public static GetKey(PDX.SDK.Internal.Service.Mods.Models.PlaysetSubscribedModMetaData playsetSubscribedMod) : System.String`  

```csharp
public static System.String GetKey(PDX.SDK.Internal.Service.Mods.Models.PlaysetSubscribedModMetaData playsetSubscribedMod);
```

- `public static GetKey(PDX.SDK.Internal.Service.Mods.Models.PlaysetWipModMetaData playsetWipMod) : System.String`  

```csharp
public static System.String GetKey(PDX.SDK.Internal.Service.Mods.Models.PlaysetWipModMetaData playsetWipMod);
```

- `public static GetKey(PDX.SDK.Internal.Service.Mods.Models.PlaysetUnmanagedModMetaData playsetUnmanagedMod) : System.String`  

```csharp
public static System.String GetKey(PDX.SDK.Internal.Service.Mods.Models.PlaysetUnmanagedModMetaData playsetUnmanagedMod);
```

- `internal static GetKey(System.Int32 id, System.String version) : System.String`  

```csharp
internal static System.String GetKey(System.Int32 id, System.String version);
```

- `internal static GetKey(PDX.SDK.Contracts.Service.Mods.Models.PlaysetSubscribedMod playsetSubscribedMod) : System.String`  

```csharp
internal static System.String GetKey(PDX.SDK.Contracts.Service.Mods.Models.PlaysetSubscribedMod playsetSubscribedMod);
```

- `internal static GetKey(PDX.SDK.Internal.Service.Mods.Models.CachedPlaysetMetaData cachedPlaysetMetaData) : System.String`  

```csharp
internal static System.String GetKey(PDX.SDK.Internal.Service.Mods.Models.CachedPlaysetMetaData cachedPlaysetMetaData);
```

- `internal static GetKey(PDX.SDK.Internal.Service.Mods.Models.PlaysetGeneralMetaData playsetGeneralMetaData) : System.String`  

```csharp
internal static System.String GetKey(PDX.SDK.Internal.Service.Mods.Models.PlaysetGeneralMetaData playsetGeneralMetaData);
```

- `public static GetModKey(System.Int32 id, System.String version) : System.String`  

```csharp
public static System.String GetModKey(System.Int32 id, System.String version);
```

- `internal static IsSubscribedMod(PDX.SDK.Contracts.Service.Mods.Models.IMod mod) : System.Boolean`  

```csharp
internal static System.Boolean IsSubscribedMod(PDX.SDK.Contracts.Service.Mods.Models.IMod mod);
```

- `internal static IsSubscribedMod(PDX.SDK.Contracts.Service.Mods.Models.IPlaysetMod mod) : System.Boolean`  

```csharp
internal static System.Boolean IsSubscribedMod(PDX.SDK.Contracts.Service.Mods.Models.IPlaysetMod mod);
```

- `internal static UpdateMetaFromAddedMod(PDX.SDK.Internal.Service.Mods.Models.PlaysetGeneralMetaData playsetGeneralMetaData, System.UInt64 modSize) : System.Void`  

```csharp
internal static System.Void UpdateMetaFromAddedMod(PDX.SDK.Internal.Service.Mods.Models.PlaysetGeneralMetaData playsetGeneralMetaData, System.UInt64 modSize);
```

- `internal static UpdateMetaFromRemovedMod(PDX.SDK.Internal.Service.Mods.Models.PlaysetGeneralMetaData playsetGeneralMetaData, System.UInt64 modSize) : System.Void`  

```csharp
internal static System.Void UpdateMetaFromRemovedMod(PDX.SDK.Internal.Service.Mods.Models.PlaysetGeneralMetaData playsetGeneralMetaData, System.UInt64 modSize);
```


