# Data Factory(ADF)

## 개념
: 데이터 파이프라인(이동+변환+스케줄링) 만드는 서비스  
: 데이터 ETL/ELT 오케스트레이션 툴  

## 하는일
1) 데이터 이동 (Ingestion / copy)  
: SAP/ SQL Server / S3 / 파일 / API / ADLS 같은 곳에서 > ADLS(데이터레이크)나 Synapse, SQL DB로 복사 (COPY activity)

2) 데이터 처리/변환(transform)  
: 날짜 포맷 바꾸기, 조인, 필터, 집계, 컬럼 정리, 정제 등  
: data flow(GUI로 만드는 변화) 또는 Databricks/Synapse, Spark/SQL 같은 외부 엔진 호출  

3.) 오케스트레이션 : 파이프라인으로 순서/조건/재시도/알림을 묶어서 운영  

---

# Data Flow

## 개념
: ADF 안의 기능 중 하나  
: ADF(서비스) 안에 pipeline(흐름/오케스트레이션)이 있고, 그 안에 copy / data flow / 외부작업 호출 등을 조합하는 구조  
: Data Flow = 코드 없이(또는 최소) GUI로 데이터 변환하는 기능  
: 캔버스에서 소스>변환(join/filter/aggregate)>싱크 를 끌어다 놓는 방식  
: 내부적으로는 spark기반으로 실행돼서, 변환이 복잡하거나 데이터가 크면 spark리소스를 사용  

---

# Synapse와 다른점

Synapse Analytics : 데이터웨어하우스 + 빅데이터(spark) + SQL + 분석을 한 작업공간에 묶은 분석 플랫폼  

ADF = 파이프라인이 주인공  
Synapse = 분석 플랫폼이 주인공, 파이프라인은 부속  

두개는 매우 유사한 엔진/화면을 쓰고, 기능이 많이 겹침  
차이점 존재  

## 1) 어디에 붙어 있냐
Synapse 파이프라인 : Synapse workspace 안에서 SQL/Spark/데이터레이크/노트북/데이터웨어하우스 작업과 한곳에서 묶여 운영  
ADF 파이프라인 : 분석 플랫폼과 분리된 독립 통합 허브로 여러 시스템을 폭넓게 연결/운영  

## 2) 뭘 중심으로 운영하냐
Synapse : DW 쿼리/스파크 작업/데이터 모텔이 중심, 파이프라인은 딸려감  
ADF 중심 : 다양한 소스>타겟으로 데이터 통합 중심  

---

# 사용 관점

## 1)Synapse를 쓰면 좋은 경우
:SQL스크립트 실행/노트북 실행/DW적재 위주  
:분석가/엔지니어가 한 Workspace에서 개발~운영까지 하고싶다  
:적재 후 모델링/성능 튜닝/서빙 등 시행 필요  

## 2)ADF를 쓰면 좋은 경우
:스케줄/재시도/운영/모니터링까지 통합  
:조직 전체 데이터 수집 연결/수집/이동의 표준화 운영을 위한 허브 역할  
: (어딘가)소스/타겟이 여러 시스템으로 넓게 퍼져있다(SaaS, 온프렘, 여러 DB 등)  
: 데이터를 가져와서 다른 곳(타겟)으로 옮기는 것 (데이터 자체를 저장하는 거 NO)  

---

# 기타 메모

키와 주소 = > 링크 서비스  
-연결에 대한 정의, blob 스토리지와 키와 같은 인증 외 데이터 세트 객체 생성  

Dataset = 고객 csv파일에 대한 정의, blob스토리지에서 어떤 종류의 데이터를 가져올지에 대한 정의  

Copy activity : 데이터 복사  

데이터 이동 (SQL Server)  
SQL 서버의 위치를 알 수 있도록 링크 서비스 필요  
(고객 테이블의 구조를 알려주는 또 다른 데이터 세트)


<img width="1223" height="628" alt="image" src="https://github.com/user-attachments/assets/cee959c1-2328-4b3b-a6f8-cb946804f8fb" />

<img width="1261" height="547" alt="image" src="https://github.com/user-attachments/assets/e41ff196-f529-436b-b94d-ef127af3ea01" />

<img width="899" height="419" alt="image" src="https://github.com/user-attachments/assets/9de249b4-3773-427f-8593-925253a9c0bb" />




