벡터 3

3D 벡터를 나타내는 클래스. 3D 벡터는 다음과 같은 여러 가지를 나타내는 데 사용할 수있는 숫자의 정렬 된 삼중 항입니다 (x, y 및 z로 표시됨).
3D 공간의 한 점.
3D 공간에서의 방향과 길이. three.js에서 길이는 항상 (0, 0, 0)에서 (x, y, z)까지의 유클리드 거리 (직선 거리)이고 방향은 (0, 0, 0)에서 x, y, z)를 포함한다.
임의로 정렬 된 임의의 숫자.
운동량 벡터와 같은 3D 벡터를 사용하여 표현할 수있는 다른 것들이 있지만, 이것들은 three.js에서 가장 보편적으로 사용됩니다.
예

var a = new THREE.Vector3 (0, 1, 0);

// 인수가 없습니다. (0, 0, 0)으로 초기화됩니다.
var b = new THREE.Vector3 ();

var d = a.distanceTo (b);
건설자

벡터 3 (x, y, z)

x - 벡터의 x 값 기본값은 0입니다.
y - 벡터의 y 값 기본값은 0입니다.
z - 벡터의 z 값 기본값은 0입니다.

새 Vector3을 만듭니다.
등록 정보

# .isVector3

이 클래스 나 파생 클래스가 Vector3인지 여부를 확인하는 데 사용됩니다. 기본값은 true입니다.

최적화를 위해 내부적으로 사용되므로이 값을 변경하면 안됩니다.
# .x

# .y

# .z

행동 양식

# .add (v)

Vector에 v를 더합니다.
# .addScalar (s)

이 벡터의 x, y 및 z 값에 스칼라 값 s를 더합니다.
# .addScaledVector (v, s)

이 벡터에 v와 s의 배수를 더합니다.
# .addVectors (a, b)

이 벡터를 a + b로 설정합니다.
# .applyAxisAngle (축, 각도)

axis - 정규화 된 Vector3입니다.
angle - 라디안 단위의 각도.

축으로 지정된 회전과 벡터에 각도를 적용합니다.
# .applyEuler (오일러)

Euler 객체를 Quaternion으로 변환하고 적용하여이 벡터에 오일러 변형을 적용합니다.
# .applyMatrix3 (m)

이 벡터에 m을 곱합니다.
# .applyMatrix4 (m)

이 벡터 (4 차원에서 암시적인 1을 가짐)와 m을 곱해서 원근법으로 나눕니다.
# .applyQuaternion (quaternion)

이 벡터에 쿼터니언 변환을 적용합니다.
# .angleTo (v)

이 벡터와 벡터 v 사이의 각도를 라디안 단위로 반환합니다.
# .ceil ()

벡터의 x, y 및 z 구성 요소는 가장 가까운 정수 값으로 반올림됩니다.
# .clamp (최소, 최대)

min - 최소 x, y 및 z 값
max - 원하는 범위의 최대 x, y 및 z 값

이 벡터의 x, y 또는 z 값이 최대 벡터의 x, y 또는 z 값보다 큰 경우 해당 값으로 대체됩니다.

이 벡터의 x, y 또는 z 값이 최소 벡터의 x, y 또는 z 값보다 작 으면 해당 값으로 대체됩니다.
# .clampLength (최소, 최대)

min - 길이가 클램프되는 최소치
max - 길이가 클램프되는 최대치

이 벡터의 길이가 최대 값보다 큰 경우 최대 값으로 대체됩니다.

이 벡터의 길이가 최소값보다 작 으면 min 값으로 대체됩니다.
# .clampScalar (최소, 최대)

min - 컴퍼넌트가 클램프되는 최소치
max - 컴퍼넌트가 클램프되는 최대치

이 벡터의 x, y 또는 z 값이 최대 값보다 큰 경우 최대 값으로 대체됩니다.

이 벡터의 x, y 또는 z 값이 최소값보다 작 으면 min 값으로 대체됩니다.
# .clone ()

이 벡터와 동일한 x, y 및 z 값을 가진 새 vector3을 반환합니다.
# .copy (v)

전달 된 vector3의 x, y 및 z 속성 값을 Vector3에 복사합니다.
# .cross (v)

이 벡터가 자신과 v의 곱을 교차하도록 설정합니다.
# .crossVectors (a, b)

이 벡터를 a와 b의 곱을 교차하도록 설정합니다.
#. 거리 toTo (v)

이 벡터로부터 v까지의 거리를 계산합니다.
#. 거리 toManhattan (v)

이 벡터에서 v까지의 맨하탄 거리를 계산합니다.
# .distanceToSquared (v)

이 벡터에서 v까지의 제곱 거리를 계산합니다. 거리를 다른 거리와 단순히 비교하는 경우 거리를 제곱 한 값을 비교하는 것이 약간 더 효율적이므로 계산해야합니다.
# .divide (v)

이 벡터를 v로 나눕니다.
# .divideScalar (s)

이 벡터를 스칼라로 나눕니다.
* s = 0 * 인 경우 벡터를 (0, 0)으로 설정합니다.
# .dot (v)

이 벡터와 v의 내적을 계산하시오.
# .equals (v)

이 벡터와 v의 완전한 동일성을 검사합니다.
# .floor ()

벡터의 구성 요소는 가장 가까운 정수 값으로 내림됩니다.
# .fromArray (array, offset)

array - 소스 배열
offset - 배열에의 오프셋 (옵션). 기본값은 0입니다.

이 벡터의 x 값을 array [offset + 0], y 값을 array [offset + 1]로, z 값을 array [offset + 2]로 설정합니다.
# .fromBufferAttribute (attribute, index)

attribute - 소스 속성
index - 속성의 인덱스

이 벡터의 x, y 및 z 값을 특성에서 설정합니다.
# .getComponent (index)

index - 0, 1 또는 2

index가 0이면 x 값을 반환합니다.
index가 1이면 y 값을 반환합니다.
index가 2이면 z 값을 반환합니다.
# .길이 ()

유클리드 길이 (직선 길이)를 (0, 0, 0)에서 (x, y, z)까지 계산합니다.
# .lengthManhattan ()

이 벡터의 맨하탄 길이를 계산합니다.
# .lengthSq ()

(0, 0, 0)에서 (x, y, z)까지 유클리드 길이 (직선 길이)의 제곱을 계산합니다. 벡터의 길이를 비교하는 경우 계산에 약간 더 효율적이므로 길이의 제곱을 비교해야합니다.
# .lerp (v, alpha)

v - 향해 보간 할 Vector3
알파 - 닫힌 간격 [0, 1]의 보간 인자.

이 벡터와 v 사이를 선형 적으로 보간합니다. 여기서 알파는 라인을 따라있는 거리입니다. - 알파 = 0이이 벡터가 될 것이고, 알파 = 1은 v가됩니다.
# .lerpVectors (v1, v2, alpha)

v1 - 시작 Vector3.
v2 - 향해 보간 할 Vector3
알파 - 닫힌 간격 [0, 1]의 보간 인자.

이 벡터를 v1과 v2 사이에서 선형 보간 된 벡터로 설정합니다. 여기서 alpha는 두 벡터를 연결하는 선을 따른 거리입니다. 즉, alpha = 0은 v1이고 alpha는 1이 v2가됩니다.
# .negate ()

이 벡터를 반전합니다. 즉, x = -x, y = -y 및 z = -z로 설정합니다.
# .normalize ()

이 벡터를 단위 벡터로 변환합니다. 즉,이 벡터와 같은 방향이지만 길이가 1 인 벡터와 동일하게 설정합니다.
# .max (v)

이 벡터의 x, y 또는 z 값이 v의 x, y 또는 z 값보다 작 으면 해당 값을 해당 최대 값으로 바꿉니다.
# .min (v)

이 벡터의 x, y 또는 z 값이 v의 x, y 또는 z 값보다 큰 경우 해당 값을 해당 최소값으로 바꿉니다.
# .multiply (v)

이 벡터에 v를 곱합니다.
# .multiplyScalar (s)

이 벡터에 스칼라를 곱합니다.
#. 다중 벡터 (a, b)

이 벡터를 a x b와 동일하게 설정합니다.
# .project (camera)

카메라 - 투영에 사용할 카메라.

카메라로 벡터를 투사합니다.
# .projectOnPlane (planeNormal)

planeNormal - 평면 법선을 나타내는 벡터입니다.

이 벡터로부터 평면의 법선에 투영 된이 벡터를 빼서이 벡터를 평면에 투영합니다.
# .projectOnVector (Vector3)

이 벡터를 다른 벡터에 투영합니다.
# .reflect (일반)

normal - 반 사면의 법선

평행선과 수직 인 평면으로부터 벡터를 반사시킵니다. 보통은 단위 길이를 가진 것으로 가정합니다.
# .round ()

벡터의 구성 요소는 가장 가까운 정수 값으로 반올림됩니다.
# .roundToZero ()

벡터의 구성 요소는 정수 값으로 0으로 반올림됩니다 (음수 인 경우 위로, 양수인 경우 아래로).
# .set (x, y, z)

이 벡터의 x, y 및 z 구성 요소를 설정합니다.
# .setComponent (index, value)

index - 0, 1 또는 2
value - 부동

index가 0이면 x를 value로 설정하십시오.
index가 1이면 y를 value로 설정하십시오.
index가 2이면 z를 value로 설정합니다.
# .setFromCylindrical (c)

이 벡터를 원통형 좌표로 설정합니다. c.
# .setFromMatrixColumn (matrix, index)

이 벡터의 x, y 및 z를 인덱스로 지정된 행렬의 열에 동일하게 설정합니다.
# .setFromMatrixPosition (m)

이 벡터를 변환 행렬 m의 위치 요소로 설정합니다.
# .setFromMatrixScale (m)

이 벡터를 변환 행렬 m의 스케일 요소로 설정합니다.
# .setFrom 구면

구형 좌표 s로부터이 벡터를 설정합니다.
# .setLength (l)

이 벡터를이 벡터와 같은 방향이지만 길이가 l 인 벡터로 설정합니다.
# .setScalar (스칼라)

이 벡터의 x, y 및 z 값을 모두 스칼라로 설정합니다.
# .setX (x)

이 벡터의 x 값을 x로 대체합니다.
# .setY (y)

이 벡터의 y 값을 y로 바꿉니다.
# .setZ (z)

이 벡터의 z 값을 z로 바꿉니다.
# .sub (v)

이 벡터에서 v를 뺍니다.
# .subScalar (s)

이 벡터의 x, y 및 z 구성 요소에서 s를 뺍니다.
#. 서브 벡터 (a, b)

이 벡터를 - b로 설정합니다.
# .toArray (배열, 오프셋)

array - (선택 사항) 벡터를 저장할 배열입니다. 이것이 제공되지 않으면 새로운 배열이 생성됩니다.
offset - (선택 사항) 선택적 오프셋 (offset)입니다.

배열 [x, y, z]를 반환하거나 제공된 배열에 x, y 및 z를 복사합니다.
# .transformDirection (m)

이 벡터의 방향을 행렬 (왼쪽 위의 3 x 3 부분 집합)으로 변환 한 다음 결과를 정규화합니다.
# .unproject (camera)

카메라 - 투영에 사용할 카메라.

카메라의 투영 행렬로 벡터를 비춘다.
출처

src / math / Vector3.js