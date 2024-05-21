# Object recognition

![image](https://github.com/junu3148/Object/assets/134668162/e4c45354-6a80-41ed-b5ba-120f8ee0fadc)



## 사용 모델

Ubuntu 22.04(워크스테이션)
Anaconda
VS Code
Python 3.8.0

<br>
AI model - cloth-segmentation <br> 
FastAPI, Python 3.8, PyTorch 1.3, CUDA 11.3,  OpenCV 4.9, FFmpeg <br> 
<a href="https://github.com/levindabhi/cloth-segmentation">
      <img src="https://github.com/junu3148/Object/assets/134668162/a694d11c-723d-45e7-a888-b722504b7412" alt="cloth Image">
</a>

<br><br>


---

## 객체 분리 실증




### AI model 세팅 (Real-ESRGAN)

```bash
git clone https://github.com/levindabhi/cloth-segmentation
cd cloth-segmentation

git clone https://github.com/levindabhi/cloth-segmentation.git
cd cloth-segmentation

conda install pytorch torchvision torchaudio cudatoolkit=11.3 -c pytorch
conda install -c conda-forge tensorboardx
pip install gdown

python setup_model_weights.py

python train.py

python -m torch.distributed.launch --nnodes=1 --node_rank=0 --nproc_per_node=4 --use_env train.py

python infer.py


```
## 1. 모델 예시 아웃풋
![000](https://github.com/junu3148/Object/assets/134668162/24b7942c-8e30-4c59-80f3-83f963230824)

## 2. 테스트 원본 이미지
![frame_0000](https://github.com/junu3148/Object/assets/134668162/886c142d-d5fb-4fd1-8cec-176266c24dbc)

## 2. 세그먼트 분리 이미지
![frame_0000](https://github.com/junu3148/Object/assets/134668162/fd3c739b-d314-494b-85dc-772c91d365ae)



