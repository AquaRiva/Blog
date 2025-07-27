---
title: 코드로 인프라 자동화
draft: false
tags: [프로젝트, 인프라, 자동화, IaC, VM]
aliases:
  - One Touch
---

<div class="portfolio-content">

<div class="portfolio-header">

IaC를 주제로 Python, Ansible, PowerShell을 활용하여 인프라를 코드로 자동화한 프로젝트입니다.

</div>

<div class="portfolio-overview">

## 프로젝트 개요

- **목표:** 코드 기반 인프라 자동화 환경 구축 및 실습
- **주요 기술:** Python, Ansible, PowerShell, VMware, GNS3, TrueNAS
- **기간:** 2025.04.09 ~ 2025.05.02

</div>

<div class="team-section">

## 팀 구성 및 역할

<div class="team-grid">

- **PM 최호준:** 퍼블리싱 총괄, TrueNAS 코드 작성
- **PL 홍명기:** 기술 스택 담당, VM 생성/삭제 코드 작성
- **서기 이성현:** PPT, Vyos, Mailserver 코드 작성
- **서기 이세일:** 문서, DNS 코드 작성
- **발표자 박선우:** 발표, HTTP/NFS 코드 작성

</div>

</div>

## 전체 아키텍처
![구성도](./images/first-project-architecture.png)

<div class="tech-stack">

## 사용한 주요 스택

<div class="tech-grid">

- **VMware vSphere, ESXi:** 배포 환경 구성
- **GNS3:** UDP 터널링 통한 네트워크 연동
- **TrueNAS:** NFS 서버 설계 및 백업

</div>

</div>

## 프로젝트 주요 내용

본 프로젝트는 인프라 자동화의 전 과정을 코드로 구현하는 것을 목표로 하였으며, 각 팀원이 다양한 인프라 요소를 자동화하는 데 기여하였습니다.

### 전체 자동화 흐름
- **VM 생성/삭제 자동화:** Python 스크립트로 ESXi 환경에서 VM을 생성/삭제
- **네트워크 자동화:** GNS3 UDP Tunnel, Vyos VM 자동화, NAT 및 인터페이스 설정
- **스토리지 및 백업 자동화:** TrueNAS를 활용한 NFS 서버, 백업 및 로그 관리 자동화
- **메일/네임서버 자동화:** Ansible, PowerShell을 통한 Mail Server, DNS Server 자동화

### 주요 챕터별 자동화
- **VM 생성/삭제:** Python, ESXi API
- **Vyos 설치/설정:** Python subprocess, paramiko, SSH 자동화
- **GNS3 UDP Tunnel:** GNS3 프로젝트 파일 및 네트워크 연동 자동화
- **TrueNAS 설정:** Logrotate, Crontab, Samba를 통한 백업 및 로그 관리
- **Mail Server:** Ansible-playbook을 통한 메일 서버 자동화
- **DNS Server:** PowerShell 스크립트로 Zone/레코드 생성 및 네임서버 위임

### 협업 및 문서화
- 각 파트별 자동화 코드를 개발하고, 실습 결과를 문서화 및 발표 자료로 정리
- 중간 피드백 및 결과 공유를 통해 프로젝트 완성도 향상

---

## VM 생성 자동화
### 목표
- Python을 활용해 VMware ESXi 환경에서 VM을 자동으로 생성/삭제하는 코드 구현

### 주요 단계
1. Setup.py 파일 실행 (Automatic Server에서 VM 생성/삭제 Python 파일 실행)
2. IP주소 입력 (생성/삭제할 VM의 IP주소 입력)
3. ESXi 확인 (ESXi에 접속해 원하는 작업이 수행되었는지 확인)

### 성과
- 반복적이고 수동적인 VM 생성/삭제 작업을 자동화하여 효율성 향상
- 실습 환경에서 다양한 VM을 신속하게 배포/회수 가능
- 코드 기반 인프라 관리 경험 및 IaC 실전 역량 강화

---

## TrueNAS 자동화
### 목표
- 내부 시스템에 메일서버, DNS, TrueNAS를 추가로 구성하고 백업 및 로그 관리를 자동화

### 주요 단계
1. TrueNAS Pool 구성 및 NFS 서버 설계
2. 메일서버에 Logrotate, Crontab, Samba 설정
3. 백업 로그 자동화 및 Windows에서 내용 확인

### 성과
- 스크립트 기반 백업/로그 관리 자동화
- 실시간 백업 및 데이터 무결성 확보

---

## Vyos VM 및 네트워크 자동화
### 목표
- Python을 활용한 Vyos VM 생성 및 네트워크 인터페이스, NAT 자동화

### 주요 단계
1. Python subprocess로 Vyos VM 생성
2. SSH로 초기 설정 및 외부 인터페이스 연결
3. Paramiko로 NAT/Interface 자동화

### 성과
- 네트워크 장비 자동화 및 실습 환경 신속 구축

---

## Mailserver 자동화
### 목표
- Ansible-playbook을 통한 메일 서버(Postfix, Dovecot, DNS) 자동화

### 주요 단계
1. Ansible Hosts에 Mailserver 그룹 추가
2. Auto server에서 Ansible-playbook 실행
3. 메일 송수신 테스트 자동화

### 성과
- 메일 서버 배포 및 테스트 자동화, 운영 효율성 향상

---

## DNS Server 자동화
### 목표
- PowerShell 스크립트로 DNS Zone/레코드 생성 및 네임서버 위임 자동화

### 주요 단계
1. PowerShell로 Zone/레코드 생성
2. Name 서버 위임 및 Nslookup 검증

### 성과
- DNS 관리 자동화, 네임서버 신속 배포

---

## HTTP/NFS 자동화
### 목표
- Ansible-playbook을 통한 HTTP, NFS 서버 자동화 및 테스트

### 주요 단계
1. Ansible Hosts에 client 그룹 추가
2. Auto server에서 Ansible-playbook 실행
3. NFS 서버의 index.html 적용 및 마운트 확인

#### 성과
- HTTP/NFS 서버 자동화, 실습 환경 내 서비스 신속 배포

---

<div class="impact-section">

## 해결한 문제점

### 기존 문제점
1. **수동 인프라 구축:** 개발자별 환경 차이로 인한 "내 컴퓨터에서는 되는데" 문제
2. **반복 작업:** VM 생성, 네트워크 설정 등 반복적인 수동 작업
3. **문서화 부족:** 수동 설정으로 인한 문서화 어려움
4. **확장성 한계:** 수동 관리로 인한 확장성 부족

### 해결 방안
1. **IaC 도입:** Python, Ansible, PowerShell을 활용한 코드 기반 인프라 관리
2. **자동화 파이프라인:** 스크립트 기반 자동화로 반복 작업 제거
3. **버전 관리:** Git을 통한 인프라 코드 버전 관리
4. **표준화:** 팀 전체가 동일한 환경에서 작업 가능

---

## 기술적 도전과 해결책

### 주요 도전 과제
1. **다양한 기술 스택 통합:** Python, Ansible, PowerShell, VMware, GNS3, TrueNAS
2. **실시간 네트워크 연동:** GNS3와 실제 네트워크 환경 연동
3. **자동화 스크립트 안정성:** 다양한 환경에서의 스크립트 실행 안정성

### 해결책
1. **모듈화 설계:** 기능별로 분리된 스크립트 모듈 개발
2. **에러 핸들링:** 예외 상황 처리 및 로깅 시스템 구축
3. **테스트 환경:** 개발/테스트/운영 환경 분리로 안정성 확보

---

<div class="back-home">

> [🏠 Home으로 돌아가기](index.md)

</div>

</div> 