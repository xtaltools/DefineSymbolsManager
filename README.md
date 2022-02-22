
# Define Symbols Manager

Version 1.0.0

- Unity Asset Store: https://assetstore.unity.com/packages/slug/207960 
- GitHub: https://github.com/xtaltools/DefineSymbolsManager

## What is it?

This is a tool for efficient management of Define Symbols.

- List the status of DefineSymbols for each platform.
- DefineSymbols can be given a description to make them easier to understand.
- You can also save disabled DefineSymbols to enable them at any time.
- Batch switching of DefineSymbols by profile is possible. (Release, Development, etc.)
- Multiple platforms can be renamed at once.

## How to use it?

### Open the DefineSymbols Manager.

Menu: Edit > Project Settings > Define Symbols

### Set define symbols state

1. Please check to enable or disable the define symbols.
2. Apply the changes  to Project Settings by clicking the Apply button.

### Rename DefineSymbols

 1. Double click the DefineSymbol name label you want to rename.
 2. Type the new name in the text field.
 3. Apply the name by clicking elsewhere to make the text field unfocused.

### Command line arguments

You can specify DefineSymbol externally when doing a batch build.
This can be used to switch between development builds, release builds, etc.

For instructions on how to launch a batch build, please refer to the following page.
https://docs.unity3d.com/Manual/CommandLineArguments.html

| Argument                             | Description                                                                                                             |
|--------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| -define <SYMBOL1,SYMBOL2>            | Enables the specified DefineSymbol. Specify the value separated by a comma or semicolon.　ex) `-define ENABLE_DEBUGMENU` |
| -defineSymoblProfile \<Profile Name> | Change current Profile and Set the DefineSymbol states.|


### Usage from scripts

#### Update DefineSymbol states

```csharp
var profile = DefineSymbols.CurrentProfile;
profile["ENABLE_DEBUG_MENU"].Enable();
profile.ApplyToProjectSettings();
```

#### Change current profile

```csharp
var devProfile = DefineSymbols.GetProfile("Development");
devProfile.ApplyToProjectSettings();
```

## Commit required files to VCS

Please commit the following files:
- ProjectSettings/DefineSymbolSettings.asset

## Copyright

Copyright (c) 2022 xtaltools, Atsuhito Machida (neptaco). All rights reserved.
