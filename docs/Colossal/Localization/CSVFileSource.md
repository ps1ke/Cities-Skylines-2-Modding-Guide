# Colossal.Localization.CSVFileSource

**Assembly:** `Colossal.Localization`  
**Namespace:** `Colossal.Localization`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.IDictionarySource`  

## Fields

- `private System.String <filePath>k__BackingField`  
- `private System.Char <columnDelimiter>k__BackingField`  

## Properties

- `public System.String filePath { get; set }`  
- `public System.Char columnDelimiter { get; set }`  

## Constructors

- `protected CSVFileSource()`  

## Methods

- `protected abstract GetIndices(System.Collections.Generic.List<System.String[]> rows, System.Int32& keyColumnIndex, System.Int32& valueColumnIndex, System.Int32& startRowIndex) : System.Void`  
- `public ReadEntries(System.Collections.Generic.IList<Colossal.IDictionaryEntryError> errors, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts) : System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>>`  
- `protected SplitLine(System.String line) : System.String[]`  
- `public virtual ToString() : System.String`  
- `public Unload() : System.Void`  

## Nested types

- `Colossal.Localization.CSVFileSource+<ReadEntries>d__8`  

