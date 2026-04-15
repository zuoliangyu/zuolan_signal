# zuolan_signal

`zuolan_signal` 是信号处理多方案总控仓库。

当前目标是统一管理以下独立方案仓库：

- `H7`
- `F4`
- `TI`
- `F4_FPGA`

## 仓库职责

- 管理子模块接入关系
- 提供方案总览与选型导航
- 维护跨方案协作规则
- 记录各方案版本映射关系

## 当前结构

- `H7/`
  - 当前已接入的 `STM32H7` 方案子模块
- `F4_FPGA/`
  - 当前已接入的 `STM32F4 + FPGA` 协同方案子模块
- `docs/`
  - 总览、协作规范与后续维护文档

后续将按同样方式接入：

- `F4/`
- `TI/`

## 子模块使用

首次完整拉取建议使用：

```powershell
git clone --recurse-submodules <总控仓库地址>
```

若仓库已拉取，再初始化子模块：

```powershell
git submodule update --init --recursive
```

## 当前状态

- 根仓库已建立总控骨架
- `H7` 先以本地仓库方式接入
- `.gitmodules` 当前记录的是本机本地路径 `C:/Users/zuolan/Desktop/zuolan_signal_STM32`
- `H7` 当前已同步你本地工作树，包含尚未在该子仓库内提交的迁移改动
- `F4_FPGA` 先以本地仓库方式接入
- `.gitmodules` 当前记录的是本机本地路径 `E:/competition/EE/Electronic/EE_OBJECT/zuolan_signal_fpga_stm32`
- `F4_FPGA` 当前已同步你本地工作树，并额外归档了旧代码压缩包 `F4_FPGA/old_code.zip`
- 待 `H7` 推送到 GitHub 后，再把子模块 URL 切换为正式远程地址
- 待 `F4_FPGA` 推送到 GitHub 后，再把子模块 URL 切换为正式远程地址

详细说明见：

- `docs/README.md`
- `docs/子模块协作规范.md`
- `docs/方案总览.md`
