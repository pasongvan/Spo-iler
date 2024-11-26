[구글독스](https://docs.google.com/document/d/1SGMtZOGRSk42DyslsK9BDZlZRZfsByDZmD9C12JSYds/edit?usp=sharing)
[피그마](https://www.figma.com/design/73VSLdfkhjtWZpaeU1hbZm/%EC%8A%B9%EB%B6%80%EC%98%88%EC%B8%A1?node-id=0-1&t=4Yoyy4iRh3Dn3wLv-1)
[노션](https://www.notion.so/PJT-B-11b943c01a2e80f6ade6db84130922d3)


# Spo-iler 프로젝트 결과 보고서

---

## 프로젝트 팀 구성
- **조장**: 피승빈  
- **조원**: 박서하  

---

## 목차
1. 프로젝트 개요 및 요구사항  
2. UseCase 다이어그램  
3. 데이터베이스 테이블 구조 (ERD)  
4. 클래스 다이어그램  
5. 사용된 라이브러리 및 프레임워크  
6. 프레임워크 선택 이유  
7. 얼굴 인식 및 감정 분석 모델 구현  
8. 결론 및 기대효과  

---

## 1. 프로젝트 개요 및 요구사항

### 프로젝트 개요
Spo-iler 프로젝트는 AI 기술을 활용해 스포츠 경기의 승률을 분석하고 예측하는 플랫폼입니다. 주요 특징으로는 **얼굴 인식**과 **표정 분석**을 기반으로 한 경기 흐름 예측, 사용자의 활동 로그 관리 기능 등이 포함됩니다.

### 요구사항 정의
#### 사용자 기능
1. **회원가입**: 사용자 정보를 입력받아 계정을 생성합니다.  
2. **로그인/로그아웃**: 인증을 통해 시스템에 접근하거나 종료합니다.  

#### 관리 기능
1. **권한 관리**: 사용자 역할(Role)에 따라 접근 가능한 리소스를 제한합니다.  
2. **관리자 페이지**: 사용자 정보 및 활동 로그를 관리합니다.  

#### 보안 기능
1. **JWT 기반 인증**: 토큰을 통한 안전한 세션 관리를 제공합니다.  
2. **데이터 암호화**: 사용자 비밀번호를 안전하게 저장합니다.  

#### 경기 분석 기능
1. 입력받은 경기 상황 정보 및 관계자의 이미지를 분석합니다.  
2. 경기 관계자의 표정에서 감정을 추출합니다.  
3. 추출된 감정을 기반으로 경기의 흐름을 예측하고 승률을 표시합니다.  
4. 분석 의뢰한 사진들을 사용자의 프로필 페이지에 기록합니다.  

---

## 2. UseCase 다이어그램

### 액터
- **User (사용자)**  

### 주요 기능
1. 회원가입 및 로그인/로그아웃  
2. 사용자 페이지에서 이전 분석 기록 확인  
3. 경기 정보와 이미지를 입력하여 승률 계산  

---

## 3. 데이터베이스 테이블 구조 (ERD)

### 테이블 설계
1. **Role Table**  
   - **컬럼**: `id`(PK), `name`(역할명)  
   - **설명**: 사용자 역할 정보를 관리합니다.  

2. **User Table**  
   - **컬럼**: `id`(PK), `username`, `email`, `password`  
   - **설명**: 사용자 계정 정보를 저장합니다.  

3. **User_Role Table**  
   - **컬럼**: `user_id`(FK), `role_id`(FK)  
   - **설명**: 사용자와 역할 간 다대다 관계를 관리합니다.  

---

## 4. 클래스 다이어그램

### 주요 클래스
1. **User**  
   - 속성: `id`, `username`, `email`, `password`  
   - 메서드: 회원가입, 로그인, 로그아웃  

2. **Role**  
   - 속성: `id`, `name`  
   - 메서드: 권한 부여  

3. **GameAnalysis**  
   - 속성: 경기 정보, 이미지 파일  
   - 메서드: 분석 수행  

---

## 5. 사용된 라이브러리 및 프레임워크

### 프론트엔드
1. **Vue.js**: 사용자 인터페이스 개발  
2. **Vue Router**: 클라이언트 라우팅  
3. **Vuex**: 중앙 상태 관리  
4. **Axios**: 백엔드 API와의 통신  

### 백엔드
1. **Spring Boot**: 백엔드 애플리케이션 개발  
2. **Spring Security**: 인증 및 권한 관리  
3. **Hibernate (JPA)**: 데이터베이스와 객체 간 매핑  
4. **JWT**: 세션리스 인증  

---

## 6. 프레임워크 선택 이유

### 프론트엔드
1. **Vue.js**:  
   - 가벼운 SPA(Single Page Application) 구축 가능.  
   - 코드 재사용성 및 확장성 제공.  

2. **Vue Router**:  
   - 페이지 리로드 없이 빠른 라우팅.  

3. **Vuex**:  
   - 복잡한 데이터 흐름 관리 및 동기화.  

4. **Axios**:  
   - REST API와의 직관적인 통신 제공.  

### 백엔드
1. **Spring Boot**:  
   - 빠르고 간편한 설정 및 강력한 확장성.  

2. **Spring Security**:  
   - 인증 및 권한 부여 표준화.  

3. **Hibernate (JPA)**:  
   - 데이터 모델링 및 NoSQL 데이터베이스 연동에 용이.  

4. **JWT**:  
   - 세션리스 인증으로 서버 부하 감소 및 확장성 향상.  

---

## 7. 얼굴 인식 및 감정 분석 모델 구현

### 사용된 기술 및 모델
1. **Face Detection (얼굴 탐지)**  
   - **기술**: TensorFlow.js, MobileNet 기반 CNN  
   - **모델 파일**:  
     - `tiny_face_model-shard1`  
     - `tiny_face_detector_model-weights_manifest.json`  
   - **특징**:  
     - Depthwise Separable Convolution으로 경량화.  
     - 다양한 조명과 각도에 대응.  

2. **Emotion Recognition (표정 분석)**  
   - **기술**: TensorFlow.js, 자체 학습 모델  
   - **모델 파일**:  
     - `face_expression_model-shard1`  
     - `face_expression_model-weights_manifest.json`  
   - **학습 데이터**:  
     - 한국인 감정 레이블 데이터(AI Hub) 사용 ([링크](https://aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=82))  
   - **분류 레이블**:  
     - Neutral, Sad, Happy, Angry, Surprised, Disgusted, Scared  

---

### 구현 과정
1. **모델 학습 및 변환**  
   - 고성능 GPU 환경에서 학습 후, TensorFlow.js 형식으로 변환.  
   - 요소 가중치(`shard1`)와 JSON 통신 모듈로 분리.  

2. **모델 특징**  
   - WebGL 기반 GPU 가속 활용으로 브라우저에서 실시간 처리.  
   - MobileNet 구조를 사용하여 실시간 얼굴 및 표정 인식 가능.  

3. **실시간 분석 및 데이터 시각화**  
   - 감정 데이터와 경기 정보를 결합하여 승률 예측.  
   - 분석 결과는 그래프와 수치로 시각화하여 사용자에게 제공.  

---

## 8. 결론 및 기대효과

### 결론
Spo-iler 프로젝트는 스포츠 경기 분석 분야에서 AI 기반 기술을 도입한 혁신적 플랫폼으로, 얼굴 및 표정 데이터를 활용해 기존의 단순한 스코어 기반 분석을 넘어선 서비스를 제공합니다.

### 기대효과
1. **사용자 경험 향상**  
   - 직관적이고 실시간으로 작동하는 분석 시스템.  

2. **개발 효율성 증대**  
   - 최신 기술과 프레임워크를 활용하여 빠르고 안정적인 시스템 구축.  

3. **시장 경쟁력 강화**  
   - 기존 플랫폼과 차별화된 기능으로 독점적 시장 포지션 확보 가능.  

---
## 9. 시연영상

https://github.com/user-attachments/assets/86edf8ad-fa0c-4af5-9553-132b5d6e2089





