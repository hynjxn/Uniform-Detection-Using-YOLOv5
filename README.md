# Uniform Detection Using YOLOv5

<div align="center">
    <img src="https://user-images.githubusercontent.com/68190553/160357007-8491d572-6e1c-47a5-9c5b-37ffdb9db4cb.png" width="40%"/><br/><br/>
<h2 align=center>This repo is a project to detect students bad uniforms using YOLOv5 🚀</h2>
</div>

<div align="center">
    <img alt="Detect your uniform" src="https://user-images.githubusercontent.com/68190553/161419129-009cbce5-6169-4fcc-80ce-34b66f3661aa.png" width="80%"/><br/><br/>
</div>
Korean schools have rules for wearing neat school uniforms to school.However, some students go to school wearing school uniforms that are not neat or mended.Therefore, in Korean schools, student instructors often give penalty points to students who do not wear neat school uniforms.<br/><br/>

We decided that this process was very subjective and wasted manpower, so we planned this project to replace it with the role of artificial intelligence.
This project not only proposes artificial intelligence that replaces the role of the student instructor, but also proposes a service that can manage penalty points and attendance.
<br/> <br/>

> **Considering the limitations of data collection, this project was carried out on the premise of certain conditions.**<br/>
> i) It's a girls' high school where skirts and shirts are school uniforms.<br/>
> ii) Consider summer clothes only <br/>


<!--
한국 학교는 단정한 교복을 입고 등교하는 학칙이 있습니다. 
하지만 몇몇 학생들은 치마길이를 수선하거나 단정하지 않은 교복을 입고 등교합니다.
때문에 한국 학교에선 학생지도선생님이 직접 단정한 교복을 입지 않은 학생들에게 벌점을 주곤 합니다.

우리는 이 과정이 매우 주관적이며 인력이 낭비되는 것이라 판단해, 
이를 인공지능의 역할로 대체하고자하여 이 프로젝트를 기획했습니다. 

위 프로젝트는 선도부 역할을 대신하는 인공지능을 제안할 뿐 아니라 벌점과 출석도 관리할 수 있는 서비스를 제안합니다.


이 프로젝트는 데이터 수집의 한계성을 고려해 특정 조건을 전제하여 진행했습니다.<br/>
i) 치마와 와이셔츠가 교복인 여자 고등학교라 가정<br/>
ii) 여름에 입는 하계복만 고려<br/>
-->

---

## Documentation
### Proejct Structure
<div align="center">
    <img src="https://user-images.githubusercontent.com/68190553/161418538-3f6b0638-cbf1-4b7c-ada9-0c8fbd3a0ac6.png" width="80%"/>
</div>

### ERD
<div align="center">
    <img alt="image" src="https://user-images.githubusercontent.com/68190553/160404256-b3197ffb-cae6-4ead-ab35-ab9b25a02469.png" width="25%">
</div>

### Model Performance
<div align="center">
    <img src="https://user-images.githubusercontent.com/68190553/160384008-b2581bf0-6c54-4471-9ac0-d423a3ed2945.png" width="50%"/>
</div>
<details open>
<summary>YOLOv5 🚀</summary>
<div align="center">
    <img src="https://user-images.githubusercontent.com/68190553/160385861-c3a7b89d-4af5-4a18-b157-11f06664e9c9.png" width="90%"/><br/>
    Our model was trained with 1,500 data and exhibits stable performance. (mAP@0.5 : 0.940)<br/>
    And We trained a total of 400 iterations using W&B, one of MLOps.
</div>



</details>

### Members
```
- Jaewoo Park (jerife@naver.com)
- Hyunjin Lee (shsan0324@gmail.com)
- Minah Choi (mina7245@gmail.com)
- Eunsu Shin (ses2201@g.hongik.ac.kr)
```
---

## Usage
### Installation with virtual environment
```bash
$ git clone https://github.com/hynjxn/Uniform-Detection-Using-YOLOv5.git
$ cd Uniform-Detection-Using-YOLOv5

$ conda create -n project python=3.9
$ conda activate project

# PyTorch installation process may vary depending on your hardware (1.7.0 <= pytorch <= 1.9.0)
$ conda install pytorch==1.9.0 torchvision==0.10.0 torchaudio==0.9.0 cpuonly -c pytorch
$ pip install -r requirements.txt

# Edit info.yaml to connect with your DB
$ vim info.yaml
```
You can set info.yamlas follow:

```yaml
account:
  mysql:
    host: put your DB host
    user: put your id
    password: put your PW
    db: put your DB name
    charset: utf8mb4
```

### Run
```bash
# Run with python
$ python wsgi.py 

# Run with gunicorn
$ gunicorn --bind 0.0.0.0:5000 wsgi:app
```
