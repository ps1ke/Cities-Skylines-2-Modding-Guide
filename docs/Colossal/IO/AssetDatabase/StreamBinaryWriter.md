# Colossal.IO.AssetDatabase.StreamBinaryWriter

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Unity.Entities.Serialization.BinaryWriter`, `System.IDisposable`  

## Fields

- `private System.IO.Stream stream`  
- `private System.Byte[] buffer`  

## Properties

- `public System.Int64 Position { get; set }`  
- `public System.Int64 Length { get }`  

## Constructors

- `public StreamBinaryWriter(System.String fileName, System.Int32 bufferSize = 65536)`  
- `public StreamBinaryWriter(System.IO.Stream stream, System.Int32 bufferSize = 65536)`  

## Methods

- `public Dispose() : System.Void`  
- `public WriteBytes(System.Void* data, System.Int32 bytes) : System.Void`  

