# Object recognition

![image](https://github.com/junu3148/Object/assets/134668162/e4c45354-6a80-41ed-b5ba-120f8ee0fadc)



## 사용 기술

### Spring boot Server

Open JDK 17, Spring boot, Gradle, Spring data JPA, Postgresql 

GitHub, Docker, FFmpeg
<br>

### Fast Server

GPU - RTX 3060

Anaconda 3

<br>
AI model - codeformer, Real-ESRGAN <br> 
FastAPI, Python 3.8, PyTorch 2.3, CUDA 11.4,  OpenCV 4.9, FFmpeg <br> 
<a href="https://github.com/sczhou/CodeFormer">
    <img src="https://github.com/junu3148/Upscale/assets/134668162/7d63c0b6-0c8b-44b4-bd4e-ca28e607acb0" alt="CodeFormer Image">
</a>

<br><br>
AI model -  IART <br> 
FastAPI, Python 3.9, PyTorch 1.13, CUDA 11.7,  OpenCV 4.9, FFmpeg <br> 
<a href="https://github.com/kai422/IART">
    <img src="https://github.com/junu3148/Upscale/assets/134668162/0c664e1e-8135-4750-b463-f50a90f8323f" alt="IART Image">
</a>


---

## 담당한 기능 (기여도 100%)

### Spring boot 서버 구현

- Upscale
    - 원본 파일 저장
    - FFmpeg 사용 2초 시간대 썸네일 추출 이미지 저장
    - Flask API 통신으로 Upscale 된 비디오 저장
    - 영상의 메타정보와 함께 스트리밍 URL 경로 반환
- 히스토리 조회
    - AI 옵션에 맞는 작업 내용 리스트 조회

### Fast 서버 구현

- Upscale 엔드포인트
    - input 파일 저장
    - AI 모델을 통한 업스케일링
    - output 파일 저장
    - 파일 반환
    - 반환 후 파일 삭제

```bash
pip install fastapi
pip install uvicorn
pip install aiofiles
conda install -c conda-forge ffmpeg
```
### AI model 세팅 (Real-ESRGAN)

```bash
git clone this repository
git clone https://github.com/sczhou/CodeFormer
cd CodeFormer
create new anaconda env
conda create -n codeformer python=3.8 -y
conda activate codeformer
install python dependencies
pip3 install -r requirements.txt
python basicsr/setup.py develop
conda install -c conda-forge dlib (only for face detection or cropping with dlib)
conda install -c conda-forge ffmpeg
```
### AI model 세팅 (IART)

```bash
git clone https://github.com/kai422/IART
cd IART
pip install torch==1.13.1+cu117 torchvision==0.14.1+cu117--extra-index-url https://download.pytorch.org/whl/cu117
pip install -r requirements.txt
가중치 : https://drive.google.com/drive/folders/
1MIUK37Izc4IcA_a3eSH-21EXOZO5G5qU
경로 : ./experiments./pretrained_models/
pip install basicsr
pip install timm
conda install -c conda-forge ffmpeg
```
---



