# Ubunt 환경 조성

<br>

## VMware + Ubuntu 설치 및 설정

<br>

 > **Ubuntu**는 오픈소스 Linux 배포판들중 하나로 이를 Windows가 설치되어있는 기기에서 사용하게 위해 가상머신 **VMware**를 사용한다.

<br>

<details>
    <summary>설치 과정</summary>
 
 1. VMware Windows 버전 설치 [https://www.vmware.com](https://www.vmware.com/kr/products/workstation-player/workstation-player-evaluation.html) 
 
     <img src="https://user-images.githubusercontent.com/101278786/159773710-0d56ee4d-c2af-4c80-aef1-d33c4e7de230.png" width="500">

<br>

 2. Ubuntu LTS 버전(20.04.4) 다운로드 [https://ubuntu.com](https://ubuntu.com/download/desktop)


      <img src="https://user-images.githubusercontent.com/101278786/159782630-bc4ac4ab-1756-421b-b56d-b84ff8073191.png" width="500">
              
<br>

 3. VMware에서 가상머신 생성

    - Create a New Virtual Machine
    
         <img src="https://user-images.githubusercontent.com/101278786/159786353-ef92d23b-a830-424a-8d1a-1f35bc849e05.png" width="500">

    - Install from: I will install the operating system later.
    
         <img src="https://user-images.githubusercontent.com/101278786/159786303-441f5f56-a8fb-4f32-a82d-cc9f8b25b801.png" width="500">

    - Guest operating system - Linux, Version - Ubuntu
    
         <img src="https://user-images.githubusercontent.com/101278786/159786381-781cc5c9-1be0-4c77-bbbf-75b350cd82a5.png" width="500">
         
<br>

  4. 가상머신에 Ubnutu 설치

      - Edit Virtual Machine Settings

          <img src="https://user-images.githubusercontent.com/101278786/159787215-35e5f6ba-8ab6-4c83-bb26-ed8bc40dd8b6.png" width="500">
          
          
          

      - Device - CD/DVD (SATA), Connection - Use ISO image file: (2에서 다운로드한 Ubunto 파일)

          <img src="https://user-images.githubusercontent.com/101278786/159787945-31dd7312-03bf-46bb-9ef4-5355b2fed70a.png" width="500">
          
      - Play virtual machine
      
      - 언어 설정 및 체험하기 선택
      
          <img src="https://user-images.githubusercontent.com/101278786/159788510-c10a72a1-df74-4f15-9fda-9adb10129c88.png" width="500">
          
      - Ubuntu 20.04.4 LTS 설치 클릭
      
          <img src="https://user-images.githubusercontent.com/101278786/160814154-1dc859c4-f0cf-4031-88dc-dc6370c56558.png" width="500">
        
      - 한국어 - 키보드 레이아웃 - Korean(101/104 keyCompltible)
          
          <img src="https://user-images.githubusercontent.com/101278786/160812762-c32fa8ba-f60d-419c-8b4c-7517107030ea.png" width="500">

      - 일반 설치, Ubuntu 설치 중 업데이트 다운로드 선택
      
          <img src="https://user-images.githubusercontent.com/101278786/160815473-9b85c760-8176-4a3e-9aea-12dace5a8ea9.png" width="500">

      - 지금 다시 시작
      
          <img src="https://user-images.githubusercontent.com/101278786/160830474-31438b45-a72e-4ace-9546-7e6f416f0642.png" width="500">

<br>
 
</details>

<br>

### Docker 설치

<br>

   > **Docker**는 Linux 컨테이너를 기반으로한 오픈소스 가상화 플랫폼으로 시스템 리소스를 효율적으로 사용할 수 있게 해주며, 뛰어난 이식성을 가진다.  [참고](https://khj93.tistory.com/entry/Docker-Docker-%EA%B0%9C%EB%85%90)

<details>
    <summary>설치 과정</summary>
 
   1. 기존 설치 삭제 
   
            sudo apt-get remove docker docker-engine docker.io containerd runc

   2. repository 설정

      - 패키지 인덱스 업데이트 및 패키지 설치

            sudo apt-get update
            
            sudo apt-get install \
               ca-certificates \
               curl \
               gnupg \
               lsb-release
            
           <img src="https://user-images.githubusercontent.com/101278786/160861769-8a6b339b-d844-4d3a-8070-570afdd1e005.png" width="500">
            
       - GPG키 추가
       
             curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
             
       - stable repository 설정

             echo \
             "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
             $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
             
             
   3. Docker 엔진 설치
 
            sudo apt-get update
            sudo apt-get install docker-ce docker-ce-cli containerd.io
            
   4. Docker 엔진 테스트

            sudo docker run hello-world
            
      <img src="https://user-images.githubusercontent.com/101278786/160872872-4332b12e-5062-44ac-8c61-5df531021f11.png" width="500">

<br>
 
</details>

<br>

### Nginx 설치

<br>

   > 

<br>

<details>
    <summary>설치 과정</summary>
 
   1. 서버 패키지 목록 업데이트

          sudo apt update
 
   2. Nginx 설치
 
          sudo apt install nginx
 
      <img src="https://user-images.githubusercontent.com/101278786/160941054-53f836b5-3a46-449a-a38e-57879c380920.png" width="500">

   3. 설치 후 테스트
  
      - Nginx 테스트
 
             sudo systemctl status nginx
 
      <img src="https://user-images.githubusercontent.com/101278786/160942307-ca5f4fb0-dea9-4148-a96a-242dc0aa9169.png" width="500">

 
      - Nginx 버전 확인
 
             sudo dpkg -l nginx
 
      <img src="https://user-images.githubusercontent.com/101278786/160942153-49f335e7-8bf3-493f-811e-e8f56432e277.png" width="500">

<br>
 
</details>

<br>

### MySOL 설치 - 현재 

<br>

>

<br>

<details>
    <summary>설치 과정</summary>
 
   1. MySOL 설치

          sudo apt install -y mysql-server
          
   <img src="https://user-images.githubusercontent.com/101278786/160945260-9e9239dd-5207-4e7a-988f-8ce91ca77e32.png" width="500">
   
   2. MySOL 서버 초기화
 
           sudo mysql_secure_installation
 
   <img src="https://user-images.githubusercontent.com/101278786/160945979-86ba8ece-a2f8-43f1-b87c-715cb6f1f7de.png" width="500">


   3. 유저 설정
      
      - New passward - 설정할 비밀번호를 2번 입력하여 설정
 
      <img src="https://user-images.githubusercontent.com/101278786/160946381-0bf4ab95-25f3-419c-aead-ac54c65c7233.png" width="500"><br>
 
      > Remove anonymous users? - 익명 유저를 차단할 것인지 설정 - Y
      >
      > Disallow root login remotely? 외부 접속을 차단할 것인지 설정 - Y
      >
      > Remove test database and access to it? 테스트 데이터베이스를 삭제할 것인지 설정 - Y
 
      <img src="https://user-images.githubusercontent.com/101278786/160946872-1bf67d32-052f-4acb-a314-15e0b478c9fd.png" width="500"><br>
 
      - privileges table를 다시 시작할 것인지 설정 - Y
 
      <img src="https://user-images.githubusercontent.com/101278786/160947049-24b8eea6-a0cc-4e43-92ea-d434a06de6b8.png" width="500">
 
<br>

</details>

<br>

### Visual Studio Code 설치
 
<br>

<details>
    <summary>설치 과정</summary>
 
   1. curl 설치
 
           $ sudo apt-get install curl
 ![image](https://user-images.githubusercontent.com/101278786/163190216-f04dac04-3a82-4fb3-b209-86f5aaffac0c.png)

   2. 마이크로소프트 GPG키 복사
 
           $ sudo sh -c 'curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > /etc/apt/trusted.gpg.d/microsoft.gpg'
 
 ![image](https://user-images.githubusercontent.com/101278786/163191456-a8af6283-e5ee-43b8-94de-7f62d80436ac.png)

 
   3. 프로그램 다운을 위한 저장소 추가 후 패키지 목록 가져오기
  
           $ sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'
           
           $ sudo apt update
           
 ![image](https://user-images.githubusercontent.com/101278786/163192039-8cc2a6d1-ced7-4c3d-9cb7-66d948ead828.png)

   4. Visual Studio Code를 설치
      
           $ sudo apt install code
 
 ![image](https://user-images.githubusercontent.com/101278786/163194220-82c7b7fb-8a53-444c-8751-4069b1abe61c.png)

   5. 설치완료
 
 ![image](https://user-images.githubusercontent.com/101278786/163194535-ec021dd4-763f-4456-8b2f-41d7b661eae6.png)

   6. 윈도우에서 사용하던 확장기능 다운로드
 
      - Korean Language Pack for Visual Studio Code
 
      - HTML CSS Support
 
      - Live Server
 

</details>

<br> 

### MariaDB 및 PHP-FPM 설치

<br>

<details>
    <summary>설치 과정</summary>

   1. MariaDB 저장소 추가
 
           sudo add-apt-repository 'deb [arch=amd64,arm64,ppc64el] http://sgp1.mirrors.digitalocean.com/mariadb/repo/10.4/ubuntu bionic main'
 
 ![image](https://user-images.githubusercontent.com/101278786/163273723-b42a9d1c-2328-4084-923c-eccf5f93ca93.png)

 
   2. MariaDB 저장소 인증키 추가
 
           sudo apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xF1656F24C74CD1D8
 
 ![image](https://user-images.githubusercontent.com/101278786/163273852-d36dd148-7a95-43c4-b79f-ebd1fa262d38.png)
 
   3. PHP 저장소 및 저장소 인증키 추가
 
           sudo add-apt-repository ppa:ondrej/php
 
 ![image](https://user-images.githubusercontent.com/101278786/163274327-6057b87c-c809-4a7b-812e-08bc2aaed99c.png)

   4. apt 갱신
 
           sudo apt update
 
   5. PHP7-FPM 설치
 
           sudo apt install php7.3-fpm
           //버전확인
           php -v
           php-fpm7.3 -v
 
 ![image](https://user-images.githubusercontent.com/101278786/163280793-68120616-e75c-4e82-ada3-4be3419bda14.png)
 
   6. PHP모듈 설치
 
           //다국어 처리모듈
           sudo apt install php7.3-mbstring
           //이미지 처리모듈
           sudo apt install php7.3-gd
           //원격지 정보 모듈
           sudo apt install php7.3-curl php7.3-xml
           //수학 연산 확장 모듈
           sudo apt install php7.3-bcmath
           //MySQL 연동 모듈
           sudo apt install php7.3-mysql
           //국제화 코드 모듈
           sudo apt install php7.3-intl
           //Composer
           sudo apt install composer
 
   7. MariaDB 설치
   
           //MariaDB 콘솔 프로그램 설치
           sudo apt install mariadb-client
           //오류발생시 전부 삭제하고 libmariadbd-dev 패치지 설치 후 재시도
           sudo apt-get install libmariadbd-dev
           //MariaDB 서버 설치
           sudo apt install mariadb-server

<br>


 
 
 
<br><br><br><br><br><br><br><br><br><br>




#### 참고자료
> Ubuntu 설치 

   - [[가상머신]VMware에 Ubuntu 20.04 LTS 설치하기](https://tomcabin.tistory.com/3)

> Docker 설치

   - [docker ](https://docs.docker.com/engine/install/ubuntu/)
   - [Ubuntu 20.04 LTS ) Docker 설치하기](https://shanepark.tistory.com/237)

> Nginx 설치

   - [Ubuntu 20.04에 Nginx 웹 서버를 설치하는 방법](https://ko.linux-console.net/?p=721)

> MySOL 설치

   - [우분투 MySQL 설치](https://hiseon.me/linux/ubuntu/ubuntu-mysql-install/)

> Visual Studio Code 설치

   - https://webnautes.tistory.com/1197

