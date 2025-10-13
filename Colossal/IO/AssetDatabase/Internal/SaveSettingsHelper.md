# Colossal.IO.AssetDatabase.Internal.SaveSettingsHelper

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.Internal`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IAsyncDisposable`, `System.IDisposable`  

## Code

```csharp
public class SaveSettingsHelper : System.IAsyncDisposable, System.IDisposable
{
    private readonly System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.SettingAsset+Fragment, System.IO.TextWriter> m_WritersMap;

    public SaveSettingsHelper();

    public System.Void Dispose();
    public System.Threading.Tasks.ValueTask DisposeAsync();
    private System.IO.TextWriter GetWriteStream(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment);
    public System.Void Write(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment, System.String line);
    public System.Threading.Tasks.Task WriteAsync(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment, System.String line);
}
```


## Fields

- `private readonly System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.SettingAsset+Fragment, System.IO.TextWriter> m_WritersMap`  

```csharp
private readonly System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.SettingAsset+Fragment, System.IO.TextWriter> m_WritersMap;
```


## Constructors

- `public SaveSettingsHelper()`  

```csharp
public SaveSettingsHelper();
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public DisposeAsync() : System.Threading.Tasks.ValueTask`  

```csharp
public System.Threading.Tasks.ValueTask DisposeAsync();
```

- `private GetWriteStream(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment) : System.IO.TextWriter`  

```csharp
private System.IO.TextWriter GetWriteStream(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment);
```

- `public Write(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment, System.String line) : System.Void`  

```csharp
public System.Void Write(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment, System.String line);
```

- `public WriteAsync(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment, System.String line) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task WriteAsync(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment, System.String line);
```


## Nested types

- `Colossal.IO.AssetDatabase.Internal.SaveSettingsHelper+<DisposeAsync>d__5`  
- `Colossal.IO.AssetDatabase.Internal.SaveSettingsHelper+<WriteAsync>d__2`  

