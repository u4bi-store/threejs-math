Matrix4

4x4 행렬을 나타내는 클래스입니다.

3D 컴퓨터 그래픽에서 4x4 매트릭스의 가장 일반적인 용도는 변환 매트릭스입니다. WebGL에서 사용되는 변환 행렬에 대한 소개는이 자습서를 확인하십시오.

이렇게하면 3D 공간의 한 점을 나타내는 Vector3에 행렬을 곱하여 이동, 회전, 전단, 크기 조절, 반사, 직각 또는 원근 투영 등의 변형을 적용 할 수 있습니다. 이것은 행렬을 벡터에 적용하는 것으로 알려져 있습니다.

모든 Object3D에는 3 개의 연관된 Matrix4가 있습니다.
Object3D.matrix : 객체의 로컬 변환을 저장합니다.
Object3D.matrixWorld : 오브젝트의 글로벌 또는 월드 변환입니다. 이것은 부모와 관련된 객체의 변형입니다. 객체에 부모가없는 경우는 로컬 변환과 동일합니다.
Object3D.modelViewMatrix : 이것은 카메라의 좌표계를 기준으로 한 객체의 변형을 나타냅니다. 객체의 modelViewMatrix는 객체의 matrixWorld에 미리 카메라의 matrixWorldInverse를 곱한 값입니다.
카메라에는 2 개의 추가 Matrix4가 있습니다.
Camera.matrixWorldInverse : 뷰 매트릭스 - 카메라의 matrixWorld의 역입니다.
Camera.projectionMatrix : 장면을 클립 공간에 투영하는 방법에 대한 정보를 나타냅니다.
참고 : Object3D.normalMatrix는 Matrix4가 아니라 Matrix3입니다.
행 주요 및 열 주요 주문에 대한 참고 사항

set () 메서드는 행 우선 순서로 인수를 취하고 내부적으로는 요소 배열에 열 주요 순서로 저장됩니다.

이것은 호출하는 것을 의미합니다.
var m = new Matrix4 ();

세트 (11, 12, 13, 14,
       21, 22, 23, 24,
       31, 32, 33, 34,
       41, 42, 43, 44); 다음을 포함하는 요소 배열이 생성됩니다.
요소 = [11, 21, 31, 41,
               12, 22, 32, 42,
               13, 23, 33, 43,
               14, 24, 34, 44]; 내부적으로 모든 계산은 컬럼 메이저 순서를 사용하여 수행됩니다. 그러나 실제 순서가 수학적으로 차이가 없으므로 대부분의 사람들은 행 주요 순서로 행렬을 생각하는 데 익숙하므로 3 행 .js 문서는 행 우선 순서로 행렬을 표시합니다. 소스 코드를 읽는다면 여기에 설명 된 행렬의 [link : https://en.wikipedia.org/wiki/Transpose transpose]를 사용하여 계산을 이해해야합니다.
건설자

Matrix4 ()

Matrix4를 4x4 단위 행렬로 생성하고 초기화합니다.
등록 정보

# .element

행렬 값의 열 - 주요 목록입니다.
# .isMatrix4

이 클래스 나 파생 클래스가 Matrix4인지 여부를 확인하는 데 사용됩니다. 기본값은 true입니다.

최적화를 위해 내부적으로 사용하므로이 값을 변경하면 안됩니다.
행동 양식

# .applyToBufferAttribute (속성)

attribute - 3D 벡터를 나타내는 float 속성입니다.

이 행렬을 속성의 모든 3D 벡터에 곱합니다 (적용).
# .clone ()

이 요소와 동일한 요소를 가지는 새로운 Matrix4를 작성합니다.
# .compose (position, quaternion, scale)

이 행렬을 position, quaternion 및 scale로 구성된 변환으로 설정합니다. 내부적으로 이것은 makeRotationFromQuaternion (quaternion)과 그 뒤에 scale (scale)을 호출 한 다음 마지막으로 setPosition (position)을 호출합니다.
# .copy (m)

행렬 m의 요소를이 행렬에 복사합니다.
# .copyPosition (m)

제공된 행렬 m의 변환 컴포넌트를이 행렬의 변환 컴포넌트로 복사합니다.
# .decompose (위치, 4 분의 1, 축척)

이 행렬을 위치, 쿼터니언 및 비율 구성 요소로 분해합니다.
# .determinant ()

이 행렬의 행렬식을 계산하여 리턴합니다.

여기에 설명 된 방법을 기반으로합니다.
#. 등가 (m)

이 행렬과 m가 동일한 경우는 true를 돌려줍니다.
# .extractBasis (xAxis, yAxis, zAxis)

제공된 행렬 벡터에이 행렬의 기초를 추출합니다. 이 행렬이 :
a, b, c, d,
e, f, g, h,
i, j, k, l,
m, n, o, p이면 xAxis, yAxis, zAxis는 다음과 같이 설정됩니다.
xAxis = (a, e, i)
yAxis = (b, f, j)
zAxis = (c, g, k)
# .extractRotation (m)

지정된 행렬 m의 회전 성분을이 행렬의 회전 성분에 추출합니다.
# .fromArray (array, offset)

array - 요소의 read 처의 배열
offset - 배열에의 오프셋 (옵션). 기본값은 0입니다.

열 (column) - 주 형식의 배열을 기반으로이 행렬의 요소를 설정합니다.
# .getInverse (m, throwOnDegenerate)

m - 역수를 취할 행렬
throwOnDegenerate - (선택 사항) true 인 경우 행렬이 축퇴 (역전이 아님) 인 경우 오류를 발생시킵니다.

여기에 설명 된 방법을 사용하여이 행렬을 전달 된 행렬 m의 역함수로 설정합니다. throwOnDegenerate가 설정되어 있지 않고 행렬이 반전되지 않으면 4x4 단위 행렬로 설정합니다.
# .getMaxScaleOnAxis ()

3 개의 축의 최대치를 취득합니다.
# .identity ()

이 행렬을 항등 행렬에 리 셋트합니다.
# .lookAt (눈, 중심, 위)

눈에서 중심으로 향한 회전 벡터를 위로 향한 회전 행렬을 만듭니다.
# .makeRotationAxis (축, 세타)

축 - 회전 축은 정규화되어야합니다.
theta - 라디안 단위의 회전 각도입니다.

이 행렬을 쎄타 라디안 단위로 축 주위의 회전 변환으로 설정합니다.
이것은 다소 논란의 여지가 있지만 Quaternions를 통해 회전하는 대신 수학적으로 건전한 대안입니다. 여기 토론을 참조하십시오.
# .makeBasis (xAxis, yAxis, zAxis)

이것을 세 개의 제공된 기본 벡터로 구성된 기본 행렬로 설정하십시오.
xAxis.x, yAxis.x, zAxis.x, 0,
xAxis.y, yAxis.y, zAxis.y, 0,
xAxis.z, yAxis.z, zAxis.z, 0,
0, 0, 0, 1
# .makePerspective (왼쪽, 오른쪽, 위쪽, 아래쪽, 가까운, 멀리)

투시 투영 행렬을 만듭니다. 이것은 PerspectiveCamera.updateProjectionMatrix ()에 의해 내부적으로 사용됩니다.
# .makeOrthographic (왼쪽, 오른쪽, 위, 아래, 가까운, 멀리)

직교 투영 행렬을 작성합니다. 이것은 OrthographicCamera.updateProjectionMatrix ()에 의해 내부적으로 사용됩니다.
# .makeRotationFromEuler (오일러)

이 행렬의 회전 성분 (좌상 3 × 3 행렬)을, 지정된 오일러 각으로 지정된 회전으로 설정합니다. 나머지 행렬은 ID로 설정됩니다. 오일러의 순서에 따라 6 가지 가능한 결과가 있습니다. 전체 목록은이 페이지를 참조하십시오.
# .makeRotationFromQuaternion (q)

이 행렬의 회전 성분을, q로 지정된 회전으로 설정합니다. 나머지 행렬은 ID로 설정됩니다. 따라서 q = w + xi + yj + zk가 주어지면 결과 행렬은 다음과 같습니다.
1-2y²-2z² 2xy-2zw 2xz-2yw 0
2xy + 2zw 1-2x² -2z² 2yz-2xw 0
2xz-2yw 2yz + 2xw 1-2x²-2y² 0
0 0 0 1
# .makeRotationX (theta)

theta - 라디안 단위의 회전 각도입니다.

이 행렬을 theta (θ) 라디안 단위로 X 축을 중심으로 회전 변환으로 설정합니다. 결과 행렬은 다음과 같습니다.
1 0 0 0
0 cos (θ) -sin (θ) 0
0 sin (θ) cos (θ) 0
0 0 0 1
# .makeRotationY (theta)

theta - 라디안 단위의 회전 각도입니다.

이 행렬을 θ 축 (θ) 라디안 단위로 Y 축을 중심으로 회전 변환으로 설정합니다. 결과 행렬은 다음과 같습니다.
cos (θ) 0 sin (θ) 0
0 1 0 0
- sin (θ) 0 cos (θ) 0
0 0 0 1
# .makeRotationZ (theta)

theta - 라디안 단위의 회전 각도입니다.

이 행렬을 Z 축을 중심으로 θ (라디안)만큼 회전 변환으로 설정합니다. 결과 행렬은 다음과 같습니다.
cos (θ) -sin (θ) 0 0
sin (θ) cos (θ) 0 0
0 0 1 0
0 0 0 1
# .makeScale (x, y, z)

x - X 축의 스케일 량
y - Y 축의 스케일의 크기
z - Z 축의 스케일 량

이 행렬을 스케일 변환으로 설정합니다.
x, 0, 0, 0,
0, y, 0, 0,
0, 0, z, 0,
0, 0, 0, 1
# .makeShear (x, y, z)

x - X 축에서 전단 할 양
y - Y 축에서 전단 할 양
z - Z 축에서 전단 할 양

이 행렬을 전단 변환으로 설정합니다.
1, y, z, 0,
x, 1, z, 0, z,
x, y, 1, 0,
0, 0, 0, 1
# .make 번역 (x, y, z)

x - X 축에서 변환 할 양.
y - Y 축에서 변환 할 양
z - Z 축으로 평행 이동하는 양

이 행렬을 변환 변환으로 설정합니다.
1, 0, 0, x,
0, 1, 0, y,
0, 0, 1, z,
0, 0, 0, 1

# .multiply (m)

사후 -이 행렬에 m을 곱합니다.
# .multiplyMatrices (a, b)

이 행렬을 x ​​b로 설정합니다.
# .multiplyScalar (s)

행렬의 모든 구성 요소에 스칼라 값을 곱합니다.
# .premultiply (m)

이 행렬에 m을 미리 곱합니다.
# .scale (v)

이 행렬의 열에 벡터 v를 곱합니다.
# .set (n11, n12, n13, n14, n21, n22, n23, n24, n31, n32, n33, n34, n41, n42, n43, n44)

이 행렬의 요소를 제공된 행 주요 값 n11, n12, ... n44로 설정하십시오.
# .setPosition (v)

나머지 행렬에 영향을주지 않고 벡터 v에서이 행렬에 대한 위치 구성 요소를 설정합니다. 즉 행렬이 현재 :
a, b, c, d,
e, f, g, h,
i, j, k, l,
m, n, o, p 이것은 다음과 같이됩니다 :
a, b, c, v.x,
e, f, g, v.y,
i, j, k, v.z,
m, n, o, p
# .toArray (배열, 오프셋)

array - 결과 벡터를 저장하는 (선택 사항) 배열.
offset - 결과를 배치 할 배열의 오프셋 (옵션).

이 행렬의 요소를 열 메이저 포맷의 배열에 기입합니다.
# .transpose ()

이 행렬을 조 변경합니다.
출처

src / math / Matrix4.js