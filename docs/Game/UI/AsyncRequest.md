# Game.UI.ScreenCaptureHelper+AsyncRequest

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class AsyncRequest
{
    private readonly System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_TaskCompletionSource;
    private Unity.Collections.NativeArray<System.Byte> m_Data;
    private readonly System.Int32 <width>k__BackingField;
    private readonly System.Int32 <height>k__BackingField;
    private readonly UnityEngine.Experimental.Rendering.GraphicsFormat <format>k__BackingField;

    public System.Int32 width { get; }
    public System.Int32 height { get; }
    public UnityEngine.Experimental.Rendering.GraphicsFormat format { get; }
    public Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& result { get; }

    public AsyncRequest(UnityEngine.Texture previewTexture);

    public System.Threading.Tasks.Task Complete();
    public System.Threading.Tasks.Task Dispose();
    private System.Void OnCompleted(UnityEngine.Rendering.AsyncGPUReadbackRequest request);
}
```


## Fields

- `private readonly System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_TaskCompletionSource`  

```csharp
private readonly System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_TaskCompletionSource;
```

- `private Unity.Collections.NativeArray<System.Byte> m_Data`  

```csharp
private Unity.Collections.NativeArray<System.Byte> m_Data;
```

- `private readonly System.Int32 <width>k__BackingField`  

```csharp
private readonly System.Int32 <width>k__BackingField;
```

- `private readonly System.Int32 <height>k__BackingField`  

```csharp
private readonly System.Int32 <height>k__BackingField;
```

- `private readonly UnityEngine.Experimental.Rendering.GraphicsFormat <format>k__BackingField`  

```csharp
private readonly UnityEngine.Experimental.Rendering.GraphicsFormat <format>k__BackingField;
```


## Properties

- `public System.Int32 width { get }`  

```csharp
public System.Int32 width { get; }
```

- `public System.Int32 height { get }`  

```csharp
public System.Int32 height { get; }
```

- `public UnityEngine.Experimental.Rendering.GraphicsFormat format { get }`  

```csharp
public UnityEngine.Experimental.Rendering.GraphicsFormat format { get; }
```

- `public Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& result { get }`  

```csharp
public Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& result { get; }
```


## Constructors

- `public AsyncRequest(UnityEngine.Texture previewTexture)`  

```csharp
public AsyncRequest(UnityEngine.Texture previewTexture);
```


## Methods

- `public Complete() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Complete();
```

- `public Dispose() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Dispose();
```

- `private OnCompleted(UnityEngine.Rendering.AsyncGPUReadbackRequest request) : System.Void`  

```csharp
private System.Void OnCompleted(UnityEngine.Rendering.AsyncGPUReadbackRequest request);
```


## Nested types

- `Game.UI.ScreenCaptureHelper+AsyncRequest+<Dispose>d__13`  

