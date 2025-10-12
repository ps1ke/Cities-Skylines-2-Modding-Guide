# Colossal.Mono.CompilerServices.SymbolWriter.LineNumberTable

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `protected Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry[] _line_numbers`  
- `public readonly System.Int32 LineBase`  
- `public readonly System.Int32 LineRange`  
- `public readonly System.Byte OpcodeBase`  
- `public readonly System.Int32 MaxAddressIncrement`  
- `public static const System.Int32 Default_LineBase`  
- `public static const System.Int32 Default_LineRange`  
- `public static const System.Byte Default_OpcodeBase`  
- `public static const System.Byte DW_LNS_copy`  
- `public static const System.Byte DW_LNS_advance_pc`  
- `public static const System.Byte DW_LNS_advance_line`  
- `public static const System.Byte DW_LNS_set_file`  
- `public static const System.Byte DW_LNS_const_add_pc`  
- `public static const System.Byte DW_LNE_end_sequence`  
- `public static const System.Byte DW_LNE_MONO_negate_is_hidden`  
- `internal static const System.Byte DW_LNE_MONO__extensions_start`  
- `internal static const System.Byte DW_LNE_MONO__extensions_end`  

## Properties

- `public Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry[] LineNumbers { get }`  

## Constructors

- `protected LineNumberTable(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file)`  
- `internal LineNumberTable(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry[] lines)`  

## Methods

- `private DoRead(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader br, System.Boolean includesColumns, System.Boolean includesEnds) : System.Void`  
- `public GetMethodBounds(Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry& start, Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry& end) : System.Boolean`  
- `internal static Read(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader br, System.Boolean readColumnsInfo, System.Boolean readEndInfo) : Colossal.Mono.CompilerServices.SymbolWriter.LineNumberTable`  
- `internal Write(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw, System.Boolean hasColumnsInfo, System.Boolean hasEndInfo) : System.Void`  

