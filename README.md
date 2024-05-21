# Object

# Video Upscale (Real-ESRGAN, IART) 

![image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2Fa8616105-5508-4c8d-93f9-9e47a410cd89%2F6abb5902-362c-4a89-b339-e20eee707546%2F%25ED%2599%2594%25EB%25A9%25B4_%25EC%25BA%25A1%25EC%25B2%2598_2024-05-07_115341.jpg?table=block&id=2b35bce1-d4d8-4209-b8a8-a573fafdb3f5&spaceId=a8616105-5508-4c8d-93f9-9e47a410cd89&width=2000&userId=f73d4ca6-c265-4f94-8d39-cd6c6399751c&cache=v2)


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

### 1. Postman 통신

![Untitled](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2Fa8616105-5508-4c8d-93f9-9e47a410cd89%2Fc3168894-360c-40e2-a4ef-c2c8790e6801%2FUntitled.png?table=block&id=b87d6a24-5cdd-4462-9206-d6cfa9141ba5&spaceId=a8616105-5508-4c8d-93f9-9e47a410cd89&width=2000&userId=f73d4ca6-c265-4f94-8d39-cd6c6399751c&cache=v2)

<br>
스프링 서버 엔드포인트

![Untitled](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2Fa8616105-5508-4c8d-93f9-9e47a410cd89%2F3b0052f0-2bf8-4ac2-acd5-4324a724d71a%2FUntitled.png?table=block&id=f819cf8e-e73b-4095-82ec-3e47bc676679&spaceId=a8616105-5508-4c8d-93f9-9e47a410cd89&width=2000&userId=f73d4ca6-c265-4f94-8d39-cd6c6399751c&cache=v2)

<br>

Flask 서버 엔드포인트

![Untitled](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2Fa8616105-5508-4c8d-93f9-9e47a410cd89%2F43da8291-fcac-4e3d-a66d-a83bb59cdeb8%2FUntitled.png?table=block&id=a6278f64-42d6-4cd1-8946-87f796b165bb&spaceId=a8616105-5508-4c8d-93f9-9e47a410cd89&width=1550&userId=f73d4ca6-c265-4f94-8d39-cd6c6399751c&cache=v2)

### 2. Input Video (Real-ESRGAN)



https://github.com/junu3148/Upscale/assets/134668162/52653814-ded8-4dee-9525-d2f3bd59b5e3




https://github.com/junu3148/Upscale/assets/134668162/57134615-8236-4cc3-b455-b333bf4b4d17



### 3. Output Video (Real-ESRGAN)



https://github.com/junu3148/Upscale/assets/134668162/0d06b8bd-3aff-4998-90e7-94b414d5adbc




https://github.com/junu3148/Upscale/assets/134668162/abf89506-95d2-4c7e-9477-3ad1b6a350a5




<br>
Codeformer를 사용하여 얼굴을 중점으로 복원하는 모델을 사용했습니다. 이 모델은 애니메이션에 특화되어 있어, 애니메이션의 완성도는 높았습니다. 그러나 영상의 사람 얼굴은 프레임마다 GAN 모델로 재생성되어, 영상을 결합했을 때 일관성이 유지되지 않았습니다.
<br>
<br>

### 1. 모델 (IART)

![image](https://github.com/junu3148/Upscale/assets/134668162/1d1aff22-c059-4035-bff8-f2caffce2405)



### 2. input Video (IART)




https://github.com/junu3148/Upscale/assets/134668162/538bf587-449c-4b0e-aa8c-680482629dcb




### 3. output Video (IART)




https://github.com/junu3148/Upscale/assets/134668162/22336c60-a8f3-46a4-b51b-91deddf1e648

노트북 성능 문제로 영상의 크기를 축소해서 실증했고, 모델분석 후 파라미터 조정해서 퀄리티 확인이 필요할 것 같습니다.


