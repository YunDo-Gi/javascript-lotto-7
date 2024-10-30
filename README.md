# javascript-lotto-precourse

## 📝 기능 구현 목록
### 1. 입력 처리
#### 로또 구입 금액 입력
- [ ] 1,000원 단위의 금액 입력 받기
- [ ] 입력 금액에 따른 로또 수량 계산
- [ ] 유효성 검사
  - [ ] 1,000원으로 나누어떨어지지 않는 금액 입력

#### 당첨 번호 입력
- [ ] 쉼표 `,` 로 구분된 6개의 당첨 번호 입력 받기
- [ ] 보너스 번호 1개 입력 받기
- [ ] 유효성 검사
  - [ ] 6개 초과 또는 미만의 번호 입력
  - [ ] 입력된 번호가 1~45 범위를 벗어나는 경우
  - [ ] 당첨 번호에 중복된 숫자가 있는 경우
  - [ ] 보너스 번호가 당첨 번호와 중복되는 경우

#### 공통 고려사항
- [ ] 입력값 누락
- [ ] 음수 값 입력
- [ ] 숫자가 아닌 값 입력

### 2. 핵심 기능
#### 로또 번호 생성
- [ ] 1~45 사이의 중복되지 않는 6개 번호 생성
- [ ] 생성된 번호를 오름차순으로 정렬
- [ ] 구매 수량만큼 로또 번호 생성

#### 당첨 여부 확인
- [ ] 구매한 각 로또 번호와 당첨 번호 비교
- [ ] 일치하는 번호 개수 계산
- [ ] 보너스 번호 일치 여부 확인(5개만 일치하는 경우)
- [ ] 당첨 등수 판단

#### 당첨 내역 및 수익률 계산
- [ ] 각 등수 별 당첨 개수 집계
- [ ] 전체 당첨금 계산
- [ ] 수익률 계산 (소수점 둘째 자리에서 반올림)

### 3. 결과 출력
#### 경주 진행 상태 출력
- [ ] 구매한 로또 수량 출력
- [ ] 생성된 로또 번호 출력 (오름차순)
- [ ] 당첨 내역 출력
- [ ] 수익률 출력

### 4. 예외 처리
- [ ] 모든 예외상황에 `[ERROR]` 프리픽스 추가
- [ ] 에러 발생 시점부터 해당 단계 재시작

## 실행 방법
1. 로또 구입 금액 입력
```bash
구입금액을 입력해 주세요.
14000
```

2. 발행한 로또 수량 및 번호 출력
```bash
14개를 구매했습니다.
[8, 21, 23, 41, 42, 43] 
[3, 5, 11, 16, 32, 38]
...
```

3. 당첨 번호 입력(쉼표로 구분)
```bash
당첨 번호를 입력해 주세요.
1,2,3,4,5,6
```

4. 보너스 번호 입력
```bash
보너스 번호를 입력해 주세요.
7
```

5. 당첨 내역 및 수익률 출력
```bash
당첨 통계
---
3개 일치 (5,000원) - 1개
4개 일치 (50,000원) - 0개
5개 일치 (1,500,000원) - 0개
5개 일치, 보너스 볼 일치 (30,000,000원) - 0개
6개 일치 (2,000,000,000원) - 0개
총 수익률은 62.5%입니다.
```

## 🛠️ 프로그래밍 요구사항

### 개발 환경
- Node.js 20.17.0

### 코드 규칙
1. 코드 구조
   - 시작점: App.js의 `run()`
   - package.json 파일 변경 금지
   - 외부 라이브러리 사용 금지 (제공된 라이브러리 제외)
   - 프로그램 종료 시 `process.exit()` 호출 금지

2. 코드 스타일
   - [JavaScript Style Guide](https://github.com/woowacourse/woowacourse-docs/tree/main/styleguide/javascript) 준수
   - indent depth는 최대 2까지만 허용
   - 3항 연산자 사용 금지
   - 함수는 한 가지 기능만 수행
   - 함수의 길이는 최대 15 라인
   - else 사용 지양

3. 테스트
   - Jest를 사용한 테스트 구현
   - 구현 기능에 대한 단위 테스트 작성 (UI 로직은 제외)

### 사용 가능한 라이브러리
[`@woowacourse/mission-utils`](https://github.com/woowacourse-projects/javascript-mission-utils)
```javascript
// 1에서 45 사이의 중복되지 않은 정수 6개 반환
MissionUtils.Random.pickUniqueNumbersInRange(1, 45, 6);

// 입출력
Console.readLineAsync()
Console.print()
```