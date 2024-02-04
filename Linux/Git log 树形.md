# Git log 树形

你可以通过在Git配置文件中设置别名来创建自定义的Git命令别名。要为给定的`git log`命令创建别名，你可以按照以下步骤进行操作：

1. 打开终端，并确保你在Git存储库的目录中。
2. 运行以下命令以编辑Git配置文件：

```bash
git config --global --edit
```

1. 在打开的配置文件中，你可以添加一个别名，例如：

```bash
[alias]
    lg = log --oneline --graph --all
```

1. 保存并关闭编辑器。

现在，你可以在终端中使用`git lg`命令来执行`git log --oneline --graph --all`。例如：

```bash
git lg
```

这将显示你所需的日志图形。请注意，`lg`只是一个示例别名，你可以选择任何你喜欢的名称。