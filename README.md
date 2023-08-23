# toy_data_analysis

<details>
<summary>각 변수별 입원기간의 차이</summary>

### DDA 분석
| 변수    | 변수 설명   | 데이터 분류 | 분석가 의견     |
|------|------|-----|-------|
| 입원기간       | 입원 기간              | 날짜형 |                                     |
| 신장          | 환자의 신장             | 연속형 | 소수점으로 표현 가능한 수치형 데이터   |
| 체중          | 환자의 체중             | 연속형 | 소수점으로 표현 가능한 수치형 데이터   |
| 고혈압여부     | 환자의 고혈압여부       | 범주형 | 해당 존재 여부만을 나타내는 데이터     |
| 당뇨여부       | 환자의 당뇨여부         | 범주형 | 해당 존재 여부만을 나타내는 데이터    |
| 성별          | 환자의 성별             | 범주형 | 해당 존재 여부만을 나타내는 데이터    |
| 연령          | 환자의 나이             | 연속형 | 소수점으로 표현 가능한 수치형 데이터  |
| 척추전방위증   | 환자의 척추전방위증 여부 | 범주형 | 해당 존재 여부만을 나타내는 데이터    |
| 디스크위치     | 환자의 디스크 위치      | 범주형 | 분류를 목적으로 하는 데이터          |
| PI            | PI                    | 연속형 | 소수점으로 표현 가능한 수치형 데이터  |
| PT            | PT 디스크 높이         | 연속형 | 소수점으로 표현 가능한 수치형 데이터  |
| Vaccum disc   | Vaccum disc           | 범주형 | 소수점으로 표현 가능한 수치형 데이터  |
| BMI           | 환자의 BMI             | 연속형 | 소수점으로 표현 가능한 수치형 데이터  |

변수 선택의 이유 : 해당 변수들은 척수 시술 및 수술후에 환자들의 몸 상태 회복에 관련이 있다고 생각되어 지는 것으로 선택하였음.

</details>

<details>
<summary>목표변수 '입원기간'과의 상관관계 확인</summary>

### EDA 분석
| 변수 | 상관관계 분석 |
|------|------|
| 신장          | 신장에 따른 연간관계를 찾아 보기 힘들다.                 |
| 체중          | 체중에 따른 연간관계를 찾아 보기 힘들다.                 |
| 고혈압여부     | 고혈압이 있을수록 입원 기간이 길어지는 것으로 보여진다.   |
| 당뇨여부       | 당뇨여부에 따른 연간관계를 찾아 보기 힘들다.             |
| 성별          | 여성이 남성에 비해 입원 기간이 높은 것으로 보인다.        |
| 연령          | 고연령으로 갈수로 입원기간이 길어지는 것으로 보여진다.     |
| 척추전방위증   | 척추전방위증에 따른 입원기간의 연관성을 찾아 보기 힘들다.  |
| 디스크위치     | 디스크 위치에 따른 입원기간의 연관성이 높은 것으로 보인다. |
| PI            | PI에 따른 연간관계를 찾아 보기 힘들다.                   |
| PT            | PT에  따른 연간관계를 찾아 보기 힘들다.                  |
| Vaccum disc   | 여부에 따른 입원기간의 연관성이 높은 것으로 보인다.       |
| BMI           | BMI에 따른 입원기간의 연관성을 찾아 보기 힘들다.          |
<summary>분석스토리</summary>
분석내용 
분석내용(봉원희) : 척추시술 및 수술을 받은 환자의 입원기간은 대표적으로 성별, 신장, 체중, 연령이 많은 영향이 끼치는 것으로 확인 되었습니다.
</details>

<details>
<summary>단일변수의 정규성 여부 판단과 상관관계 증명</summary>

### CDA 분석
correlation coefficient(상관관계) : -1 ~ 1 사이 (0에 가까우면 관계없음, -1에 가까우면 반비례, 1에 가까우면 비례(기준:p-value 0.05) 대립가설 참)
| 변수 | 상관관계 이유 |
|------|------|
| 신장          | 신장에 따른 입원기간의 상관관계가 있다.(pvalue=0.04748161479152065)        |
| 체중          | 체중에 따른 입원기간의 상관관계가 있다.(pvalue=0.01987223464009912)        |
| 고혈압여부     | 고혈압여부에 따른 입원기간의 상관관계가 있다.(pvalue=0.07613024933800935)   |
| 당뇨여부       | 당뇨여부에 따른 입원기간의 상관관계가 없다.(pvalue=0.34861241786231345)    |
| 성별          | 성별은 입원기간에 상관관계가 있다. (pvalue=0.02094153582671839)            |
| 연령          | 연령에 따른 입원기간의 상관관계가 있다. (pvalue=0.029203834197053385)      |
| 척추전방위증   | 척추전방위증에 따른 입원기간의 상관관계가 없다.(pvalue=0.34557643733933774) |
| 디스크위치     | 디스크위치에 따른 입원기간은 상관관계가 없다.(pvalue=0.835230775207565)     |
| PI            | PI에 따른 입원기간의 상관관계가 없다.(pvalue=0.6809981071755282)          |
| PT            | PT에 따른 입원기간의 상관관계가 없다.(pvalue=0.6188437581048726)          |
| Vaccum disc   | Vaccum disc 와 입원기간은 상관관계가 없다.(pvalue=0.2552260504137014)     |
| BMI           | BMI에 따른 입원기간의 상관관계가 없다.(pvalue=0.15751063851862063)         |
</details>