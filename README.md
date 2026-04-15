# zuolan_signal

`zuolan_signal` 是一个信号处理多方案总控仓库，用来统一管理不同硬件路线下的独立实现仓库。

当前仓库的职责不是承载所有业务代码，而是负责：

- 管理各方案子模块
- 提供方案导航与选型入口
- 维护跨方案协作规则
- 统一整理总控层文档

## 当前方案

| 方案 | 定位 | 状态 | 仓库 |
| --- | --- | --- | --- |
| `H7` | `STM32H7` 主控方案 | 已接入 | [zuolan_signal_H7](https://github.com/zuoliangyu/zuolan_signal_H7) |
| `F4` | `STM32F4` 单片机方案 | 预留 | 待创建 |
| `TI` | `TI` 平台方案 | 预留 | 待创建 |
| `F4_FPGA` | `STM32F4 + FPGA` 协同方案 | 已接入 | [zuolan_signal_F4_FPGA](https://github.com/zuoliangyu/zuolan_signal_F4_FPGA) |

## 仓库结构

```text
zuolan_signal/
├─ H7/         # STM32H7 子模块
├─ F4_FPGA/    # STM32F4 + FPGA 子模块
└─ docs/       # 总控层文档
```

后续计划按同样方式继续接入：

- `F4/`
- `TI/`

## 快速入口

- 总控仓库文档索引：[docs/README.md](docs/README.md)
- 方案总览：[docs/方案总览.md](docs/%E6%96%B9%E6%A1%88%E6%80%BB%E8%A7%88.md)
- 子模块协作规范：[docs/子模块协作规范.md](docs/%E5%AD%90%E6%A8%A1%E5%9D%97%E5%8D%8F%E4%BD%9C%E8%A7%84%E8%8C%83.md)
- H7 发布说明：[docs/H7本地接入与GitHub切换说明.md](docs/H7%E6%9C%AC%E5%9C%B0%E6%8E%A5%E5%85%A5%E4%B8%8EGitHub%E5%88%87%E6%8D%A2%E8%AF%B4%E6%98%8E.md)
- F4_FPGA 发布说明：[docs/F4_FPGA本地接入与旧代码归档说明.md](docs/F4_FPGA%E6%9C%AC%E5%9C%B0%E6%8E%A5%E5%85%A5%E4%B8%8E%E6%97%A7%E4%BB%A3%E7%A0%81%E5%BD%92%E6%A1%A3%E8%AF%B4%E6%98%8E.md)

## 当前已接入仓库

### H7

- 子模块路径：`H7/`
- GitHub：`git@github.com:zuoliangyu/zuolan_signal_H7.git`
- 说明：当前已完成从 `zuolan_signal_STM32` 到 `zuolan_signal_STM32_H7` 的工程目录重命名

### F4_FPGA

- 子模块路径：`F4_FPGA/`
- GitHub：`git@github.com:zuoliangyu/zuolan_signal_F4_FPGA.git`
- 说明：当前保留了一份历史参考压缩归档 `old_code.zip`

## 使用方式

首次克隆建议直接带上子模块：

```powershell
git clone --recurse-submodules git@github.com:zuoliangyu/zuolan_signal.git
```

如果仓库已经拉下来了，再初始化子模块：

```powershell
git submodule update --init --recursive
```

更新子模块后，记得回到根仓库提交子模块指针：

```powershell
git add H7 F4_FPGA .gitmodules
git commit -m "更新子模块指针"
```

## 协作约定

- 根仓库只管理总控层内容，不长期堆放具体方案源码
- 每个子模块都应维护自己的 `AGENTS.md`
- 接口、流程、路径、子模块 URL 变化时，同步更新根仓库文档
- 编译产物、过程性文件、IDE 本地缓存默认不进入版本库

## 当前状态

- 总控仓库已发布到 GitHub
- `H7` 与 `F4_FPGA` 已切换为 GitHub 子模块
- `F4` 与 `TI` 仍处于预留阶段
