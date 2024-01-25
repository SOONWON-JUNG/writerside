# 계약등록(신) 승인합의수수료

## 승인합의 수수료 변경 사항
- 승인합의 점소 정보 위치 변경 (관리거래처코드 기준)
- 주문 접수 및 운송장 등록에서 사용하는 업무 거래처 히스토리 테이블 이용

![Create new topic options](img1.png){ border-effect="line" thumbnail="true" width="350"}

## AS-IS VS TO-BE

> AS-IS TO-BE TAB 클릭
>
{style="tip"}

<tabs>
    <tab title="AS-IS">
      <code-block lang="plain text">
         - 계약이 추진중, 계약만료, 거래중 여부 상관 없이 유일한 최근 1개의 데이터
         - 테이블 명 : TCT_JOB_CUST (업무 거래처) 
      </code-block>
    </tab>
    <tab title="TO-BE">
        <code-block lang="plain text">
         - 운송장 등록에 사용되는 거래처의 해당 시점의 정보    
         - 적용일자 기준    
         - 테이블명 : TCT_JOB_CUST_HST (업무 거래처 히스토리) 
         </code-block>
    </tab>

</tabs>

> **계약 데이터베이스 모델링 이슈**
>
> - 동일한 이름의 데이터(승인합의 점소코드, 차감요율)이 각기 다른 테이블
    > (TCT_JOB_CUST/TCT_JOB_CUST_HST)에 저장
> - 중복된 항목에 일관되지 않은 데이터, 비정상적 업데이트 등 이슈 발생
> - 설계(모델링) 부터 잘못되어 있기에 수정을 위해 많은 시간과 비용 필요
>
{style="note"}