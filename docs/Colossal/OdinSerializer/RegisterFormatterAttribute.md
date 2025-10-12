# Colossal.OdinSerializer.RegisterFormatterAttribute

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Fields

- `private System.Type <FormatterType>k__BackingField`  
- `private System.Type <WeakFallback>k__BackingField`  
- `private System.Int32 <Priority>k__BackingField`  

## Properties

- `public System.Type FormatterType { get; private set }`  
- `public System.Type WeakFallback { get; private set }`  
- `public System.Int32 Priority { get; private set }`  

## Constructors

- `public RegisterFormatterAttribute(System.Type formatterType, System.Int32 priority = 0)`  
- `public RegisterFormatterAttribute(System.Type formatterType, System.Type weakFallback, System.Int32 priority = 0)`  

