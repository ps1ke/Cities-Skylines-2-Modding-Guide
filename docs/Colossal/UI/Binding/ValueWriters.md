# Colossal.UI.Binding.ValueWriters

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Fields

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Object> s_Writers`  

## Methods

- `public static Create<T>() : Colossal.UI.Binding.IWriter<T>`  
- `public static Create(System.Type type) : System.Object`  
- `private static GetDictionaryInterface(System.Type type) : System.Type`  
- `private static GetListInterface(System.Type type) : System.Type`  
- `public static Nullable<T>(Colossal.UI.Binding.IWriter<T> writer) : Colossal.UI.Binding.NullableWriter<T>`  
- `public static Register<T>(Colossal.UI.Binding.WriterDelegate<T> func) : System.Void`  
- `public static Register<T>(Colossal.UI.Binding.IWriter<T> writer) : System.Void`  

## Nested types

- `Colossal.UI.Binding.ValueWriters+<>c`  

