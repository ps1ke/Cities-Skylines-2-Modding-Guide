# Colossal.IO.AssetDatabase.UnityWebRequestAwaiter

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Runtime.CompilerServices.INotifyCompletion`  

## Fields

- `private UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp`  
- `private System.Action callback`  

## Properties

- `public System.Boolean IsCompleted { get }`  

## Constructors

- `public UnityWebRequestAwaiter(UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp)`  

## Methods

- `public GetResult() : System.Void`  
- `public OnCompleted(System.Action callback) : System.Void`  
- `private OnRequestCompleted(UnityEngine.AsyncOperation obj) : System.Void`  

