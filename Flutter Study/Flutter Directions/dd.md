* Class : 객체의 속성과 기능이 정의 되어있는 설계도
* Object : class가 정의되고 메모리에 할당되었을 때 이를 객체라 함
* Instance : object가 소프트웨어적으로 실현된 것. instance는 object와 비슷한 말이긴 하지만 '~부터 생성되었다'라는 의미를 내포하기 때문에 ~와의 관계에 좀 더 무게가 실림.
             __object는 class의 instance다.
* 위젯(class)?
  - 어플 상에서 모든 것이 위젯이다. 구성요소나 padding, column같은 요소들, 나아가 어플 그 자체도 위젯이라고 할 수 있다.
  - Flutter의 모든 위젯은 argument를 갖는다.
  - Stateless Widget : 변화가 없는 정적인 위젯_ 스크린상에 존재만 한다 / 어떠한 실시간 데이터도 저장x / 모양 상태를 변화시키는 value값을 지니지 않는다.
  - Stateful Widget : 움직임이나 변화가 있는 위젯_ 체크박스, 텍스트박스 처럼 사용자의 interaction에 따라 변화가 일어나는 것.
  - Widget tree : Widget은 부모자식 위젯으로 구성. flutter SDK에서 받은 모든 위젯을 사용할 수 있음.
    ㄴ MyApp(커스텀_이름은 고정x 바꿀수o) : 루트 위젯, stateless, ㅃㅕ대
     ㄴ MaterialApp : 전체 앱을 감싸는 위젯. 
      ㄴ MyHomePage(커스텀) : ui나 디자인이 들어감
       ㄴ Scaffold : 앱 화면과 기능을 구성하기 위한 빈 페이지를 준비해주는 위젯. 이미지 버튼 텍스트 등등이 들어감.
        ㄴ AppBar : 앱 상단
         ㄴ Text : Login 등..?
        ㄴ Center
         ㄴ Column
          ㄴ Image
          ㄴ TextField
          ㄴ Button

* 파일 
  - pubspec.yaml : meta data를 정의, 관리하는 파일. 프로그램 버전이나 사용환경, 라이브러리 등을 정의.
  - lib_main.dart : 코딩하는 주요 파일
  -  
  
* 진행
 
  - 'package:flutter/material.dart'를 항상 처음에 import해주고 시작한다.
  
  
  
* 주요기능 몇몇

  - 파일에 이미지같은 걸 추가하고 터미널에서 
    flutter pub get
    flutter upgrade 
    이 두 명령어를 입력해줘야 호출해서 쓸 수가 있습니다.
    그리고 pubspec.yaml의 assets: 이 부분에서 파일 경로 입력해줄 때 들여쓰기 잘 확인해야 인정해줍니당. assets앞에 탭1번 이미지 경로 앞에 탭 두번.
    
* 예시 코드

  
  import 'package:flutter/material.dart';

void main() => runApp(MyApp()); //MyApp이라는 뼈대를 만들어주는 것.

class MyApp extends StatelessWidget { //stl를 치면 자동으로 정적인 커스텀 위젯 class 구조가 뜸 
  @override
  Widget build(BuildContext context) {
    return MaterialApp(  
      title: '무야호',   // 앱의 통칭. 이름 만들어주는것
      theme: ThemeData(    // 앱의 기능적인 디자인 테마를 지정 
        primarySwatch: Colors.blue // 앱의 기본적인 색상 견본 설정 
      ),
      home: MyHomePage(), //앱이 실행되었을 때 앱에 가장 먼저 보여지는 것. 여기서 MyHomePage를 입력해줘도 되고 바로 Scaffold 입력해도 된다.
    );
  }
}

class MyHomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(   // 앱에서 다장한 기능을 넣을 수 있게 도와주는 도화지 느낌S
      appBar: AppBar(
        title: Text('ByeJyuJi'),   //text와 관련된 디자인적 기능을 담은 위젯.
        centerTitle: true,         //가운데 정렬
        backgroundColor: Colors.redAccent,  //배경색
        elevation: 0.0,  //높이

      ),

      body: Center(            //가로축 정
        child: Column(         //중요하다 이거
            mainAxisAlignment: MainAxisAlignment.center,    //세로축 정렬(상단 중단 하단)
            children: [
              Text('맹'),
              Text('정'),
              Text('조')
            ],
          ),
      ),
      );

  }
}
  
  
  
  
  
 ㅡ,,ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ
 
 import 'package:flutter/material.dart';
void main() => runApp(MyApp());
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false, //우측 상단 빨간 띠를 없애
      title: '바이쥬직회사',
      home: Grade(),   //
    );
  }
}
class Grade extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.white,
      appBar: AppBar(
        title: Text('바이쥬지'),
        backgroundColor: Colors.redAccent,
        centerTitle: true,
        elevation: 0.0,
      ),
      body: Padding(
        padding: EdgeInsets.fromLTRB(30.0, 40.0, 0.0, 0.0),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start, //가로 혹은 세로로 자운데 정렬
          children: [
            Center(
              child: CircleAvatar(
                backgroundImage: AssetImage('image/BJJ.jpg'), //이미지 호출 
                radius: 80.0,
              ),
            ),
            Divider(             // 공간 나누는 선 두두등장
              height: 60.0,      // 선의 위아래 합친 길이가 60이라는
              color: Colors.grey[900],
              thickness: 0.5,    //선 굵기
              endIndent: 30.0,   //side에서 부터 얼마나 떨어져있나
            ),
            Text('name',
            style: TextStyle(
              color: Colors.red,
              letterSpacing: 2.0
            ),
            ),
            SizedBox(
              height: 10.0,
            ),
            Text('ByeJyuJi',
            style: TextStyle(
              color: Colors.red,
              letterSpacing: 2.0,
              fontSize: 28.0,
              fontWeight: FontWeight.bold
            ),),
            SizedBox(
              height: 50.0,
            ),
            Text('Selected by',
              style: TextStyle(
                  color: Colors.red,
                  letterSpacing: 2.0
              ),
            ),
            SizedBox(
              height: 10.0,
            ),
            Text('Forbes',
              style: TextStyle(
                  color: Colors.red,
                  letterSpacing: 2.0,
                  fontSize: 28.0,
                  fontWeight: FontWeight.bold
              ),
            ),
            SizedBox(
              height: 30.0,
            ),
            Row(
              children: [
                Icon(Icons.check_circle_outline),
                Text('SJCE OlHAEui Giup',
                style: TextStyle(
                  fontSize: 16.0,
                  letterSpacing: 1.0
                ),)
              ],
            ),
            SizedBox(
              height: 20.0,
            ),
            Row(
              children: [
                Icon(Icons.check_circle_outline),
                Text('Promising Corp.',
                  style: TextStyle(
                      fontSize: 16.0,
                      letterSpacing: 1.0
                  ),)
              ],
            ),
            SizedBox(
              height: 20.0,
            ),
            Row(
              children: [
                Icon(Icons.check_circle_outline),
                Text('SexSexBo',
                  style: TextStyle(
                      fontSize: 16.0,
                      letterSpacing: 1.0
                  ),)
              ],
            ),
            Center(

              child: CircleAvatar(
                backgroundImage: AssetImage('image/JyuJipet.jpeg'),
                radius:  60.0,
                backgroundColor: Colors.grey
              ),
            ),

        ],
      ),
    ),
    );

  }
}