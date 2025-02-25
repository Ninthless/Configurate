# Configurate

![GitHub Workflow Status](https://img.shields.io/github/workflow/status/SpongePowered/Configurate/Build)
![GitHub License](https://img.shields.io/github/license/SpongePowered/Configurate)
![Maven Central](https://img.shields.io/maven-central/v/org.spongepowered/configurate-core)
![Sonatype Nexus](https://img.shields.io/nexus/r/org.spongepowered/configurate-core)

Configurate 是一款用于 Java 应用程序的简单配置库，提供基于节点的数据表示，能够处理多种配置格式。

## 特性

- **多种格式支持**：支持 JSON、HOCON、YAML、XML 等配置文件格式。
- **灵活的 API**：提供简单的 API 来读取、更新和保存配置数据。
- **类型安全**：通过与 Java 类型系统的结合，确保配置数据的类型安全。
- **支持嵌套数据结构**：支持多层嵌套的配置文件，方便复杂配置的管理。

## 项目结构

项目分为不同的模块：

### Configurate 核心

`configurate-core` 是库的基础，包含用于操作配置的主要 API。它是通用的，不依赖于任何特定的配置格式。

### Configurate 加载器

每种不同的配置格式都作为一个“配置加载器”实现，位于单独的模块中。项目提供了多种加载器实现，但也可以单独实现自定义加载器以支持新的格式。

当前项目提供的加载器包括：

- `configurate-gson`：使用 Gson 库解析和生成 JSON 格式。
- `configurate-hocon`：使用 Lightbend Config 库解析和生成 HOCON 格式。
- `configurate-jackson`：使用 Jackson 库解析和生成 JSON 格式。
- `configurate-xml`：使用 JAXP 库解析和生成 XML 格式。
- `configurate-yaml`：使用 SnakeYAML 库解析和生成 YAML 格式。

### 扩展功能

一些与 Configurate 本身紧密集成的功能作为单独的模块提供：

- `configurate-extra-dfu[2-4]`：Mojang 的 DataFixerUpper 与 Configurate 系统的集成。
- `configurate-extra-kotlin`：允许 Configurate 类型使用 Kotlin 特性，并支持 Kotlin 数据类的对象映射。
- `configurate-extra-guice`：允许使用 Guice 的 `Injector` 在对象映射器中创建新对象实例。
