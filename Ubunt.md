# Ubunt 환경 조성

<br>

## VMware + Ubuntu 설치 및 설정

<br>

 > Ubuntu는 오픈소스 Linux 배포판들중 하나로 이를 Windows가 설치되어있는 기기에서 사용하게 위해 가상머신 VMware를 사용한다.

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

## repository를 이용하여 Docker 설치

<br>

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

<br><br><br><br><br><br><br><br><br><br><br>
      



#### 참고자료
> Ubuntu 설치 

   - [[가상머신]VMware에 Ubuntu 20.04 LTS 설치하기](https://tomcabin.tistory.com/3)

> Ubuntu에 Docker 설치

   - [docker ](https://docs.docker.com/engine/install/ubuntu/)
   - [Ubuntu 20.04 LTS ) Docker 설치하기](https://shanepark.tistory.com/237)
