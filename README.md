# Medi-Bot

**개발기간**  
2024.01.08 ~ 2024.01.22

**플랫폼**  
카카오톡(카카오 챗봇)

**개발 인원**  
4명 중 팀원

**담당 역할**: 
알약 데이터 라벨링 약 400장
Yolo모델 커스텀 학습
객체 탐지 및 OCR 파이프 라인 구축

**사용 기술**
객체 인식 - YOLOv8
OpenCV - graySacle, Contrast, Threshold 파라미터 조정으로 인식률 향상
OCR - EasyOCR

**개발환경**

- **언어**: Python(3.8.0)
- **서버**: 구름IDE
- **프레임워크**: Flask
- **기타환경**: Google Colab(모델 학습)
- **API, 라이브러리**: YOLOv8n, EasyOCR, OpenCV, pandas, folium

## 기능 설명

### 1. 약 검색 기능
- **기술**: Regular Expression, 약 정보 API
- **설명**: 두 개의 약 정보 API에서 받아온 데이터 내에서 정규 표현식(regex)을 사용하여 약 이름 또는 각인으로 검색 후 조회되는 약 성분 및 제조사 정보를 제공

### 2. 약 객체 인식 및 정보 제공 기능
- **기술**: Object Detection, OCR, 약 정보 API
- **설명**: 사용자가 제공한 이미지를 바탕으로 약 정보 API에서 제공되는 약 이미지 파일을 라벨링하여 학습시킨 모델(Object Detection)을 이용. 객체 인식(OCR) 후 텍스트를 추출하여 1번 기능을 통해 약 정보를 사용자에게 제공

### 3. 약국 정보 제공 기능
- **기술**: Google Maps API, Folium, HTML
- **설명**: Google Maps API와 Folium 라이브러리를 사용하여 사용자의 위치와 약국 데이터를 지도에 표시하고, 약국의 현재 운영 여부, 이용자와의 거리 등의 정보를 포함하여 HTML URL 형식으로 제공

### 4. 서버 및 챗봇 연동
- **기술**: Python Flask, Kakao 챗봇, 구름IDE
- **설명**: Python Flask를 이용하여 서버를 구축하고 Kakao 챗봇 서비스와 연동하여 사용자 데이터를 기반으로 1, 2, 3번 기능을 처리하여 카카오 챗봇 화면에 버튼 형식으로 URL 링크 제공. 구름 IDE를 사용하여 서버를 구동하였으며, 이미지 검색을 위한 학습 모델이 무료 서버에서 구동하는 데 어려움이 있어 2개의 서버 및 2개의 Flask 인스턴스를 사용하여 main_server, imageseach_server, kakao챗봇 서버를 연결

### 5. Kakao 챗봇 시나리오 구성 및 기본 프론트
- **기술**: Kakao 챗봇 Developers
- **설명**: Kakao 챗봇 시나리오를 구성하고 기본적인 프론트 구현
