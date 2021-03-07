0. 대부분이 class이고 객체이다.
   
   && , ||
   // or /*  *  */


1. Data Type

  * 정수 : int a = 1
  * 실수 : double b = 2.5
  * 문자열 : String name = '용초' or "용초"
          - 파이썬 처럼 print(name1 + name2) 처럼 사용 가능
  * boolean : bool isTrue = true;
             bool inFalse = false;
  
  * 걍 변수 : var
          - var변수 선언과 동시에 입력하는 내용의 type으로 고정이 된다. 
            ex) var a = 1; a = 'hi' (X) -> a는 int형으로 고정
                var a;  a = 1; a = 'hi' (O)
          
  * dynamic type : var와 다르게 dynamic a = 1;  a = 'hi'; 형식의 변환이 자유롭다.
  
  * final & const : var와 비슷하게 data 값을 고정시켜주는 역할.
  
   - final a = 1;  : 사용자가 실행하는 런타임 때 값이 대입. 이 부분은 정의만 해두는 것이고 후에 생성자를 통해 값을 한번 바꿀 수 있음.
   - const a = 1;  : 컴파일이 될 때 값이 대입 _불변 but fast
   
   
  ㄴ double a = 1; 은 되지만 int a = 1.5 는 안된다.
  ㄴ '/'가 몫을 구하는 것이 아니라 나누기 그 자체임. 고로 실수형으로 반환하는 연산이고 몫은 ~/ 으로 구할 수 있다.
  ㄴ print('$name1$name2')는 문자 그대로 출력되는 것이 아니라 $뒤에 무언가 작성하면 그것을 변수 처리를 해주기 때문에 위와 동일하게 나옴. (약간 파이썬의 f-string느낌)
     ex) String word = '나는 $a살 입니다' -> 나는 5살 입니다
     
  * list

   - List ages = [1,2,3];    : 인덱스값 변환가능, 

  * Map
  
   - Map person = {'name' : '용초', 'age' : 24}; : 처럼 약간 구조체 느낌
   

2. if문 _ c언어

   * if(true){
      print(a);
   }
   else if{
      print(b);
   }
   else{
      print(c);
   }
   
3. 반복문 _ c언어 + py3

  * for (int i=0; i<10;i++){
        print(a);
    }
    
  * list ages = [1,2,3];
    for (var age in ages){
      print(age);
    }
 
  
  * while(true){
      print(a);
    }
    
4. 함수 _ c

  * int add(int a, int b){
        return a+b;
    }
    
    -   return 타입은 쓰지 않아도 되지만 헷갈린다면 쓰자.
  * method
   
   - .where() : 괄호 안의 조건을 이행시키는 
   - .forEach() : 주어진 함수를 리스트 요소 각각 실행시킴 ex_list.forEach(print)처럼 print같은 함수들도 변수처럼 이용가능.
   - .contain() : ex_ list = ['abc', 'def', 'efg']  print( list.contains('ef') ) = true
                  arrow에 lambda에 적용하면 filtered_list.where((list) => list.contains('ef')).forEach(print) = def, efg
   
   
5. arrow/lambda

  * ex) var filter = ages.where((age) => age > 10);    : where은 조건메소드, '=>' 기호 왼쪽에는 변수명, 오른쪽은 동작할 코드나 반환값 _ 10초과의 값들이 filter변수에 입력.
  
6. import

  * import '파일명.dart' 를 실행하면 그 파일에 있는 함수같은 것을 쓸 수 있다. 함수 밖에 선언.
  * 외부 라이브러리를 가져올 수도 있다.
  
7. class

 class Person{
  String name;
  int age;
  String sex;
  
  Person({String name, int age, String sex}){
    this.name = name;
    this.age = age;
    this.sex = sex;
  }
}

void main(){

  Person p1 = new Person();   //p1이 Instance, new Person이 생성자
  Person p2 = new Person();   
    
  
}
    