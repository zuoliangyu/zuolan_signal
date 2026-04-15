# F4_FPGA 本地接入与旧代码归档说明

## 当前状态

当前总控仓库中的 `F4_FPGA/` 以本地子模块方式接入：

- 子模块路径：`F4_FPGA/`
- 当前本地 URL：`E:/competition/EE/Electronic/EE_OBJECT/zuolan_signal_fpga_stm32`

同时，`F4_FPGA/` 已同步你本地仓库的当前工作树，因此里面保留了源仓库当前的本地改动与未跟踪文件。

## 旧代码归档

这套方案对应的旧代码压缩包已复制到：

- `F4_FPGA/old_code.zip`

当前按“历史参考代码压缩归档”处理，不单独作为子模块。

这样做的目的：

- 保留旧实现作对照
- 后续做寄存器、总线、时序或驱动迁移时有参考基线
- 避免再额外维护一个旧代码仓库关系

## 当前特别注意

`F4_FPGA/` 子仓库里目前至少包含两类尚未提交内容：

- 源仓库本身已有的未跟踪文档 `Doc/开发/Untitled.md`
- 新复制进来的 `old_code.zip`

因此当前 `F4_FPGA` 是可继续整理开发的状态，但还不是一个干净的正式子模块提交点。

## 后续推荐流程

### 1. 在 `F4_FPGA/` 内完成本地整理

建议至少完成：

- 判断 `Doc/开发/Untitled.md` 是否保留并提交
- 判断 `old_code.zip` 是否纳入版本管理，或补充内部说明文档

### 2. 把 `F4_FPGA` 仓库推到 GitHub

推送后拿到正式仓库地址，例如：

```text
git@github.com:<your-org-or-user>/zuolan_signal_fpga_stm32.git
```

或：

```text
https://github.com/<your-org-or-user>/zuolan_signal_fpga_stm32.git
```

### 3. 在根仓库切换子模块 URL

在总控仓库根目录执行：

```powershell
git submodule set-url F4_FPGA <F4_FPGA正式仓库地址>
```

### 4. 提交根仓库更新

切换 URL 后，在根仓库提交：

- `.gitmodules`
- `F4_FPGA` 子模块指针
