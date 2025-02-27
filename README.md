---
created: 2025-02-26 22:19
tags:
  - 클라우드
  - Cloud
  - Azure
  - VPN
  - Capture
  - Sniffer
---
# 🌱 Azure Virtual HUB VPN 용 패킷 캡처

## 패킷 캡처 시작 - 포털

Azure Portal에서 패킷 캡처를 설정할 수 있습니다.

1. Azure Portal에서 Virtual WAN 으로 이동합니다.

2. 목록에서 Virtual WAN 리소스를 선택합니다.

3. 왼쪽에서 **연결**을 누르고 **허브**를 선택합니다.

4. 목록에서 Virtual Hub 리소스를 선택하여 이동합니다.
	- ![Virtual WAN-Hub](/Files/azure-vwan-hub.jpg)

6. 왼쪽에서 **연결**을 누르고 **VPN(사이트 간)** 을 선택합니다.

7. 화면 위쪽에서 **패킷 캡처**를 선택하여 패킷 캡처 페이지를 엽니다.	
 	- ![Virtual Hub VPN Packet Capture](/Files/azure-vwan-hub-vpn-capture-1.jpg)

8. 패킷 캡처 **▶️ 시작**을 선택합니다.	
 	- ![Virtual Hub VPN Packet Capture Start](/Files/azure-vwan-hub-vpn-capture-2.jpg)

9. 패킷 캡처 시작 페이지에서 필요한 조정을 합니다. 내부 및 외부 패킷을 모두 캡처하려는 경우 “단일 방향 트래픽만 캡처” 옵션을 선택하지 마세요.

10. 설정을 구성한 후 패킷 캡처 **▶️ 시작**을 클릭합니다.	
 	- ![Virtual Hub VPN Packet Capture Start](/Files/azure-vwan-hub-vpn-capture-3.jpg)


## 패킷 캡처 중지 - 포털

패킷 캡처를 완료하려면 읽기/쓰기 액세스 권한이 있는 유효한 SAS(또는 공유 액세스 서명) URL이 필요합니다. 패킷 캡처가 중지될 때 패킷 캡처의 출력은 SAS URL에서 참조하는 컨테이너에 기록됩니다.

1. SAS URL을 가져오려면 스토리지 계정으로 이동합니다.

2. 사용하려는 컨테이너로 이동합니다.
	- ![azure-storage-container](/Files/azure-storage-container.jpg)

3. 만약 컨테이너가 없다면 **+ 컨테이너** 버튼을 눌러 컨테이너를 신규로 생성합니다.
	- ![azure-storage-container-new](/Files/azure-storage-container-new.jpg)

4. 마우스 오른쪽 단추를 클릭하여 드롭다운 목록을 표시합니다. **SAS 생성**을 선택하여 SAS 생성 페이지를 엽니다.
	- ![azure-storage-container-create-sas](/Files/azure-storage-container-create-sas.jpg)

5. SAS 생성 페이지에서 설정을 구성합니다. 읽기 및 **쓰기** 액세스 권한을 부여했는지 확인합니다. **SAS 토큰 및 URL 생성**을 클릭합니다.
	- ![azure-storage-container-create-sas-options](/Files/azure-storage-container-create-sas-options.jpg)
	
6. SAS 토큰 및 SAS URL이 생성되고 단추 바로 아래에 표시됩니다. Blob **SAS URL**을 복사합니다.
	- ![azure-storage-container-create-sas-options](/Files/azure-storage-container-create-sas-url.jpg)

1. Azure Portal의 VPN(사이트 간) 패킷 캡처 페이지로 다시 이동하고 **패킷 캡처 중지** 단추를 클릭합니다.

2. 출력 SAS URL 텍스트 상자에 SAS URL(이전 단계의)을 붙여넣고 패킷 캡처 중지를 클릭합니다.

3. 패킷 캡처(pcap) 파일은 지정된 계정에 저장됩니다.

---
## Reference
1. https://learn.microsoft.com/ko-kr/azure/vpn-gateway/packet-capture
