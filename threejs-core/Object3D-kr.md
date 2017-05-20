Object3D

이것은 three.js의 대부분의 객체에 대한 기본 클래스이며 3D 공간에서 객체를 조작하기위한 속성 및 메서드 집합을 제공합니다. 

이것은 오브젝트를 자식으로 추가하는 .add (object) 메소드를 통해 오브젝트를 그룹화하는 데 사용할 수 있지만 이 경우 Group 을 사용하는 것이 더 좋습니다 .
건설자

Object3D ()

생성자는 인수를 취하지 않습니다.
등록 정보

# . castShadow

객체가 그림자 맵으로 렌더링되는지 여부입니다. 기본값은 false 입니다.
# . children

오브젝트의 자식을 가지는 배열. 수동으로 그룹화하는 개체에 대한 정보는 그룹 을 참조하십시오 .
# . frustumCullled

이 값을 설정하면 객체를 렌더링하기 전에 객체가 카메라의 절두체 내에 있는지 모든 프레임을 검사합니다. 그렇지 않으면 객체가 보이지 않더라도 모든 프레임이 렌더됩니다. 기본값은 true 입니다.
# . 신분증

readonly -이 객체 인스턴스의 고유 번호입니다.
# . isObject3D

이 클래스 나 파생 클래스가 Object3D인지 확인하는 데 사용됩니다. 기본값은 true 입니다. 

최적화를 위해 내부적으로 사용되므로이 값을 변경하면 안됩니다.
# . layers

객체의 레이어 멤버십입니다. 객체는 사용중인 카메라 와 공통된 레이어가 하나 이상있는 경우에만 표시됩니다 .
# . 매트릭스

로컬 변환 행렬입니다.
# . matrixAutoUpdate

이 값을 설정하면 위치, 행렬 (회전 또는 쿼터니언) 및 모든 프레임의 크기를 계산하고 matrixWorld 속성도 다시 계산합니다. 기본값은 Object3D.DefaultMatrixAutoUpdate (true)입니다.
# . matrixWorld

객체의 전역 변환입니다. Object3D에 부모가 없으면 로컬 변환 .matrix와 동일 합니다.
# . matrixWorldNeedsUpdate

이 값을 설정하면 해당 프레임에서 matrixWorld를 계산하고이 속성을 false로 다시 설정합니다. 기본값은 false 입니다.
# . modelViewMatrix

이것은 셰이더에 전달되어 객체의 위치를 ​​계산하는 데 사용됩니다.
# . 이름

개체의 선택적 이름입니다 (고유 할 필요는 없음). 기본값은 빈 문자열입니다.
# . 정상 매트릭스

이것은 셰이더에 전달되어 객체의 조명을 계산하는 데 사용됩니다. 이 object의 modelViewMatrix의 좌상 3 × 3 부분 행렬의 역행렬입니다. 

이 특별한 매트릭스의 이유는 단순히 modelViewMatrix를 사용하면 비 단위 길이의 법선 (스케일링) 또는 수직이 아닌 방향 (비 균일 스케일링)이 생길 수 있기 때문입니다. 

반면에 modelViewMatrix의 번역 부분은 법선 계산과 관련이 없습니다. 따라서 Matrix3으로 충분합니다.
# . onAfterRender

Object3D가 렌더링 된 직후에 실행되는 선택적 콜백입니다. 이 함수는 renderer, scene, camera, geometry, material, group 매개 변수로 호출됩니다.
# . onBeforeRender

Object3D가 렌더링되기 직전에 실행되는 선택적 콜백입니다. 이 함수는 renderer, scene, camera, geometry, material, group 매개 변수로 호출됩니다.
# . 부모의

씬 그래프 의 오브젝트의 부모 .
# . 위치

객체의 로컬 위치입니다.
# . 4 원

Quaternion 으로서의 객체의 로컬 회전 .
# . 수신 그림자

머티리얼이 그림자를 받는지 여부입니다. 기본값은 false 입니다.
# . renderOrder

이 값은 불투명하고 투명한 오브젝트가 독립적으로 정렬 된 채로도 장면 그래프 오브젝트 의 기본 렌더링 순서를 겹쳐 쓸 수있게합니다 . 정렬은 가장 낮은 renderOrder에서 가장 높은 renderOrder입니다. 기본값은 0 입니다.
# . 회전

객체의 로컬 회전 ( 오일러 각 참조 ) ( 라디안 단위)입니다.
# . 규모

객체의 로컬 # . 규모 . 기본값은 Vector3 (1, 1, 1)입니다.
# . 쪽으로

예를 들어, 결과의 방향을 결정하기 위해서, lookAt 메소드 에 의해 사용됩니다 . 
기본값은 Object3D.DefaultUp - 즉 (0, 1, 0)입니다.
# . 사용자 데이터

Object3D에 대한 사용자 정의 데이터를 저장하는 데 사용할 수있는 객체입니다. 기능에 대한 참조는 복제되지 않으므로 보유하지 않아야합니다.
# . uuid

이 객체 인스턴스의 UUID 입니다. 이것은 자동으로 할당되므로 편집해서는 안됩니다.
# . 명백한

true이면 객체가 렌더링됩니다 . 기본값은 true 입니다.
정적 속성

정적 속성 및 메서드는 해당 클래스의 인스턴스가 아닌 클래스별로 정의됩니다. 즉, Object3D.DefaultUp 또는 Object3D.DefaultMatrixAutoUpdate 를 변경하면 변경된 후에 만들어진 Object3D (또는 파생 클래스)의 모든 인스턴스에 대해 up 및 matrixAutoUpdate 값이 변경 됩니다. 이미 생성 된 Object3D는 영향을받지 않습니다.
# . DefaultUp

디폴트 업 도의 디폴트 위치로서 이용 객체 방향 DirectionalLight , HemisphereLight 과 스포트 라이트 (위에서 아래 빛나는 라이트를 생성). 
기본적으로 (0, 1, 0)으로 설정하십시오.
# . DefaultMatrixAutoUpdate

새로 생성 된 Object3D 에 대한 matrixAutoUpdate 의 기본 설정입니다 .
행동 양식

EventDispatcher 메서드는이 클래스에서 사용할 수 있습니다.

# . 추가 ( 객체 , ...)

이 객체의 자식 객체 를 추가합니다 . 임의의 수의 오브젝트가 추가 될 수 있습니다. 수동으로 그룹화하는 개체에 대한 정보는 그룹 을 

참조하십시오 .
# . applyMatrix ( 행렬 )

행렬로 위치, 회전 및 크기를 업데이트합니다.
# . 복제 ( 재귀 적 )

재귀 적 - true의 경우, 오브젝트의 자손도 복제됩니다. 기본값은 true입니다. 

이 오브젝트의 복제를 돌려 주어, 옵션으로 모든 자손을 돌려줍니다.
# . 복사 ( 객체 , 재귀 )

recursive - true의 경우, 오브젝트의 자손도 카피됩니다. 기본값은 true입니다. 

지정된 객체를이 객체에 카피합니다.
# . getObjectById ( id )

id - 객체 인스턴스의 고유 번호 

객체의 하위 객체를 검색하고 일치하는 ID가있는 첫 번째 객체를 반환합니다. 
ID는 1, 2, 3, ...의 순서로 할당됩니다. 각 새로운 객체마다 1 씩 증가합니다.
# . getObjectByName ( name )

name - 아이의 Object3D.name property와 일치하는 캐릭터 라인 

객체의 자식을 검색하여 일치하는 이름을 가진 첫 번째 객체를 반환합니다. 
대부분의 객체에서 # . name 은 기본적으로 빈 문자열입니다. 이 방법을 사용하려면 수동으로 설정해야합니다.
# . getObjectByProperty ( 이름 , 값 )

name - 검색하는 프롭퍼티 명 
value - 지정된 프로퍼티의 값 

오브젝트의 아이를 검색해, 지정된 값에 일치하는 프로퍼티를 최초로 돌려줍니다.
# . getWorldPosition ( 옵션 타겟 )

optionalTarget - 결과를 설정하기위한 타겟 (옵션). 그렇지 않으면 새 Vector3 이 인스턴스화됩니다. 

월드 공간에서 객체의 위치를 ​​나타내는 벡터를 반환합니다.
# . getWorldQuaternion ( optionalTarget )

optionalTarget - (선택 사항) 지정되면 결과가이 Quaternion으로 복사되고, 그렇지 않으면 새로운 Quaternion이 생성됩니다. 

월드 공간에서 객체의 회전을 나타내는 쿼터니언을 반환합니다.
# . getWorldRotation ( 옵션 타겟 )

optionalTarget - (선택 사항) 지정되면 결과가이 오일러에 복사되고 그렇지 않으면 새 오일러가 생성됩니다. 

월드 공간에서 물체의 회전을 나타내는 오일러 각을 반환합니다.
# . getWorldScale ( optionalTarget )

optionalTarget - (선택 사항) 지정된 경우 결과가 Vector3에 복사되고, 그렇지 않으면 새 Vector3이 만들어집니다. 

월드 공간의 각 축에 대해 객체에 적용된 배율 인수의 벡터를 반환합니다.
# . getWorldDirection ( optionalTarget )

optionalTarget - (선택 사항) 지정된 경우 결과가 Vector3에 복사되고, 그렇지 않으면 새 Vector3이 만들어집니다. 

월드 공간에서 객체의 양의 z 축 방향을 나타내는 벡터를 반환합니다.
# . localToWorld ( 벡터 )

vector - 로컬 (객체) 공간의 위치를 ​​나타내는 벡터입니다. 

벡터를 로컬 공간에서 월드 공간으로 변환합니다.
# . lookAt ( 벡터 )

vector - 월드 공간에서 위치를 나타내는 벡터. 

세계 공간에서 한 점을 향하도록 개체를 회전합니다.
# . raycast ( raycaster , intersects )

캐스트 된 광선과이 객체 사이의 교차를 가져 오는 추상 (빈) 메서드입니다. 메쉬 , 선 및 점 과 같은 하위 클래스는 레이 캐스팅 을 사용하기 위해이 메서드를 구현합니다.
# . 제거 ( 객체 , ...)

이 object의 아이로서 object 를 삭제합니다 . 임의의 수의 오브젝트가 제거 될 수 있습니다.
# . rotateOnAxis ( 축 , 각도 )

axis - 객체 공간에서 정규화 된 벡터입니다. 
angle - 라디안 단위의 각도. 

객체 공간에서 축을 따라 객체를 회전합니다. 축은 정규화 된 것으로 가정합니다.
# . rotateX ( rad )

rad - 라디안으로 회전 할 각도. 

로컬 공간에서 x 축을 중심으로 객체를 회전합니다.
# . rotateY ( rad )

rad - 라디안으로 회전 할 각도. 

로컬 공간에서 y 축을 중심으로 객체를 회전합니다.
# . rotateZ ( rad )

rad - 라디안으로 회전 할 각도. 

로컬 공간에서 z 축을 중심으로 객체를 회전합니다.
# . setRotationFromAxisAngle ( 축 , 각도 )

axis - 객체 공간에서 정규화 된 벡터입니다. 
각도 - 각도 (라디안)가 

호출 setFromAxisAngle ( 축 , 각도 상의) .quaternion을 .
# . setRotationFromEuler ( 오일러 )

euler - 회전 량을 지정하는 오일러 각입니다. 
호출 setRotationFromEuler ( 오일러 온) .quaternion을 .
# . setRotationFromMatrix ( m )

m - 행렬의 회전 성분으로 쿼터니온을 회전합니다. 
호출 setFromRotationMatrix ( m은 )이에 .quaternion . 

이것은 m의 상위 3x3이 순수 회전 행렬 (즉, 스케일되지 않음)이라고 가정합니다.
# . setRotationFromQuaternion ( q )

q - 표준화 된 쿼터니온. 

주어진 쿼터니온을 쿼터니언 으로 복사하십시오 .
# . toJSON ( q )

개체를 JSON 형식으로 변환하십시오.
# . translateOnAxis ( 축 , 거리 )

axis - 객체 공간에서 정규화 된 벡터입니다. 
distance - 번역 할 거리입니다. 

오브젝트 공간에서 축을 따라 거리별로 오브젝트를 변환합니다. 축은 정규화 된 것으로 가정합니다.
# . translateX ( 거리 )

거리 단위로 x 축을 따라 객체를 평행 이동 합니다.
# . translateY ( 거리 )

거리 단위로 y 축을 따라 객체를 평행 이동 시킵니다.
# . translateZ ( 거리 )

거리 단위로 z 축을 따라 객체를 평행 이동 합니다.
# . 트래버스 ( 콜백 )

callback - 첫 번째 인수로 object3D 객체를 갖는 함수. 

이 객체 및 모든 자손에 대한 콜백을 실행합니다.
# . traverseVisible ( 콜백 )

callback - 첫 번째 인수로 object3D 객체를 갖는 함수. 

트래버스처럼, 콜백은 보이는 객체들에 대해서만 실행될 것입니다. 보이지 않는 객체의 자손은 가로 지르지 않습니다.
# . traverseAncestors ( 콜백 )

callback - 첫 번째 인수로 object3D 객체를 갖는 함수. 

모든 조상에 콜백을 실행합니다.
# . updateMatrix ()

로컬 변환을 업데이트하십시오.
# . updateMatrixWorld ( force )

오브젝트와 그 아이의 글로벌 변환을 갱신합니다.
# . worldToLocal ( 벡터 )

벡터 - 세계 벡터입니다. 

벡터를 월드 공간에서 로컬 공간으로 업데이트합니다.
출처

src / core / Object3D.js