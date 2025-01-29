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
