## Actions
화면에 `장면`을 만들고 `스프라이트` 객체를 추가하는 것은 우리에게 해야할 한 부분이다. 게임을 게임답게 하려면 움직이는 것들이 필요하다. `액션` 객체는 게임에 필수적인 요소이다. __액션__은 `노드` 객체를 시공간에서 변화를 줄 수 있다. `스프라이트`를 한 `점`에서 다른 점으로 옮기고 완료되면 콜백을 사용할 수 있는가? 물론이다! `노드`에서 수행할 항목을 `액션`의 `시퀀스`로 만들 수 있다. 위치, 회전, 스케일과 같은 `노드` 속성을 변경할 수 있다. 액션의 예: `움직임`, `회전`, `스케일`. 모든 게임에서 __액션__을 사용한다. 

[샘플 코드](https://github.com/chukong/programmers-guide-samples)를 살펴보자.

이 장에서는, 작업 중인 __액션__있다:

![](basic_concepts-img/2n_level1_action_start.png "")

5초 뒤에 스프라이트는 새로운 위치로 옮겨질 것이다:

![](basic_concepts-img/2n_level1_action_end.png "")

`액션` 객체는 쉽게 만들 수 있다.

{% codetabs name="C++", type="cpp" -%}
auto mySprite = Sprite::create("Blue_Front1.png");

// moveBy : 현재 좌표에서 주어진 값만큼 이동.
// 2초 동안 스트라이트를 오른쪽으로 50 픽셀, 위로 10 픽셀 옮긴다.
auto moveBy = MoveBy::create(2, Vec2(50,10));
mySprite->runAction(moveBy);

// moveTo : 지정한 좌표로 이동.
// 2초 동안 스트라이트를 지정한 위치로 옮긴다.
auto moveTo = MoveTo::create(2, Vec2(50,10));
mySprite->runAction(moveTo);
{%- endcodetabs %}
