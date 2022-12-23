# 아이돌 리스트 조회 API

Request : 
Method : GET/POST

        https://www.tnpick.com/sho/api/v1/donation/rank/{PRD_ID}/?auth_key={AUTH_KEY}&token={TOKEN} 


| 매크로명  | 설명   |
|--|--|
| PRD_ID | 상품 ID  |
| AUTH_KEY  | 인증 KEY - 연동에 필요한 KEY로서 TNK 대시보드에서 확인 가능함. |
| TOKEN  | PRD_DI + AUTH_KEY를 MD5 HASH한 값이다.  |

Response:
type : JSON

    { res_cd : 1 (succes) or -1 (fail_1) or -2 (fail_2) or ...
    res_msg : ""  or "에러메시지",
    prd_name : 상품명(기부상품명),
    prd_id : 상품ID,
    rank_list : [
                   { idol_name : text, rank : int, donation_count : int}, { ... }, ...
                ]
    }
  

| 컬럼명| 설명   | 설명 |
|--|--|--|
| res_cd | 응답코드  | 100 (성공), 200(인증실패) |
| res_msg | 응답 메시지  | 성공이면 "", 실패이면 메시지 출력
| prd_name | 상품명  | 기부상품명
| prd_id | 상품ID  | 기부상품 ID
| rank_list | 순위 LIST  | 순위List , Format JSONArray



## rank_list

| 컬럼명| 설명   |
|--|--|
| idol_name | 아이돌 이름  |
| rank | 순위  |
| donation_count | 기부건수  |


