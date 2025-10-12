# Game.UnityWebRequestExtensionMethods+UnityWebRequestAwaiter

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Runtime.CompilerServices.INotifyCompletion`  

## Fields

- `private UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp`  
- `private System.Action continuation`  

## Properties

- `public System.Boolean IsCompleted { get }`  

## Constructors

- `public UnityWebRequestAwaiter(UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp)`  

## Methods

- `public GetAwaiter() : Game.UnityWebRequestExtensionMethods+UnityWebRequestAwaiter`  
- `public GetResult() : UnityEngine.Networking.UnityWebRequest+Result`  
- `public OnCompleted(System.Action continuation) : System.Void`  
- `public OnRequestCompleted(UnityEngine.AsyncOperation obj) : System.Void`  

