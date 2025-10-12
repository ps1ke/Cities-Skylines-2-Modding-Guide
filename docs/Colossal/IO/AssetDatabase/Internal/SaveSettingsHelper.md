# Colossal.IO.AssetDatabase.Internal.SaveSettingsHelper

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.Internal`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IAsyncDisposable`, `System.IDisposable`  

## Fields

- `private readonly System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.SettingAsset+Fragment, System.IO.TextWriter> m_WritersMap`  

## Constructors

- `public SaveSettingsHelper()`  

## Methods

- `public Dispose() : System.Void`  
- `public DisposeAsync() : System.Threading.Tasks.ValueTask`  
- `private GetWriteStream(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment) : System.IO.TextWriter`  
- `public Write(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment, System.String line) : System.Void`  
- `public WriteAsync(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment, System.String line) : System.Threading.Tasks.Task`  

## Nested types

- `Colossal.IO.AssetDatabase.Internal.SaveSettingsHelper+<DisposeAsync>d__5`  
- `Colossal.IO.AssetDatabase.Internal.SaveSettingsHelper+<WriteAsync>d__2`  

