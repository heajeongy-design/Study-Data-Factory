# Data Factory sample에서 BLOB > SQL Database로 이동하기

## 1. data factory 생성  

<img width="1670" height="196" alt="image" src="https://github.com/user-attachments/assets/2c5daa59-a610-4c45-b4f4-e8f4ad4b0b9c" />


## 2. SQL database 만들기  

<img width="673" height="656" alt="image" src="https://github.com/user-attachments/assets/580fea12-470a-4ca8-b3ed-1095efda0ccb" />



<img width="1575" height="243" alt="image" src="https://github.com/user-attachments/assets/113d718b-699e-423f-a8cb-c39335ff2bd5" />


## 3. Storage account 생성  

<img width="797" height="285" alt="image" src="https://github.com/user-attachments/assets/cc320ed6-75b2-49b4-a4e5-81c67b6772ba" />


## 리소스 모음에 만든거 확인가능

<img width="1699" height="579" alt="image" src="https://github.com/user-attachments/assets/ea292923-5e34-4c72-8d94-64e58a633097" />


## 4. Blob에 Input 생성 & csv 파일 저장  

<img width="1914" height="373" alt="image" src="https://github.com/user-attachments/assets/8bd2d0fb-1f2b-43bb-ae62-ac4421617fd3" />

- input 컨테이너 생성
  
<img width="229" height="224" alt="image" src="https://github.com/user-attachments/assets/773022e1-fb15-4f3c-8973-774245ac5054" />

- 파일 업로드

<img width="538" height="394" alt="image" src="https://github.com/user-attachments/assets/e8b7e947-1dfc-4eca-b76b-c2d6fd15ef7a" />


<img width="1306" height="319" alt="image" src="https://github.com/user-attachments/assets/16456e3a-5a7e-4716-a186-1f05ba66f3e9" />


- 내부 '편집' 통해서 확인가능

<img width="389" height="761" alt="image" src="https://github.com/user-attachments/assets/3f2fee8a-bb0d-4831-83de-d40af046d037" />


## 5. SQL Database – 쿼리편집기 – 로그인 – 테이블 생성 – 테이블 들어온거 확인  


<img width="1780" height="538" alt="image" src="https://github.com/user-attachments/assets/2529365b-ff03-4126-891b-acb100f47da4" />


<img width="897" height="464" alt="image" src="https://github.com/user-attachments/assets/e22a45ac-0a48-49df-9faa-9159e28dd3cc" />


## 6. Data factory studio 시작  


<img width="1171" height="586" alt="image" src="https://github.com/user-attachments/assets/cf0c88da-a4ca-42c0-8950-6592ddd5b58c" />


- 파이프라인 생성, 템플릿에서 파이프라인 생성, 데이터 복사 등 이용가능
<img width="1682" height="548" alt="image" src="https://github.com/user-attachments/assets/65675e76-53aa-4f3f-bc3d-d02746e5743a" />


## 7. pipeline 생성 > Integration runtime  
   7-1. Csv 파일 연결하려면 link service 생성필요  

<img width="1863" height="650" alt="image" src="https://github.com/user-attachments/assets/77c7717a-33fb-4a23-b597-3601632bfe24" />

- 연결키(link service) 생성하기
  
<img width="755" height="801" alt="image" src="https://github.com/user-attachments/assets/8b7da93f-d0ae-4d4d-960b-3f7c2063341c" />

  
   7-2. 데이터 세트 연결 - Blob
- 데이터 세트 연결 이유 : 스토리지에서 데이터를 가져올 때 데이터의 형식을 알아야해서


<img width="602" height="376" alt="image" src="https://github.com/user-attachments/assets/2a55ea18-5556-46a8-8c78-2a127e8e8887" />


<img width="755" height="391" alt="image" src="https://github.com/user-attachments/assets/29784310-e3d1-44e6-84c8-cda23b4ce81e" />


- 데이터 세트 연결완료
<img width="1458" height="763" alt="image" src="https://github.com/user-attachments/assets/4ec5b4c2-f4b8-4d0e-928d-6f001bcc1be7" />

   
   7-3. SQL에 연결
 
<img width="1899" height="815" alt="image" src="https://github.com/user-attachments/assets/c0c35c14-dcf9-4f1d-a545-56a2a49c958c" />


- 연결테스트 후 만들기
<img width="506" height="834" alt="image" src="https://github.com/user-attachments/assets/94178e4a-455a-4216-9b10-ef77330a7347" />

- 완료
<img width="1079" height="70" alt="image" src="https://github.com/user-attachments/assets/6fb979e9-bbf9-4a0b-83ff-8df3f29632a3" />


   7-4. 데이터 세트 연결 - sql server  


<img width="1907" height="324" alt="image" src="https://github.com/user-attachments/assets/4451b90b-2d0f-4152-84ca-fdb80be56f7a" />


## 2개 데이터 세트, 2개 연결 서비스 생성
   
## 8. 복사작업  
   -원본 (source) : 어디서 읽을지  
   -싱크 (sink) : 어디에 쓸지 (최종 목적지가 SQL database table이니까)  


<img width="925" height="442" alt="image" src="https://github.com/user-attachments/assets/11689b29-0d66-46e1-82d1-b168ea8e7aa1" />

- 디버그 (실행 완료)

<img width="1749" height="617" alt="image" src="https://github.com/user-attachments/assets/2e2446d0-3b94-42b0-b242-98e28d870e5f" />


## 9. 조회
- sql server에서 조회완료  = 제대로 작동하는지 확인 후 게시 진행
  
<img width="1515" height="601" alt="image" src="https://github.com/user-attachments/assets/374492d7-ba11-4b0f-a68d-268aaa039223" />


<img width="1592" height="821" alt="image" src="https://github.com/user-attachments/assets/cc9f894d-39f6-44ff-86ba-ca76b02e44a8" />


- 트리거 이용해서 이벤트 발생 시 파이프라 예약하거나 추출 가능
  
<img width="398" height="314" alt="image" src="https://github.com/user-attachments/assets/b4ff2eee-c774-44c4-86a8-593f66d195f0" />


- 모니터링 가능

<img width="1922" height="314" alt="image" src="https://github.com/user-attachments/assets/2599b9ac-8d9d-49bc-b53e-f52fbfe3462d" />


## 예외> 데이터 더블링 되었을때 

<img width="718" height="550" alt="image" src="https://github.com/user-attachments/assets/580b5bf9-97f5-4538-851d-a36426f93a98" />

- delete 작성해주기
  
<img width="690" height="337" alt="image" src="https://github.com/user-attachments/assets/97770616-4673-469c-aec8-75059aef76df" />
