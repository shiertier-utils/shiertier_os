# shiertier_os

[English](https://github.com/shiertier-utils/shiertier_os/blob/main/README.md) | 中文

## 简介

`shiertier_os` 是一个 Python 实用工具库，旨在简化环境变量的管理。它提供了获取、设置和转换环境变量的功能，使您在应用程序中处理环境配置更加容易。

## 安装

您可以通过 `pip` 安装 `shiertier_os`：

```bash
pip install git+https://github.com/shiertier/shiertier_os.git
```

请注意，该项目仍在开发中。

## 使用方法

### 获取环境变量

您可以使用 `get_env` 函数来检索环境变量。该函数允许您指定一个默认值，如果环境变量未设置，则返回该默认值。如果值包含逗号，它将被转换为列表。

```python
from shiertier_os import get_env

# 获取环境变量
value = get_env('MY_VAR', default_value='default')
print(value)

# 获取环境变量并将其转换为列表
value_list = get_env('MY_LIST_VAR', default_value='item1,item2,item3')
print(value_list)
```

### 设置环境变量

您可以使用 `set_env` 函数来设置环境变量。如果值是一个列表，它将在设置之前被转换为字符串。

```python
from shiertier_os import set_env

# 设置环境变量
set_env('MY_VAR', 'new_value')

# 从列表设置环境变量
set_env('MY_LIST_VAR', ['item1', 'item2', 'item3'])
```

### 获取配置变量

您可以使用 `get_var` 函数来检索配置变量。该函数首先检查环境变量是否已设置。如果没有，它将返回提供的配置值。

```python
from shiertier_os import get_var

# 获取配置变量
config_value = get_var('MY_VAR', 'default_config_value')
print(config_value)
```

### 字符串与列表之间的转换

该库还提供了实用函数，用于在字符串和列表之间进行转换：

- `convert_str_to_list(s)`: 将逗号分隔的字符串转换为列表。
- `convert_list_to_str(l)`: 将列表转换为逗号分隔的字符串。

```python
from shiertier_os import convert_str_to_list, convert_list_to_str

# 将字符串转换为列表
my_list = convert_str_to_list('item1,item2,item3')
print(my_list)

# 将列表转换为字符串
my_string = convert_list_to_str(['item1', 'item2', 'item3'])
print(my_string)
```

## 许可证

本项目基于 MIT 许可证发布。有关详细信息，请参阅 [LICENSE](LICENSE) 文件。