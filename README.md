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
- `H7` 已发布到 GitHub：`git@github.com:zuoliangyu/zuolan_signal_H7.git`
- `F4_FPGA` 已发布到 GitHub：`git@github.com:zuoliangyu/zuolan_signal_F4_FPGA.git`
- `.gitmodules` 已切换为 GitHub SSH URL
- 根仓库远端为：`git@github.com:zuoliangyu/zuolan_signal.git`
- `F4_FPGA` 保留了旧代码压缩归档 `old_code.zip`

详细说明见：

- `docs/README.md`
- `docs/子模块协作规范.md`
- `docs/方案总览.md`
