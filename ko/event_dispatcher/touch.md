## Touch Events
__Touch events__ 는 모마일 게임에 중요한 이벤트이다. 터치 이벤트는 쉽게 만들 수 있고 다양한 기능을 제공한다. 터치 이벤트에 대해 확실히 알아 둡시다. 모바일 장치의 화면을 터치하면 터치를 수락하고 터치 한 위치를 확인한 다음 터치 한 내용을 결정한다. 그런 다음 터치에 응답합니다. 당신이 터치한 것은 응답하는 대상이 아니라 그 아래에 있을 수도 있다. 터치 이벤트에는 일반적으로 우선 순위가 지정되며 우선 순위가 가장 높은 이벤트는 응답하는 이벤트이다. 기본 터치 이벤트 리스너를 만드는 방법은 다음과 같다:

{% codetabs name="C++", type="cpp" -%}
//  원 터치 이벤트 리스너 만들기
// (한번에 한 터치만 처리된다.)
auto listener1 = EventListenerTouchOneByOne::create();

// 누를 때 동작.
listener1->onTouchBegan = [](Touch* touch, Event* event){
    // your code
    return true; // if you are consuming it
};

// 누른 상태로 움직일 때 동작.
listener1->onTouchMoved = [](Touch* touch, Event* event){
    // your code
};

// 화면에서 손을 띄었을 때 동작.
listener1->onTouchEnded = [=](Touch* touch, Event* event){
    // your code
};

// Add listener
_eventDispatcher->addEventListenerWithSceneGraphPriority(listener1, this);
{%- endcodetabs %}

보시다시피 터치 이벤트 리스너를 사용할 때 행동을 나타내는 3 가지 이벤트가 있다. 그 이벤트는 각 각 호출되는 시점이 다르다.

__onTouchBegan__ 은 터치를 시작할 때 동작한다.

__onTouchMoved__ 는 터치를 한 상태로 움직일 때 동작한다.

__onTouchEnded__ 는 터치를 종료하는 시점에서 동작한다.