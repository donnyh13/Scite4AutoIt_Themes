# Scite4AutoIt-Themes

## Required Extension(s)

These themes have been made to specifically work with either, or both of the following Extensions, otherwise AutoIt syntax highlighting will be defaulted to VS code colorings:

* [AutoIt by Genius](https://marketplace.visualstudio.com/items?itemName=genius257.autoit)
* [AutoIt-VSCode by Logan](https://marketplace.visualstudio.com/items?itemName=damien.autoit)

## Intro

These themes are an attempt to copy the themes that come with Scite4AutoIt. Being that there are many further customizations available for VS Code compared to Scite, many colorations in VS Code may not match, and these may not be as well combined as they are in Scite, as VS Code colorizes things slightly different from Scite in some instances.

Because of the vast number of available settings and tokens for each language, it has been thought best to only have these custom themes apply to AutoIt files. I have used the token names from the two leading AutoIt extensions that are currently available, published by LoganCH and Genius257. When the user opens any other language file, the theme coloring will revert to the base theme's colorization for tokens, but not for the editor colors.

The base themes are three themes included with VS Code, VS Code Light, VS Code Dark, and Monokai, which are all MIT licensed, and belong to the respective owner(s). Copyright (c) Microsoft Corporation.

All Scite Themes, colorings and names are owned by the developers of Scite4AutoIt, and the respective theme creators, and I claim no ownership to any of them.

## Included in this Theme set

| Theme Name                    | Base VS Code Theme | Comment                                                   |
| ----------------------------- |  ----------------- | --------------------------------------------------------- |
| **Scite4AutoIt_Standard**     | *VS Code Light*    | Standard SciTE4AutoIt3 Color scheme                       |
| **Scite4AutoIt_Old_Standard** | *VS Code Light*    | Old Standard SciTE4AutoIt3 Color scheme                   |
| **Scite4AutoIt_MSDEV**        | *VS Code Light*    | Jon's Standard MSDEV Color scheme                         |
| **Scite4AutoIt_MSDEV2**       | *VS Code Light*    | Valiks' "Close to" MSDEV Color scheme                     |
| **Scite4AutoIt_Old_LCD**      | *VS Code Light*    | mLipok's Font & Color scheme for low contrast LCD Display |
| **Scite4AutoIt_Monokai**      | *VS Code Monokai*  | Monokai Color scheme                                      |
| **Scite4AutoIt_Twilight**     | *VS Code Dark*     | Twilight Color scheme                                     |
| **Scite4AutoIt_Dark**         | *VS Code Dark*     | Dark SciTE4AutoIt3 Color scheme                           |

## Note

For those users on older Windows versions, and unable to update VS Code to later versions, the following should be noted. The extension created by LoganCH became incompatible from version 1.0.14+ with Vs Code 1.70.3, (the latest available on Windows 7). In Logan's versions 1.4.0, and 1.5.0 there were several modifications and additions that make tokenization better, and cleaner, which users on older systems will not be able to benefit from. As a possible work around, see below.

As of the time of writing (May, 2026), Genius257's extension (v1.8.9) is still compatible with VS Code 1.70.3, and does not present these issues.

### Possible Workaround

Being under the above limitations myself, I have found the following workaround. Any users with some coding experience can follow the following steps at their own risk. These directions work for Logan's version 1.5.0. I make no guarantee it will work with later versions.

1. Download a copy of Logan's extension files from his GitHub, or, minimally, a copy of the file **autoit.tmLanguage.json**, found in the syntaxes file. (Make sure to get the file with the .json extension).
2. Locate your VS Code extensions folder, mine was found at the following location:
    * C:\Users\Owner\.vscode\extensions
3. Make a copy of Logan's extension folder somewhere else, in case something goes wrong, the extension folder is named: `damien.autoit-1.0.13` or similar.
4. Open Logan's extension folder found in the VS Code extension folder (not the copy you made).
5. Find and open the `package.json` file.
    1. Inside the `package.json` file, find the following line, (Mine was around line 225):
    > "grammars": [  
    > {  
    > "language": "autoit",  
    > "scopeName": "source.autoit",  
    > "path": "./syntaxes/autoit.tmLanguage"  
    > },  
    > {  
    > "language": "vscode-autoit-output",  
    > "scopeName": "source.vscode_autoit_output",  
    > "path": "syntaxes/vscode-autoit-output.tmLanguage.json"  
    > }  
    > ],  
    2. Edit the **"path"** line for **"language": "autoit"**
    * From
    > "path": "./syntaxes/autoit.tmLanguage"
    * To:
    > "path": "./syntaxes/autoit.tmLanguage.json"
    3. Save and close the file.
6. Navigate to inside the `Syntaxes` folder.
7. Copy the new **autoit.tmLanguage.json** file into this folder, replacing the existing file, if present.
8. Close VS Code if open, and open an AutoIt Script in VS Code to make sure everything is colorized properly, and that no errors are present.

* Fun fact, as of Logan's version 1.5.0, the source files can be still successfully compiled with the latest compatible webpack and babel loader packages installed. With minimal testing, the extension is fully functional with all new features.
