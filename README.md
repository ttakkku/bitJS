# binJS File Format

4    8        8
xxxx yyyyyyyy zzzzzzzz

CMD  Arg0     Arg1

* 한줄에 각각 4자, 8자, 8자. 총 20자의 숫자가 있어야 합니다
* x, y, z의 숫자는 모두 2진수여야 합니다
* x, y, z 사이의 공백은 중요하지 않습니다
* CMD는 실행할 명령을 정의하고 Arg0과 Arg1은 특정한 값을 나타낼 수 있습니다

# Commands
## 0000 : NUL
이 CMD값은 "공백"을 의미 합니다. 런타임에서 이 줄은 무시됩니다

## 0001 : SET
이 CMD값은 "대입"을 의미 합니다
이 줄의 Arg0값은 대입할 메모리의 주소를 의미하고
Arg1값은 대입할 숫자값을 의미합니다

## 0010 : ADD
이 CMD값은 "추가"를 의미 합니다
이 줄의 Arg0값은 추가할 메모리의 주소를 의미하고
Arg1값은 추가할 숫자값을 의미합니다

## 0011 : SUB
이 CMD값은 "가감"을 의미 합니다
이 줄의 Arg0값은 가감할 메모리의 주소를 의미하고
Arg1값은 가감할 숫자값을 의미합니다

## 0100 : DIS
이 CMD값은 "출력"을 의미 합니다
이 줄의 Arg0, Arg1값은 출력할 메모리의 주소를 의미하고
두 메모리 주소 사이에 있는 모든 값을 출력합니다

## 0101 : DIX
이 CMD값은 "문자출력"을 의미 합니다
이 줄의 Arg0, Arg1값은 출력할 메모리의 주소를 의미하고
두 메모리 주소 사이에 있는 모든 값을 출력합니다

## 1111 : END
이 CMD값은 "중단"을 의미 합니다
이 줄의 Arg0값은 중단시 반환할 코드를 의미하고
Arg1값은 무시됩니다