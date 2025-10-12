# Game.UI.ScreenCaptureHelper+AsyncRequest

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private readonly System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_TaskCompletionSource`  
- `private Unity.Collections.NativeArray<System.Byte> m_Data`  
- `private readonly System.Int32 <width>k__BackingField`  
- `private readonly System.Int32 <height>k__BackingField`  
- `private readonly UnityEngine.Experimental.Rendering.GraphicsFormat <format>k__BackingField`  

## Properties

- `public System.Int32 width { get }`  
- `public System.Int32 height { get }`  
- `public UnityEngine.Experimental.Rendering.GraphicsFormat format { get }`  
- `public Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& result { get }`  

## Constructors

- `public AsyncRequest(UnityEngine.Texture previewTexture)`  

## Methods

- `public Complete() : System.Threading.Tasks.Task`  
- `public Dispose() : System.Threading.Tasks.Task`  
- `private OnCompleted(UnityEngine.Rendering.AsyncGPUReadbackRequest request) : System.Void`  

## Nested types

- `Game.UI.ScreenCaptureHelper+AsyncRequest+<Dispose>d__13`  

