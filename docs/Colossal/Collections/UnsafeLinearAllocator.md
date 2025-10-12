# Colossal.Collections.UnsafeLinearAllocator

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Collections.AllocatorManager+IAllocator`, `System.IDisposable`  

**Attributes:** `BurstCompile`  

## Fields

- `private Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Collections.UnsafeLinearAllocator+Buffer> m_Buffers`  
- `private Unity.Collections.AllocatorManager+AllocatorHandle m_Handle`  
- `private System.UInt32 m_MaxUsed`  
- `private System.UInt32 m_MaxSize`  
- `private System.Boolean m_LastBufferUsed`  
- `private System.UInt32 <Used>k__BackingField`  
- `private System.UInt32 <Size>k__BackingField`  

## Properties

- `public System.UInt32 Used { get; private set }`  
- `public System.UInt32 Size { get; private set }`  
- `public Unity.Collections.AllocatorManager+TryFunction Function { get }`  
- `public Unity.Collections.AllocatorManager+AllocatorHandle Handle { get; set }`  
- `public Unity.Collections.Allocator ToAllocator { get }`  
- `public System.Boolean IsCustomAllocator { get }`  
- `public System.Boolean IsAutoDispose { get }`  

## Methods

- `public Dispose() : System.Void`  
- `public Initialize(System.UInt32 initialSize) : System.Void`  
- `public Rewind(System.Boolean updateSize = False) : System.Void`  
- `public Try(Unity.Collections.AllocatorManager+Block& block) : System.Int32`  
- `internal static Try(System.IntPtr state, Unity.Collections.AllocatorManager+Block& block) : System.Int32`  
- `public static Try$BurstManaged(System.IntPtr state, Unity.Collections.AllocatorManager+Block& block) : System.Int32`  

## Nested types

- `Colossal.Collections.UnsafeLinearAllocator+Buffer`  
- `Colossal.Collections.UnsafeLinearAllocator+Colossal.Collections.Try_000000FB$PostfixBurstDelegate`  
- `Colossal.Collections.UnsafeLinearAllocator+Colossal.Collections.Try_000000FB$BurstDirectCall`  

