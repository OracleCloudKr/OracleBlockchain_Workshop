# 오라클 블록체인 인스턴스 생성하기
이 단계에서는 3개의 인스턴스를 생성할 예정입니다. Founder 인스턴스 1개와 Participant 인스턴스 2개를 생성하게 됩니다. 인스턴스의 Role은 Founder와 Participant 두가지로 선택이 가능합니다. Founder는 블록체인 네트워크의 중심이 되는 인스턴스로 다른 여러 Participant 인스턴스를 관리할 수 있게 됩니다.

강사로 부터 개별로 전달 받은 IP는 Oracle Blockchain Platform EE(Enterprise Edition) 버전이 설치되어 있는 IP 입니다. EE 버전은 On-Premise에 설치해서 사용할 수 있는 버전으로 Cloud 버전과 거의 유사한 화면을 갖고 있습니다. 이 Lab에서는 EE버전을 사용할 예정입니다.

1. OBP(Oracle BlockChain Platform) Console 에 접속하기
   본인에게 할당된 3개의 IP 주소 중 첫번째 IP를 사용해서 아래와 같이 접속하면 Blockchain Platform 콘솔 화면에 접속할 수 있습니다.

   http://**할당 받은 IP Address**:7070/console/

2. Organization(조직) 생성하기 Provisioning
처음 접속을 한 경우에는 아래와 같이 나오게 됩니다.  
오른쪽에 있는 인스턴스 생성 버튼을 누릅니다.
![](images/obp_login.png)

3. Lab을 위해 미리 생성해 놓은 계정(obpuser1 / welcome1)으로 로그인을 합니다. 
4. 로그인을 하면 아래와 같은 블록체인의 모든 인스턴스들을 관리하는 메인화면으로 이동하게 됩니다. Create Instance 를 클릭합니다.
![](images/obp_console_main.png)

5. 이제 블록체인 네트워크의 메인이 되는 인스턴스를 만들도록 하겠습니다. 인스턴스 이름을 DetroitAuto로 입력합니다. Founder로 선택해서 인스턴스를 만들겠습니다.
![](images/obp_create_instance1.png)

6. Cluster Configuration 탭에서는 Platform Host를 입력하고 Submit 버튼을 누릅니다. Platform Host는 강사로부터 받은 도메인 이름을 입력합니다. 
   > 인스턴스 생성은 1개의 Host 에 1개의 인스턴스를 생성할 수 있으며 Domain 이름으로만 생성이 가능합니다. On-Premise로 구성시에도 내부에 DNS 서버(Private DNS)에 등록이 되어 있어야 생성이 가능합니다.

![](images/obp_create_instance2.png)

7. 정상적으로 요청이 전달이 되면 인스턴스 생성이 시작됩니다. 인스턴스 생성까지는 수분 정도 소요가 되게 됩니다.
![](images/obp_create_instance3.png)

8. 인스턴스가 생성이 되면 Up 으로 표시가 됩니다. 오른쪽에 햄버거 버튼을 클릭하면 해당 인스턴스의 콘솔로 이동할 수 있는 Service Console 이 표시됩니다.
![](images/obp_create_instance4.png)

9. 인스턴스의 Service Console로 이동하기 전에 도메인주소에 대한 IP주소를 세팅하는 과정이 필요합니다. 이 도메인 주소는 Private DNS에 등록되어 있는 주소이므로 직접 접근할 수 없습니다. 이 IP와 DNS 주소를 hosts파일에 등록해 줍니다. 할당 받은 **3개**의 IP와 DNS 주소를 모두 입력합니다.
   * 윈도우는 관리자 권한으로 메모장을 열어야 하고 Linux나 Mac은 sudo(root) 권한으로 파일을 열어야 합니다.

    > Windows : [Windows]/system32/drivers/etc/hosts
    > 
    > Linux or Mac : /etc/hosts

    > **[할당 받은 IP Address]** [할당 받은 DNS]<br>
    > 예:) 132.145.91.168 inst1.sub.obpvcn.oraclevcn.com
   
10. 이제 브라우저에서 DNS 이름으로 새롭게 생성된 detroitauto Founder의 Console 화면으로 이동합니다. obpuser1/welcome1 으로 로그인을 합니다.
![](images/obp_instance_console.png)

11. 새롭게 생성된 블록체인 Founder 인스턴스의 콘솔 메인 화면을 볼 수 있게 됩니다.
![](images/obp_instance_console2.png)

12. 지금까지는 Founder 인스턴스를 생성했습니다. 이와 같은 네트워크를 구성할 Participant 인스턴스를 만들어 보도록 하겠습니다. 다시 메인 콘솔로 돌아가서 Create Instance를 클릭해서 생성화면으로 이동합니다. 인스턴스 이름을 **Jude Dealer**를 생성하도록 하겠습니다. 여기서는 새로운 네트워크를 생성하는 Founder가 아니기 때문에 **Participant** 를 선택합니다. 입력 후에 Cluster Configuration 를 선택합니다.
![](images/obp_create_participant1.png)

13. Cluster Configuration에서는 Platform Host를 할당 받은 두번째 DNS 이름을 입력합니다.
![](images/obp_create_participant2.png)

14. 수분이 지나면 모든 인스턴스가 생성이 되고 정상적으로 기동이 된 것을 확인하실 수 있습니다.
![](images/obp_create_instance_done.png)

15. Jude Dealer 생성과 동일한 과정으로 **Sam Dealer**도 생성을 합니다.
![](images/obp_create_participant2_1.png)

16. Cluster Configuration에서는 Platform Host에 할당 받은 두번째 DNS 이름을 입력합니다.
![](images/obp_create_participant2_2.png)

17. 몇분이 지나면 모든 인스턴스가 생성이 되고 정상적으로 기동이 된 것을 확인하실 수 있습니다.
![](images/obp_create_participant2_3.png)

---
[이전 Lab으로 이동](../README.md)
