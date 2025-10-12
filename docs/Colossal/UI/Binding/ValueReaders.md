# Colossal.UI.Binding.ValueReaders

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Fields

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Object> s_Readers`  

## Methods

- `public static Create<T>() : Colossal.UI.Binding.IReader<T>`  
- `public static Create(System.Type type) : System.Object`  
- `private static IsDictionary(System.Type type) : System.Boolean`  
- `private static IsList(System.Type type) : System.Boolean`  
- `public static Nullable<T>(Colossal.UI.Binding.IReader<T> reader) : Colossal.UI.Binding.NullableReader<T>`  
- `public static Register<T>(Colossal.UI.Binding.ReaderDelegate<T> func) : System.Void`  
- `public static Register<T>(Colossal.UI.Binding.IReader<T> reader) : System.Void`  

## Nested types

- `Colossal.UI.Binding.ValueReaders+<>c`  

