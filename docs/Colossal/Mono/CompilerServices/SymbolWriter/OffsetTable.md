# Colossal.Mono.CompilerServices.SymbolWriter.OffsetTable

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `public System.Int32 TotalFileSize`  
- `public System.Int32 DataSectionOffset`  
- `public System.Int32 DataSectionSize`  
- `public System.Int32 CompileUnitCount`  
- `public System.Int32 CompileUnitTableOffset`  
- `public System.Int32 CompileUnitTableSize`  
- `public System.Int32 SourceCount`  
- `public System.Int32 SourceTableOffset`  
- `public System.Int32 SourceTableSize`  
- `public System.Int32 MethodCount`  
- `public System.Int32 MethodTableOffset`  
- `public System.Int32 MethodTableSize`  
- `public System.Int32 TypeCount`  
- `public System.Int32 AnonymousScopeCount`  
- `public System.Int32 AnonymousScopeTableOffset`  
- `public System.Int32 AnonymousScopeTableSize`  
- `public Colossal.Mono.CompilerServices.SymbolWriter.OffsetTable+Flags FileFlags`  
- `public System.Int32 LineNumberTable_LineBase`  
- `public System.Int32 LineNumberTable_LineRange`  
- `public System.Int32 LineNumberTable_OpcodeBase`  
- `public static const System.Int32 MajorVersion`  
- `public static const System.Int32 MinorVersion`  
- `public static const System.Int64 Magic`  

## Constructors

- `internal OffsetTable()`  
- `internal OffsetTable(System.IO.BinaryReader reader, System.Int32 major_version, System.Int32 minor_version)`  

## Methods

- `public virtual ToString() : System.String`  
- `internal Write(System.IO.BinaryWriter bw, System.Int32 major_version, System.Int32 minor_version) : System.Void`  

## Nested types

- `Colossal.Mono.CompilerServices.SymbolWriter.OffsetTable+Flags`  

