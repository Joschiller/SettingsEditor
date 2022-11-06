# SettingsEditor

- [1 Introduction](#1-introduction)
- [2 API](#2-api)
  - [2.1 SettingsEditor (UserControl)](#21-settingseditor-usercontrol)
  - [2.2 SettingsEditorItem (interface)](#22-settingseditoritem-interface)

## 1 Introduction

The `SettingsEditor` provides a centralized settings control that automatically renders all available settings controls (`SettingsEditorItem`s) via reflections. That way the controls can easily be expanded without the need of a manual change to any settings menu.

## 2 API

### 2.1 SettingsEditor (UserControl)

> Renders all `UserControl`s that implement the `SettingsEditorItem` interface.
>
> The `SettingsEditorItem`s can be grouped by using the `SettingsEditorItem.GetTabName`.
>
> The `SettingsEditor` offers methods for the common loading, validation and saving of settings.

Accessible Interface:

```c#
public SettingsEditor()

public void LoadData(int? identification)
public bool ValidateData()
public void SaveData()
```

### 2.2 SettingsEditorItem (interface)

> An item that will be rendered within the `SettingsEditor`.
>
> Implement this interface within any `UserControl` to let the `UserControl` be rendered within any generated instance of the `SettingsEditor`.

Accessible Interface:

```c#
void LoadData(int? accountIdentifier)
bool ValidateData()
void SaveData()

string GetTabName()
string GetControlName()
bool IsVisible()
```
