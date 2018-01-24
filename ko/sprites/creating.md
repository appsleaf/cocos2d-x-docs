## Sprites 만들기
필요에 따라 여러가지 방법으로 sprite 를 만들 수 있습니다. __PNG__, __JPEG__, __TIFF__ 등을 포함한 다양한 그래픽 포맷의 이미지로부터 `스프라이트` 를 만들 수 있다. 몇 가지 방법을 통해 메소드를 생성하고 각각에 대해 이야기 해 보자.

### 스프라이트 만들기
`스프라이트` 사용할 이미지 파일을 지정해서 만들 수 있다

{% codetabs name="C++", type="cpp" -%}
auto mySprite = Sprite::create("mysprite.png");
{%- endcodetabs %}

![](sprites-img/i1.png "")

위의 그림은 __mysprite.png__ 를 이용해서 `Sprite` 를 만들었다. 전체 이미지를 사용해 `스프라이트` 를 만든 결과이다. `Sprite` 는 __mysprite.png__ 와 크기가 같다. 만약 이미지 파일 크기가 200 x 200 라면 `Sprite` 도 200 x 200 로 같은 결과를 나타낸다.

### 사각형이 있는 스프라이트 만들기

앞에 예제에서, 만들어진 `Sprite` 는 원본 이미지 파일의 크기와 동일하다. `Sprite` 가 이미지 파일의 특정 부분만으로 만들어지길 원한다면, `Rect` 를 지정하면 된다.

`Rect` 는 4개의 값을 갖는다: __원본 x__, __원본 y__, __폭__ 과 __높이__

{% codetabs name="C++", type="cpp" -%}
auto mySprite = Sprite::create("mysprite.png", Rect(0,0,40,40));
{%- endcodetabs %}

![](sprites-img/i4.png "")

`Rect` 은 왼쪽 위 모서리에서 시작한다. 이는 왼쪽 밑 모서리에서 시작하는 화면 위치 레이아웃과 정반대이다. 따라서 결과로 나오는 `Sprite` 는 이미지 파일의 일부분이다. 이 경우 `Sprite` 의 크기는 왼쪽 위 모서리부터 시작하여 40x40 이다. 

만약 `Rect` 을 지정하지 않으면, Cocos2d-x 는 자동으로 지정된 이미지의 폭과 높이의 전체를 사용한다. 아래 예를 살펴보자. 만약 200 x 200 크기의 이미지를 사용한다면, 다음의 2개의 명령문은 동일한 결과를 갖는다.

{% codetabs name="C++", type="cpp" -%}
auto mySprite = Sprite::create("mysprite.png");

auto mySprite = Sprite::create("mysprite.png", Rect(0,0,200,200));
{%- endcodetabs %}
