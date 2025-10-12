# Game.Settings.SettingsUIInputActionAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class abstract public  

**Base:** `System.Attribute`  

## Fields

- `public readonly System.String name`  
- `public readonly Game.Input.InputManager+DeviceType device`  
- `public readonly Game.Input.ActionType type`  
- `public readonly System.Boolean allowModifiers`  
- `public readonly System.Boolean developerOnly`  
- `public readonly Game.Input.Mode mode`  
- `public readonly System.Collections.ObjectModel.ReadOnlyCollection<System.String> interactions`  
- `public readonly System.Collections.ObjectModel.ReadOnlyCollection<System.String> processors`  
- `private readonly System.String[] customUsages`  

## Properties

- `public Game.Input.Usages usages { get }`  

## Constructors

- `protected SettingsUIInputActionAttribute(System.String name, Game.Input.InputManager+DeviceType device, Game.Input.ActionType type, System.Boolean allowModifiers, System.Boolean developerOnly, Game.Input.Mode mode, System.String[] customUsages, System.String[] interactions, System.String[] processors)`  
- `protected SettingsUIInputActionAttribute(System.String name, Game.Input.InputManager+DeviceType device, Game.Input.ActionType type, Game.Input.Mode mode, System.String[] customUsages)`  

