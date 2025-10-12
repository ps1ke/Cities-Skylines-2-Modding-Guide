# Colossal.Core.CrcParameters

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Core`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private readonly System.Int32 _width`  
- `private readonly System.UInt64 _polynomial`  
- `private readonly System.UInt64 _initialValue`  
- `private readonly System.UInt64 _xorOutValue`  
- `private readonly System.Boolean _reflectIn`  
- `private readonly System.Boolean _reflectOut`  

## Properties

- `public System.Int32 Width { get }`  
- `public System.UInt64 Polynomial { get }`  
- `public System.UInt64 InitialValue { get }`  
- `public System.UInt64 XorOutValue { get }`  
- `public System.Boolean ReflectIn { get }`  
- `public System.Boolean ReflectOut { get }`  

## Constructors

- `public CrcParameters(System.Int32 width, System.UInt64 polynomial, System.UInt64 initialValue, System.UInt64 xorOutValue, System.Boolean reflectIn, System.Boolean reflectOut)`  

## Methods

- `private ThrowIfParametersInvalid(System.Int32 width, System.UInt64 polynomial, System.UInt64 initialValue, System.UInt64 xorOutValue) : System.Void`  

