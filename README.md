# corona
corona project

# 주제 
실시간 전국 약국 마스크 현황 사이트  
: 성빈이가 주도적으로 ^_^ 나는 서포트
#
## 개발 환경
- Apache Tomcat
- JSP + Servlet
- Mysql
#
## 주요 기능
- 실시간 약국 마스크 현황 시각화(GPS)
- 국내 & 해외 코로나 감염 현황
- 사용자 거주 지역에 따른 마스크 재고 알림
- 약국 운영 시간 표시
- 로그인 & 회원가입 & 문의게시판
#
## API
공공 데이터 포털
* 건강보험심사평가원_공적 마스크 판매 정보 API
* 전국 약국 정보 조회 서비스 API

카카오
* 지도 API
#
## 작업로그
- [x] 예은 : 로그인 / 회원가입 / 인트로 화면 디자인
- [ ] 예은 : 메인 / 게시판 / 회사소개 화면 디자인
- [ ] 성빈 : 사용자 / 게시판 DB 테이블 설계

#
## users : 사용자 테이블
```sql
userid char(15) not null primary key  -- 아이디
passwd char(20) not null              -- 패스워드
birth date not null                   -- 생년월일
area point not null                   -- 지역
email char(40) not null               -- 이메일주소
regist_date datetime not null         -- 가입일
update_date datetime not null         -- 정보수정일
maskalarm_yn boolean not null         -- 마스크알림여부
use_yn boolean not null               -- 사용여부
withdraw_date datetime null           -- 탈퇴일시
```
## notices : 공지사항 테이블
```sql
noticeid int not null primary key     -- 공지사항ID
title char(50) not null               -- 제목
content varchar(1000) not null        -- 내용
regist_date datetime not null         -- 작성일시
update_date datetime null             -- 수정일시
delete_date datetime null             -- 삭제일시
writer char(15) not null              -- 작성자
views int not null                    -- 조회수
file1 char(100) null                  -- 파일경로1
file2 char(100) null                  -- 파일경로2
```
## q&a : 문의 테이블
```sql
noticeid int not null primary key     -- 공지사항ID
title char(50) not null               -- 제목
content varchar(1000) not null        -- 내용
regist_date datetime not null         -- 작성일시
update_date datetime null             -- 수정일시
delete_date datetime null             -- 삭제일시
writer char(15) not null              -- 작성자
views int not null                    -- 조회수
file1 char(100) null                  -- 파일경로1
file2 char(100) null                  -- 파일경로2
passwd char(20) null                  -- 패스워드
category char(20) not null            -- 카테고리
```
#
## 작업 일정
- [x] 2020.04.01 ~ 2020.04.07 : 화면 설계 - 예은
- [x] 2020.04.01 ~ 2020.04.07 : 기능 상세 설계 - 예은, 성빈
- [ ] 2020.04.08 ~ 2020.04.10 : DB 설계 - 성빈
- [ ] 2020.04.13 ~ 2020.04.24 : FrontEnd 구현 - 예은
- [ ] 2020.04.13 ~ 2020.04.24 : BackEnd 구현 - 예은, 성빈
- [ ] 2020.04.27 ~ 2020.04.30 : 테스트 및 마무리 - 예은, 성빈
