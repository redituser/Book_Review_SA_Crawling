# Book_Review_SA_Crawling

이 문서는 `Book_Review_SA` 프로젝트의 핵심 부분인 **도서 리뷰 데이터 크롤링**에 대한 내용을 담고 있습니다. 주요 파일로는 알라딘 도서 리뷰를 수집하는 크롤러와 Streamlit 애플리케이션에서 검색 결과를 가져오는 데 사용되는 `crawling.py` (네이버 도서 리뷰 크롤러)가 있습니다. 각 크롤러의 기능과 설치/실행 방법을 상세히 설명합니다.

---




# 알라딘 도서 리뷰 크롤러 (Aladdin Book Review Crawler)

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![Selenium](https://img.shields.io/badge/Selenium-Web%20Automation-orange.svg)
![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup-HTML%20Parsing-green.svg)
![CSV](https://img.shields.io/badge/Output-CSV-lightgrey.svg)

알라딘 웹사이트에서 도서 리뷰 데이터를 자동으로 수집하는 Python 기반의 웹 크롤러입니다. Selenium과 BeautifulSoup을 활용하여 동적으로 로드되는 콘텐츠를 처리하고, JSON-LD 형식의 메타데이터를 추출하여 책 정보를 풍부하게 수집합니다. 수집된 리뷰는 CSV 파일로 저장됩니다.

---

## 🌟 주요 기능

* **다중 페이지 크롤링**: 설정된 시작 페이지부터 끝 페이지까지 알라딘 도서 목록을 탐색합니다.
* **도서 상세 정보 추출**: 각 도서 페이지에서 제목, 저자, 출판사, 장르, 평점, 리뷰 수 등의 메타데이터를 JSON-LD에서 추출합니다.
* **리뷰 데이터 수집**: "더보기" 버튼을 자동으로 클릭하여 모든 리뷰를 로드하고, 각 리뷰의 내용과 별점을 수집합니다.
* **안정적인 웹 드라이버 관리**: `webdriver_manager`를 사용하여 Chrome 드라이버를 자동으로 설치하고 관리하여 환경 설정의 번거로움을 줄입니다.
* **중간 저장 기능**: 크롤링 과정 중 특정 페이지 단위(10페이지마다)로 데이터를 CSV 파일로 중간 저장하여, 예기치 않은 오류 발생 시 데이터 손실을 최소화합니다.
* **CSV 출력**: 수집된 모든 도서 정보 및 리뷰 데이터를 구조화된 CSV 파일로 저장합니다.




# 네이버 도서 리뷰 크롤러 (Naver Book Review Crawler)

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![Selenium](https://img.shields.io/badge/Selenium-Web%20Automation-orange.svg)
![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup-HTML%20Parsing-green.svg)
![Pandas](https://img.shields.io/badge/Data%20Analysis-Pandas-lightgrey.svg)

네이버 쇼핑의 도서 섹션에서 책 제목과 사용자 리뷰 데이터를 자동으로 수집하는 Python 기반의 웹 크롤러입니다. Selenium과 Beautiful Soup을 활용하여 동적으로 로드되는 콘텐츠를 효과적으로 처리하고 필요한 정보를 추출합니다.

---

## ✨ 주요 기능

* **검색 기반 크롤링**: 사용자가 입력한 검색어에 따라 네이버 쇼핑 도서 검색 결과를 탐색합니다.
* **다중 도서 상세 페이지 방문**: 검색된 각 도서의 상세 페이지로 이동하여 정보를 추출합니다.
* **도서 정보 추출**: 각 도서 페이지에서 제목을 추출합니다. (필요시 저자, 출판사, 평점 등 추가 정보 확장 가능)
* **모든 리뷰 로드 및 수집**: "리뷰" 탭을 클릭하고, "더보기" 버튼을 자동으로 반복 클릭하여 해당 책의 모든 사용자 리뷰를 로드하고 수집합니다.
* **안정적인 웹 드라이버 관리**: `webdriver_manager` 라이브러리를 사용하여 Chrome 드라이버를 자동으로 다운로드 및 관리함으로써, 환경 설정의 번거로움을 줄이고 항상 최신 드라이버를 사용합니다.
* **CSV 출력**: 수집된 책 제목과 모든 리뷰 데이터를 구조화된 CSV 파일로 저장합니다.

---



## 🛠️ 공통 설치 및 실행 방법

### 1. 전제 조건

* **Python 3.x**: 파이썬이 설치되어 있어야 합니다.
    [Python 공식 웹사이트](https://www.python.org/downloads/)에서 다운로드할 수 있습니다.
* **Google Chrome**: 웹 크롤링에 Chrome 브라우저가 사용됩니다.

### 2. 의존성 설치

프로젝트를 실행하기 전에 필요한 라이브러리들을 설치해야 합니다. 터미널 또는 명령 프롬프트에서 다음 명령어를 실행하세요:

```bash
pip install selenium beautifulsoup4 webdriver-manager
```

