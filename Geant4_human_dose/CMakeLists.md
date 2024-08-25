# human_dose CMakeLists.txt comments

## Set the project

```cmake {.line-numbers}
cmake_minimum_required(VERSION 3.16...3.27)
project(human_dose)
```

### cmake_minimum_required()[<i class="fa-solid fa-link fa-2xs" style="color: #0091ff;"></i>][cmake_minimum_required]

`cmake_minimum_required(VERSION <min>[...<policy_max>] [FATAL_ERROR])`

作用是将变量`CMAKE_MINIMUM_REQUIRED_VERSION`设置为`<min>`。

其中，`<policy_max>`是3.12及以后版本新特性。`<min>`和可选项`<policy_max>`的形式为`major.minor[.patch[.tweak]]`。`...`就和字面上的意思一样，同时当版本低于3.12时，`...<max>`将被忽略，进而保护了代码的可移植性。

`FATAL_ERROR`被2.6及以上版本接受并忽略，但建议被加上；以用`error`来替换2.4及以下版本的`warning`。2.5会怎么样我也不知道，但一般没有人会用那么古老的版本吧。。。

Notes:

- 在文档的最前面调用`cmake_minimum_required`命令，因为后面的命令基本上都应依赖于特定的版本。
- 由于作用域的问题，不建议在`function()`中使用`cmake_minimum_required`。

### project()[<i class="fa-solid fa-link fa-2xs" style="color: #0091ff;"></i>][project]{#project}

```cmake {.line-numbers}
project(<PROJECT-NAME> [<language-name>...])
project(<PROJECT-NAME>
        [VERSION <major>[.<minor>[.<patch>[.<tweak>]]]]
        [DESCRIPTION <project-description-string>]
        [HOMEPAGE_URL <url-string>]
        [LANGUAGES <language-name>...])
```

设置项目的名称，并存储在变量`PROJECT_NAME`中。顶层调用时，`CMakeLists.txt`也会将其存储在变量`CMAKE_PROJECT_NAME`中。

同时设置了以下变量：

- `PROJRCT_SOURCE_DIR, <PROJECT-NAME>_SOURCE_DIR`
  - *project*的绝对路径
- `PROJECT_BINARY_DIR, <PROJECT-NAME>_BINARY_DIR`
  - *project*二进制目录的绝对路径
- `PROJECT_IS_TOP_LEVEL, <PROJECT-NAME>_IS_TOP_LEVEL`
  - 3.21版新特性。布尔类型值，代表是否为顶层

#### Options

原型中出现的其他参数是可选变量，具体作用暂时我还不明白，感兴趣的可以点击[project](#project)后面的链接查看官网文档。

#### Usage

一个项目的顶层文件`CMakeLists.txt`必须包含直接调用`projrct()`的命令，通过`include()`加载是无效的。没有的话，CMake将会给出一个警告并假设在顶层有一个`project(Project)`来请用默认语言(C和CXX)。

Notes:

- 通常情况下，请在`cmake_minimum_required`后面直接调用`project`，原因就是前面说的那样。

## Find Geant4 Packages {#find-geant4-packages}

```cmake {.line-numbers}
option(WITH_GEANT4_UIVIS "Build example with Geant4 UI and Vis drivers" ON)
if(WITH_GEANT4_UIVIS)
  find_package(Geant4 REQUIRED ui_all vis_all)
else()
  find_package(Geant4 REQUIRED)
endif()
```

### option()

`option(<variable> "<help_text>" [value])`

提供一些用户可选的选项，用布尔值表示用户的选择。[Find Geant4 Packages](#find-geant4-packages)例子中给出了一个选项`WITH_GEANT4_UIVIS`，默认值为`ON`。用来启用Geant4 UI(用户界面)和Vis(可视化界面)驱动。

进而，下面的判断语句会根据用户的选项选择是否查找Geant4 ui_all和vis_all包(暂时我也说不准这两个包具体是什么，应该时提供用户交互命令和图形界面的；多的就不知道了)。

最后，用户可以通过直接修改`CMakeLists.txt`文件中的`WITH_GEANT4_UIVIS`的值来选择是否启用Geant4 UI和Vis。或者在命令行编译文件时加上命令`-DWITH_GEANT4_UIVIS=OFF`来禁用(这种用法更具灵活性)。

Notes:

- \[value\]的默认值为OFF
- 命令对常规变量和缓存变量无效
- 对于依赖于其他选项值的变量可以参考[`CMakeDependentOption`][CMakeDependentOption]

[cmake_minimum_required]: https://cmake.org/cmake/help/v3.28/command/cmake_minimum_required.html#cmake-minimum-required "cmake_minimum_required"
[project]: https://cmake.org/cmake/help/v3.28/command/project.html#project "project"
[CMakeDependentOption]: https://cmake.org/cmake/help/v3.28/module/CMakeDependentOption.html#module:CMakeDependentOption "CMakeDependentOption"
