---
layout: post
title: commands
categories: Linux
---

Linux commands

## chmod

권한 부여하기

rwx(read: 4, write: 2, execute: 1)

1) 문자열 모드

```chmod 옵션 (reference)(operator)(modes) 파일```

**reference(대상)**
- u : user의 권한 (사용자의 권한)
- g : group의 권한 (파일의 group 멤버인 사용자의 권한)
- o : other의 권한 (user, group의 멤버가 아닌 사용자의 권한)
- a : all의 권한 (위의 셋을 포함하는 모든 사용자의 권한)

**operator**
- ＋ : 해당 권한을 추가한다.
- － : 해당 권한을 제거한다.
- = : 해당 권한을 설정한데로 변경한다.

**modes**
- r : read 권한 (읽기)
- w : write 권한 (쓰기)
- x : excute 권한 (실행)
- － : 사용권한없음

**예제**
```
chmod ug+rw sample : sample파일의 user나 group 멤버들에게 읽기, 쓰기 권한을 추가
chmod u=rwx,g+x sample : sample파일의 user는 읽기,쓰기,실행 권한 부여, group 멤버들에게 실행권한 추가
```

2) 8진법 수 모드

```chmod 옵션 (8진법 수) 파일```

**예제**
```
chmod 777 test : test 파일의 user, group, other의 권한을 모두 rwx로 변경.
chmod 4755 test : test파일의 user id설정을 지정하고, user에게 rwx 권한 부여, group과 other에게 r-x권한부여
```


## 파일 비교하기

```
diff file1 file2
diff3 file1 file2 file3
```

```
comm fil1 file2 #두 파일에서 공통적인 부분과 한쪽에만 있는 부분 찾기
-1 : 두 파일을 비교하여 첫번째 파일과 다른 두번째 파일의 내용과 공통 부분 
-2 : 두번째 파일과 다른 부분의 첫번째 파일내용과 공통 부분 
-3 : 두 파일의 공통된 부분 제외한 나머지 즉 차이 부분
```


## find

파일 찾기

```
find . -name [FILE] -type f
find . -name "*str*" -type d
find / -maxdepth 1 -name "sys" #sys라는 파일을 root 디렉터리에서만 검색
```


## grep

파일에서 검색하기

```
grep "STR" [FILE]	#대상 파일에서 문자열 검색
grep "STR" *		#현재 디렉터리 모든 파일에서 문자열 검색
grep "STR" *.ext	#특정 확장자를 가진 모든 파일에서 문자열 검색

grep -i "STR" [FILE]	#대소문자 구분하지 않고 문자열 검색
grep -v "STR" [FILE]	#매칭되는 패턴이 존재하지 않는 라인 검색
grep -w "STR" [FILE]	#단어 단위로 문자열 검색
grep -n "STR" [FILE]	#검색된 문자열이 포함된 라인 번호 출력
grep -r "STR" [FILE]	#하위 디렉터리를 포함한 모든 파일에서 문자열 검색
grep -H "STR" *		#검색 결과 앞에 파일 이름 표시
```


## 텍스트 처리

```
cat books.csv						#매개변수로 전달된 파일 출력
cat books.csv | grep 파이썬		 #"파이썬"이라는 문자열이 포함돼 있는 줄만 출력
cat books.csv | cut -d , -f 1,2		#,(쉼표)로 구분된 첫 번째 열과 두 번째 열만 출력
									#-d 옵션으로 구분할 문자, -f 옵션으로 열의 번호(여러 개 지정 가능) 지정
cat books.csv | sed 's/,/ /g'		#s/<정규 표현식>/<치환할 문자>/<옵션> => 특정 조건에 맞는 줄을 치환하거나 제거
```


