
<div align="center">
  <img align="center" src="./img/logo.png" width="100" height="100" />
</div>

<h2 align="center"/>JarEditor <sup><em>liubsyy</em></sup></h2>

<!--<h4 align="center"><strong>English</strong> | <a href="./README_CN.md">简体中文</a></h4>-->

[![License](https://img.shields.io/github/license/Liubsyy/JarEditor?color=blue)](./LICENSE)
[![](https://img.shields.io/jetbrains/plugin/d/24397)](https://plugins.jetbrains.com/plugin/24397-jareditor)
[![release](https://img.shields.io/github/release/Liubsyy/JarEditor?color=red)](https://github.com/Liubsyy/JarEditor/releases)

IDEA plugin for modifying files in jar directly without decompression, including class and resource files.

**Plugin marketplace** : [https://plugins.jetbrains.com/plugin/24397-jareditor](https://plugins.jetbrains.com/plugin/24397-jareditor)

## Features
- Edit class/resource files in jar directly without decompression
- Add/Delete/Rename file/dictionary in jar
- Paste file/dictionary from clipboard
- Copy file/dictionary to clipboard
- Support springboot fatjar
- Support kotlin

## Quick start

### 1. Insatall plugin from marketplace
First install the plugin JarEditor from marketplace, IDEA at least version **2020.3**

<img src="./img/JarEditor_install.png" width="800" height="606" />


### 2. Edit and Save Jar
After installation , you can see a tab page to switch to Jar Editor in the .class decompiled file.

`External jars: File->Project Structure->Libraries->Add Library , then you can see the decompiled jar.`

<img src="./img/JarEditor_main.png" width="800" height="488" />

After modification, click **Save/Compile** to compile and save the currently modified java content. 

Finally click **Build Jar** to write the compiled and saved class file into the Jar package.

Modifying the resource files in the jar package is also supported.

### 3. Other operations of JarEditor
In the project view of the jar package, right-click to see **JarEditor->New/Delete** and other operations, where you can add/delete/rename/copy/paste files.

<img src="./img/JarEditor_new_delete.png" width="550" height="454" />


## Some mechanisms
- The JDK that the compilation depends on is the JDK of your SDK list. You can choose JDK and target version of the compiled class.
- The classpath you depend on when compiling java is the dependency of the project. If the dependency package cannot be found, you can add the dependency.
- Save/Compile will save the modified files to the jar_edit subdirectory of the directory where the jar package is located. Build Jar will incrementally write the files in the jar_edit directory to the jar, and finally delete this directory.

