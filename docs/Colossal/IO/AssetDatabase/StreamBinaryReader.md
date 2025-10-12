# Colossal.IO.AssetDatabase.StreamBinaryReader

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Unity.Entities.Serialization.BinaryReader`, `System.IDisposable`  

## Fields

- `private readonly System.String filePath`  
- `private System.Int64 <Position>k__BackingField`  

## Properties

- `public System.Int64 Position { get; set }`  

## Constructors

- `public StreamBinaryReader(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, System.Int64 bufferSize = 65536)`  

## Methods

- `public Dispose() : System.Void`  
- `public ReadBytes(System.Void* data, System.Int32 bytes) : System.Void`  
- `public ReadBytes(System.Void* data, System.Int32 bytes, Unity.Jobs.JobHandle& dependency) : System.Void`  

