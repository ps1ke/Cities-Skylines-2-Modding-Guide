# Colossal.Json.PositionTrackingStringReader

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class public  

**Base:** `System.IO.StringReader`  
**Implements:** `System.IDisposable`  

## Fields

- `private System.String input`  
- `private System.Int32 start`  
- `private System.Int32 position`  

## Constructors

- `public PositionTrackingStringReader(System.String input)`  

## Methods

- `public GetBlock() : System.String`  
- `public GetBounds(System.Int32 count) : System.String`  
- `public GetCharacter() : System.Char`  
- `public virtual Read() : System.Int32`  
- `public virtual Read(System.Char[] buffer, System.Int32 index, System.Int32 count) : System.Int32`  
- `public virtual ReadLine() : System.String`  
- `public virtual ReadToEnd() : System.String`  
- `public TagStart() : System.Void`  

