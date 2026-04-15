# H7 本地接入与 GitHub 切换说明

## 当前状态

当前总控仓库中的 `H7/` 已切换为 GitHub 子模块：

- 子模块路径：`H7/`
- 当前远端 URL：`git@github.com:zuoliangyu/zuolan_signal_H7.git`

当前状态对应的迁移与发布已经完成。

## 历史说明

- 你当前 `H7` 仓库还没有推到 GitHub
- 但总控仓库结构已经需要先落下来
- 所以先用本地路径建立子模块关系，再在后续切换到正式远程地址

## 后续推荐流程

### 1. 在 `H7/` 内完成本地整理

建议至少完成：

- 确认目录改名是否最终定为 `zuolan_signal_STM32_H7/`
- 提交这次迁移改动

### 2. 把 `H7` 仓库推到 GitHub

推送后拿到正式仓库地址，例如：

```text
git@github.com:<your-org-or-user>/zuolan_signal_STM32_H7.git
```

或：

```text
https://github.com/<your-org-or-user>/zuolan_signal_STM32_H7.git
```

### 3. 在根仓库切换子模块 URL

在总控仓库根目录执行：

```powershell
git submodule set-url H7 <H7正式仓库地址>
```

### 4. 提交根仓库更新

切换 URL 后，在根仓库提交：

- `.gitmodules`
- `H7` 子模块指针

## 注意

- 在切到正式 GitHub URL 之前，不建议把当前 `.gitmodules` 直接作为公开协作入口长期使用。
- 如果后续新增 `F4`、`TI`、`F4_FPGA`，建议直接先建远程仓库，再接子模块，这样流程会更干净。
