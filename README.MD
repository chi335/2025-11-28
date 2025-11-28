# Unreal Engine 5 기초 가이드 요약  
*(Unreal Engine 5 Beginner Tutorial guide_수정본.pdf)*

이 문서는 언리얼 엔진 5의 설치, 프로젝트 생성, 화면 구성, C++ 개발 환경 설정까지 설명하는 기초 가이드입니다.

---

## 1. EP1: 언리얼 엔진 설치 및 실행

### 1-1. 에픽게임즈 런처 다운로드 및 로그인
- 에픽게임즈 웹사이트에서 런처 다운로드 후 설치  
- 계정 로그인 또는 신규 가입

### 1-2. 언리얼 엔진 설치
- 런처 좌측 메뉴에서 **Unreal Engine** 선택  
- **Library** 탭 → 엔진 버전 선택 → Install  
- 옵션(Option) 버튼에서 필요한 컴포넌트 선택 가능

### 1-3. 내 프로젝트 확인
- Library → My Projects에서 기존 프로젝트 확인  
- 기본 저장 경로가 아닐 경우 자동 인식되지 않을 수 있음

---

## 2. 새 프로젝트 생성
1. Launch 버튼 클릭 → Unreal Project Browser 실행  
2. 카테고리 선택 (Games, Architecture, Film 등)  
3. 템플릿 선택 (Blank, Third Person 등)  
4. 프로젝트 이름 입력 후 Create

### 템플릿 종류 예시
- First Person  
- Third Person  
- Virtual Reality  
- Architecture 등

---

## 3. 언리얼 엔진 화면 구성

| 구성 요소 | 설명 |
|----------|------|
| Viewport | 게임 화면 및 오브젝트 배치 |
| Menu & Toolbar | 프로젝트 실행 및 기본 기능 |
| Outliner | 오브젝트 계층 구조 |
| Detail Panel | 선택한 오브젝트의 세부 설정 |
| Content Browser | 프로젝트 리소스 관리 |
| Actor Placement | 기본 액터 목록 |

---

## 4. 기타 기본 작업

### 기본 조작
- 마우스 우클릭 + WASD : 이동  
- Q / W / E / R : 선택 · 이동 · 회전 · 스케일

### 레벨 생성
- Content Browser → 우클릭 → Folder 생성  
- 우클릭 → Level 생성

### C++ 개발 환경 설정
- Visual Studio 설치  
- "C++을 사용한 게임 개발" 워크로드 추가

---

# Unreal Engine 상호작용 오브젝트 가이드 요약  
*(Unreal Engine Interaction Object.pdf)*

Fab 스토어에서 문(Door) 애셋을 다운로드하고, 프로젝트에 통합해 상호작용 가능한 문 액터(BP_DoorActor)를 제작하는 과정을 설명합니다.

---

## 1. Fab 스토어에서 Door 애셋 다운로드

### 1-1. 애셋 검색 및 라이브러리 추가
- 에픽게임즈 런처 → Fab 진입  
- 필터(예: 무료) 적용  
- 검색창에 `door` 입력  
- 원하는 애셋 선택 → 라이선스 설정 → "내 라이브러리에 추가"

### 1-2. 다운로드 및 익스포트 설정
- 저장 위치 선택  
- Target: Custom (Disk)  
- Format: FBX  
- 텍스처 등 추가 파일 다운로드  
- 익스포트 실행

---

## 2. 프로젝트로 애셋 통합
- 다운로드한 애셋을 Content Browser로 드래그 앤 드롭

---

## 3. 인터페이스 블루프린트 생성
- Blueprint Interface 생성 (예: `BP_Interaction`)  
- 함수 추가  
  - Interact  
  - Can Receive Trace

---

## 4. UI 설정 (커서 · 상호작용 안내)
- 위젯(Blueprint Widget) 생성 (예: UI_Cursor)  
  - 커서 이미지 추가  
  - 앵커 중앙 설정  
- 상호작용 안내 위젯도 별도 제작

---

## 5. 문 액터 블루프린트 생성 (BP_DoorActor)

### 구성 요소
- Static Mesh (문 모델)  
- Sphere Collision  
- Widget Component  
  - Widget Class를 상호작용 UI로 설정

### 인터페이스 적용
- Class Settings → Implemented Interfaces → `BP_Interaction` 추가

---

## 6. 문 Pivot(피벗) 조정
1. Door Static Mesh 선택  
2. 모델링 모드 → Xform  
3. Pivot 편집 활성화  
4. 경첩 위치로 피벗 이동하여 회전 기준점 설정

---
