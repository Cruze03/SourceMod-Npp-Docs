![Docs screenshot](https://github.com/raziEiL/SourceMod-Npp-Docs/blob/master/img/docs.png "Inline docs")
# SourceMod-Npp-Docs
[![GitHub release](https://img.shields.io/github/release/raziEiL/SourceMod-Npp-Docs.svg?colorB=97CA00?label=version)](https://github.com/raziEiL/Notes-pp/releases/latest)
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/razicat)   
Here the new API docs with all (I hope) function, define, enum, methodmap and fixed xml structure. Docs were generated by reworked generator plugin.

# Plugin

### Features:
 - Generate auto-completion files.
 - Generate inline docs (*sourcemod.xml*).
 - Supports SourceMod 1.7 API specifics.
 
### New in v1.2:
 - Added xml filter.
 - Added more console stats.
 - Better way to detect commentary lines.
 - Code optimization.
 - Detect methodmap.
 - Detect enum & define correctly.
 - Detect all func params.
 - Makes keywords to pop up correctly
 
### Server command:
**sm_makedocs** - starts to parse SourceMod includes and generates output files.

# Notepad++

## Autocompletion
API files are located in the **plugins\APIs\\** subfolder of the Notepad++ installation folder. Use **sm_makedocs** command to generate docs. Files will be created in the **plugins\NPP\\** subfolder of sourcemod folder. Copy **sourcemod.xm**l file to Notepad++ API folder. The completion list can be triggered automatically as you type, via settings in **Settings -> Preferences -> Auto-Completion:** Auto-Completion is enabled by a checkbox. Additionally there is a setting "From X th character", accepting a the minimum length of a prefix needed before the completion list is shown (some people like 2, some 3, some 4...); and, there is a setting to specify which candidates should be used: words, functions, or both.

## Highlights
Check **plugins\NPP\\** folder for **NPP_STYLE** files. These files contain defining the keyword lists for the SourcePawn language. Open one of those files, select keywords and copy. Go to **Notepd++ -> Lanuguage -> Define your language...** Create new language and past keywords to the Keywords Lists group. Configurate you own style. Read more about [UDL 2.0](https://udl20.weebly.com/index.html)

# Methodmap notes
![Docs screenshot](https://github.com/raziEiL/SourceMod-Npp-Docs/blob/master/img/docs%20list.png "Inline docs: methodmap strings")  
These strings are not exist SourceMod function! Purpose of these strings provide access to docs and show methodmap structure. Notepad++ don't reacts on dots in names (exp: LineNumber.get) and docs not shown, so `.` were separated with `_` symbol.
>**Note:** If you want to use string as code you must remove prefix and separate `_` with `.`  
>**Note:** If you want to watch docs you must do the vice versa.

## Prefix structure:

| Type | With tag | Without tag |
|------| ------ | ------ |
| Constructor | METHODMAP_`%1`_`%2`\_CONSTRUCTOR\_`%3` | METHODMAP_`%1`\_CONSTRUCTOR_`%3` |
| Method | METHODMAP_`%1`_`%2`_METHOD\_`%3` | METHODMAP_`%1`\_METHOD_`%3` |
| Property | METHODMAP_`%1`_`%2`_PROP\_`%3` | METHODMAP_`%1`_PROP\_`%3` |

Where: `%1` - Class name, `%2` - Tag name, `%3` - Real method/property/constructor name.

**PREFIX** - Text before `%3` param (e.g., `METHODMAP_ArrayList_Handle_METHOD_`GetArray).

## Examples:

**Editing string to watch docs:**  
Method: Clone  
Prefix: METHODMAP_ArrayList_Handle_METHOD_  
Result: METHODMAP_ArrayList_Handle_METHOD_Clone

**Editing string to use as code:**  
Docs string: METHODMAP_ArrayStack_PROP_BlockSize_get  
Removes prefix: METHODMAP_ArrayStack_PROP_  
Result: my_code.BlockSize.get()

# Credits:
 - Thanks [@MCPAN](https://forums.alliedmods.net/member.php?u=73370) for original plugin.
 
# Donation
My cat wants a new toy! I try to make quality and beautiful toys for my beloved cat. I create toys in my spare time but sometimes I can step into a tangle and get confused! Oops! It takes time to get out! When the toy is ready I give it to the cat, the GitHub cat and the community can also play with it. So if you enjoy my toys and want to thank me for my work, you can send any amount. All money will be spent on milk! [Donate:feet:](https://www.paypal.me/razicat)
