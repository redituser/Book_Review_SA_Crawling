# 📚 Book_Review_SA: 도서 리뷰 감성 분석을 위한 크롤링 시스템

이 문서는 `Book_Review_SA` 프로젝트의 핵심 기능 중 하나인 **도서 리뷰 크롤링**에 대해 설명합니다.  
알라딘과 네이버에서 도서 리뷰 데이터를 수집하는 크롤러의 역할과 사용 방법을 다루며, 각각의 크롤러는 다음과 같은 목적에 활용됩니다:

- **알라딘 도서 리뷰 크롤러**: 모델 학습을 위한 데이터 수집
- **네이버 도서 리뷰 크롤러**: 실시간 검색 기반 리뷰 수집   

각 크롤러는 Streamlit 애플리케이션과 연동되어 감성 분석에 필요한 데이터를 제공합니다.

---

## 🌀 알라딘 도서 리뷰 크롤러  
> **Aladdin Book Review Crawler**

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![Selenium](https://img.shields.io/badge/Selenium-Web%20Automation-orange.svg)
![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup-HTML%20Parsing-green.svg)
![CSV](https://img.shields.io/badge/Output-CSV-lightgrey.svg)

Selenium과 BeautifulSoup을 활용하여 **알라딘 웹사이트**에서 도서 리뷰 데이터를 자동 수집하는 크롤러입니다.  
JSON-LD 기반의 메타데이터와 리뷰를 수집하여 CSV 파일로 저장합니다.

### 🔧 주요 기능
- ✅ **다중 페이지 크롤링**: 설정된 시작 ~ 끝 페이지 탐색
- ✅ **도서 메타데이터 추출**: 제목, 저자, 출판사, 장르, 평점, 리뷰 수 등
- ✅ **모든 리뷰 수집**: "더보기" 클릭을 통해 리뷰 전체 로드
- ✅ **웹드라이버 자동 관리**: `webdriver_manager` 사용으로 드라이버 설치 자동화
- ✅ **중간 저장 기능**: 10페이지마다 CSV로 자동 저장 → 오류 대비
- ✅ **결과 출력**: 구조화된 CSV 파일로 저장

---

## 🌐 네이버 도서 리뷰 크롤러  
> **Naver Book Review Crawler**

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![Selenium](https://img.shields.io/badge/Selenium-Web%20Automation-orange.svg)
![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup-HTML%20Parsing-green.svg)
![Pandas](https://img.shields.io/badge/Data%20Analysis-Pandas-lightgrey.svg)

Selenium과 BeautifulSoup을 활용하여 **네이버 쇼핑 도서 섹션**에서 사용자 리뷰를 자동 수집하는 크롤러입니다.  
Streamlit UI와 연동되어 사용자의 검색어 기반 리뷰 수집을 지원합니다.

### ✨ 주요 기능
- 🔍 **검색 기반 크롤링**: 입력된 키워드로 도서 검색
- 📖 **도서 상세 페이지 방문**: 검색 결과 목록 순회
- 📝 **도서 정보 추출**: 제목 중심 (향후 확장 가능)
- 💬 **모든 리뷰 수집**: "리뷰" 탭 → "더보기" 반복 클릭
- ⚙️ **웹드라이버 자동 관리**: 최신 Chrome 드라이버 자동 설치
- 📁 **결과 저장**: 책 제목 + 리뷰 내용을 CSV로 저장

---

## 🛠️ 공통 설치 및 실행 방법

### ✅ 전제 조건
- Python 3.x 설치  
  → [Python 공식 다운로드](https://www.python.org/downloads/)
- Google Chrome 설치  

### 📦 필수 라이브러리 설치

아래 명령어로 필요한 라이브러리를 설치하세요:

```bash
pip install selenium beautifulsoup4 webdriver-manager
