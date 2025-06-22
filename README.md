## 데이터셋 분석 및 깃허브 작성 예시

**Hard Hat Workers 데이터셋 분석**

이 데이터셋은 작업 현장에서 안전모(헬멧) 착용 여부를 감지하기 위한 객체 탐지(Object Detection) 용도로 제작된 공개 데이터셋입니다. Northeastern University - China에서 제공하며, Roboflow 플랫폼을 통해 관리 및 버전 관리가 이루어집니다[1].

---

**1. 데이터셋 개요**

- 총 이미지 수: 7,041장[2]
- 클래스: head, helmet, person (총 3개)[3]
- 어노테이션 포맷: YOLOv11
- 라이선스: Public Domain(공개 도메인)[1][3]
- 원본 데이터셋은 75/25 비율로 train/test로 분할됨[1]

---

**2. 전처리 및 증강**

- 모든 이미지는 416x416 크기로 리사이즈되었으며, 엣지 반사(reflect edges) 기법이 적용됨[2].
- EXIF 정보 제거 및 픽셀 자동 방향 조정이 이루어짐[2].
- v1 버전에는 이미지 증강이 적용되지 않음(원본 데이터 기준)[2][1].
- 다양한 버전(v2~v14)에서 클래스 제거, 증강(최대 3배), 분할 비율 변경 등 다양한 실험이 이루어짐[1].

---

**3. 데이터셋 구조**

- `train`, `val`, `test` 디렉토리로 구분되어 있으며, 각각의 이미지와 라벨 파일이 존재함[3].
- 클래스명 및 개수는 data.yaml 파일에 정의되어 있음[3].

```yaml
nc: 3
names: ['head', 'helmet', 'person']
```

---

**4. 활용 예시 및 사용법**

- 안전모 착용 여부 자동 감지 모델 학습
- 작업장 안전 관리 시스템 구축
- 컴퓨터 비전 실습 및 연구용 벤치마크 데이터로 활용 가능[1]

Roboflow 플랫폼을 활용하면, 데이터셋을 쉽게 Fork/다운로드하여 전처리, 증강, 클래스 수정 등 다양한 실험이 가능하며, Roboflow Notebooks를 통해 학습 및 배포까지 지원함[2][1].

---

**5. 참고 링크**

- [Roboflow 데이터셋 페이지](https://universe.roboflow.com/joseph-nelson/hard-hat-workers)
- [원본 데이터셋 출처](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/7CBGOS)

---


> 본 프로젝트는 Hard Hat Workers 데이터셋을 이용해 작업장 내 안전모 착용 여부를 객체 탐지 방식으로 분류하는 모델 개발을 목표로 합니다. 데이터셋은 총 7,041장의 이미지와 3개 클래스(head, helmet, person)로 구성되어 있으며, Roboflow 플랫폼에서 관리 및 다양한 버전으로 제공됩니다. 본 저장소에서는 v1(416x416 리사이즈, 증강 미적용) 버전을 사용하였으며, train/val/test로 분할하여 실험을 진행했습니다. 데이터셋 및 실험 환경에 대한 자세한 내용은 data.yaml 및 README를 참고해 주세요.

