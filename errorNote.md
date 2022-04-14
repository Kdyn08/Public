## 미해결

<details>
    <summary>자세히</summary>





</details>

<br>

## 미확인

<details>
    <summary>자세히</summary>
  
### [Ubunt.md](https://github.com/Kdyn08/Public/blob/main/Ubuntu.md)
  
  - 설치중 명령어를 입력했는데 반응이 없었다. 적용이 된 것일까?

         echo \
        "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
        $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
        
</details>

<br>
        
## 해결

<details>
    <summary>자세히</summary>
    
    - Visual Studio Code 설치중 설치 코드를 입력했는데 apt 패키지를 찾을 수 없다고 한다.

               $ sudo apt install code

![image](https://user-images.githubusercontent.com/101278786/163192547-b7d07bbc-9b1d-4095-8433-52f3e8ffd7b8.png)

    > 중간 코드가 누락되었었다.
    
              sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'
    
    - Nginx 테스트중 404 에러가 나와서 재설치했다.
    
    ![image](https://user-images.githubusercontent.com/101278786/163277039-139b168c-bf7e-42ea-b684-af1e580f2094.png)
    
    > 재설치 반복으로 해결
    
    - MariaDB 설치중 망가진 고정 패키지 오류 발생
    
    ![image](https://user-images.githubusercontent.com/101278786/163272561-f9fb9819-aa57-4dc7-980c-efa1d312491d.png)
    
    > MySQL 삭제로 해결 한줄 알았으나 해결 실패
    
                sudo apt-get remove mariadb-server mariadb-client mysql-server mysql-client
    
    >  libmariadbd-dev 패키지 설치후 재설치로 해결 실패 http://egloos.zum.com/mcchae/v/11141964
       
                sudo apt-get install libmariadbd-dev

</details>


<br>
