## Logging as a way to output messages
때때로 앱이 실행 중일 때 정보 또는 디버그 목적으로 콘솔에 메시지가 기록되는 것을 보고 싶을 수 있다. 엔진에 내장된 __log()__ 를 이용하면 된다. 

예:

{% codetabs name="C++", type="cpp" -%}
// a simple string
log("This would be outputted to the console");

// a string and a variable
string s = "My variable";
log("string is %s", s);

// a double and a variable
double dd = 42;
log("double is %f", dd);

// an integer and a variable
int i = 6;
log("integer is %d", i);

// a float and a variable
float f = 2.0f;
log("float is %f", f);

// a bool and a variable
bool b = true;
if (b == true)
    log("bool is true");
else
    log("bool is false");
{%- endcodetabs %}

그리고 c++ 사용자는 __log()__ 대신에 __std::count__ 를 사용하는 것이 더 좋다. 하지만 __log()__ 가 복잡한 출력 형태를 쉽게 제공할 수 있다.