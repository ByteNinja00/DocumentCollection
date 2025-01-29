检查是否己安装git和conda，本文布署环境需要安装。
- 创建虚拟环境
```
conda create -n myenv python=3.10 -y
```
- 激活Conda环境
```
conda activate myenv
```
- 克隆Janus仓库
```
git clone https://github.com/deepseek-ai/Janus.git
```
- 进入 Janus 目录
```
cd Janus
```
- 安装 Janus 依赖
```
pip install -e .
```
- 安装 Gradio（UI）
```
pip install gradio
pip uninstall torch torchvision torchaudio -y
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
```
- 运行 Janus Pro UI
```
python demo/app_januspro.py
```
或强行调用GPU运行（速度更快）：
```
python demo/app_januspro.py --device cuda
```
安装完成以后，根据提示打开本地链接：http://127.0.0.1:7860 即可进入到使用面板

> 如果在安装软件依赖包时无法访问github或pip，请使用本地网络代理，前提是己经有科学上网环境。

- pip网络代理
```
pip config set global.proxy http://127.0.0.1:10809
```
- git网络代理
```
git config --global http.proxy http://127.0.0.1:10809
```
- 取消代理
```
git config --global --unset http.proxy
pip config unset global.proxy
```