# Colossal.UI.StreamReader

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `cohtml.Net.UnitySyncStreamReader`  
**Implements:** `System.IDisposable`  

## Fields

- `private System.IO.Stream m_Stream`  
- `private static System.Collections.Generic.List<Colossal.UI.StreamReader> s_StreamReaders`  

## Constructors

- `public StreamReader(System.IO.Stream stream)`  
- `public StreamReader(System.String path)`  
- `public StreamReader(System.Byte[] data)`  

## Methods

- `public virtual Close() : System.Void`  
- `public static DisposeReaders() : System.Void`  
- `public virtual GetSize() : System.UInt32`  
- `public virtual Read(System.UInt32 offset, System.IntPtr buffer, System.UInt32 count) : System.UInt32`  

