쿼터니언

4 원의 구현. 이것은 다른 장점들 중에서도 두려운 짐벌 잠금 문제가 발생하지 않고 회전하는 데 사용됩니다.
예

var quaternion = new THREE.Quaternion ();
quaternion.setFromAxisAngle (새 THREE.Vector3 (0, 1, 0), Math.PI / 2);

var 벡터 = 새로운 THREE.Vector3 (1, 0, 0);
벡터 .applyQuaternion (quaternion);
건설자

쿼터니온 (x, y, z, w)

x - x 좌표
y - y 좌표
z - z 좌표
w - w 좌표
등록 정보

# .x

이 속성을 변경하면 onChangeCallback이 호출됩니다.
# .y

이 속성을 변경하면 onChangeCallback이 호출됩니다.
# .z

이 속성을 변경하면 onChangeCallback이 호출됩니다.
# .w

이 속성을 변경하면 onChangeCallback이 호출됩니다.
행동 양식

# .clone ()

동일한 x, y, z 및 w 속성을 가진 새 Quaternion을이 클래스에 만듭니다.
# .conjugate ()

이 4 원의 회전 공액을 구합니다. 쿼터니언의 켤레는 회전축을 중심으로 반대 방향으로 동일한 회전을 나타냅니다.
# .copy (q)

q의 x, y, z 및 w 속성을이 쿼터니언에 복사합니다.
# .equals (v)

v -이 쿼터니언을 비교할 쿼터니언.

v의 x, y, z 및 w 속성을이 쿼터니언의 동일한 속성과 비교하여 동일한 회전을 나타내는 지 확인합니다.
# .dot (v)

쿼터니온 v와 내적의 내적을 계산합니다.
# .fromArray (array, offset)

array - 쿼터니언을 구성하는 데 사용 된 형식 (x, y, z, w)의 배열.
offset - 배열에 대한 오프셋 (옵션).

이 쿼터니언의 x, y, z 및 w 속성을 배열에서 설정합니다.
# .inverse ()

이 4 원을 반전합니다 - 공액을 계산 한 다음 결과를 정규화합니다.
# .길이 ()

이 쿼터니언의 유클리드 길이 (직선 길이)를 4 차원 벡터로 간주하여 계산합니다.
# .lengthSq ()

이 쿼터니언의 유클리드 길이 (직선 길이)를 4 차원 벡터로 간주하여 계산합니다. 이것은 두 쿼터니온의 길이를 비교할 때 유용 할 수 있습니다. 이는 length ()보다 약간 더 효율적인 계산이기 때문입니다.
# .normalize ()

이 쿼터니언을 정규화합니다. 즉,이 회전과 동일한 회전을하지만 길이가 1 인 쿼터니언을 계산합니다.
# .multiply (q)

이 quaternion에 q를 곱합니다.
# .multiplyQuaternions (a, b)

이 쿼터니언을 x b로 설정합니다.
여기에 설명 된 방법에서 변경되었습니다.
# .onChange (onChangeCallback)

onChangeCallback () 메서드를 설정합니다.
# .onChangeCallback ()

이 함수는 다음 중 하나가 발생할 때마다 호출됩니다.
x, y, z 또는 w 속성이 변경됩니다.
set (), copy (), clone (), setFromAxisAngle (), setFromRotationMatrix (), conjugate (), normalize (), multiplyQuaternions (), slerp () 또는 fromArray () 함수가 호출됩니다.
setFromEuler () 함수는 update 인수를 true로 설정하여 호출됩니다.
기본적으로이 함수는 빈 함수이지만 onChange (onChangeCallback)를 사용하여 필요할 경우 변경할 수 있습니다.
# .primultiply (q)

이 쿼터니언을 q로 미리 곱합니다.
# .slerp (qb, t)

qb - 다른 쿼터니온 순환
t - 닫은 구간 [0, 1]의 보간 계수

쿼터니언 사이의 구형 선형 보간을 처리합니다. t는이 quaternion (여기서 t는 0 임)과 qb (여기서 t는 1 임) 사이의 회전 양을 나타냅니다. 이 쿼터니언은 결과로 설정됩니다. 또한 아래의 slerp 정적 버전을 참조하십시오.
// 대상 쿼터니언쪽으로 메쉬 회전
mesh.quaternion.slerp (endQuaternion, 0.01);
# .set (x, y, z, w)

이 Quaternion의 x, y, z, w 속성을 설정합니다.
# .setFromAxisAngle (축, 각도)

이 쿼터니온을 축과 각도로 지정된 회전에서 설정합니다.
여기에서 나온 방법에 맞게 수정되었습니다.
축은 정규화 된 것으로 가정하고 각도는 라디안 단위입니다.
# .setFromEuler (오일러)

오일러 각으로 지정된 회전에서이 쿼터니언을 설정합니다.
# .setFromRotationMatrix (m)

이 쿼터니온을 m의 회전 성분으로 설정합니다.
여기에서 나온 방법에 맞게 수정되었습니다.
# .setFromUnitVectors (vFrom, vTo)

이 쿼터니언을 방향 벡터 vFrom을 방향 벡터 vTo로 회전시키는 데 필요한 회전을 설정합니다.
여기에서 나온 방법에 맞게 수정되었습니다.
vFrom 및 vTo는 정규화 된 것으로 가정한다.
# .toArray (배열, 오프셋)

array - 쿼터니언을 저장하는 선택적 배열입니다. 지정하지 않으면 새 배열이 만들어집니다.
offset - (옵션) 지정된 경우 결과는이 Array에 복사됩니다.

이 Quaternion의 수치 요소를 [x, y, z, w] 형식의 배열로 돌려줍니다.
정적 메소드

정적 메서드 (인스턴스 메서드와 반대)는 특정 인스턴스가 아닌 클래스에서 직접 호출되도록 디자인되었습니다. 정적 버전을 사용하려면 다음과 같이 호출하십시오.
THREE.Quaternion.slerp (qStart, qEnd, qTarget, t); 반대로 '정상'또는 인스턴스 된 슬래프 메서드를 호출하려면 다음을 수행합니다.
// 기본값으로 쿼터니언을 인스턴스화합니다.
var q = new THREE.Quaternion ();

// 인스턴스 된 slerp 메서드를 호출합니다.
q.slerp (qb, t)
# .slerp (qStart, qEnd, qTarget, t)

qStart - 시작 쿼터니언 (여기서 t는 0 임)
qEnd - 끝나는 쿼터니온 (여기서 t는 1 임)
qTarget - 결과로 설정된 타겟 쿼터니언
t - 닫은 구간 [0, 1]의 보간 계수

일반적인 방법과는 달리, 정적 버전의 slerp는 대상 쿼터니언을 slerp 연산의 결과로 설정합니다.
// 코드 셋업
var startQuaternion = new THREE.Quaternion (). set (0, 0, 0, 1) .normalize ();
var endQuaternion = new THREE.Quaternion (). set (1, 1, 1, 1) .normalize ();
var t = 0;

// 루프에서 메쉬의 회전을 업데이트한다.
t = (t + 0.01) % 1; // 일정한 각운동량
THREE.Quaternion.slerp (startQuaternion, endQuaternion, mesh.quaternion, t);
# .slerpFlat (dst, dstOffset, src0, srcOffset0, src1, srcOffset1, t)

dst - 출력 배열.
dstOffset - 출력 배열에 대한 오프셋입니다.
src0 - 스타트하는 쿼터니언의 소스 배열
srcOffset0 - 배열 src0 에의 오프셋 (offset)
src1 - 타겟 수식의 소스 배열.
srcOffset1 - 배열 src1 에의 오프셋 (offset)
t - 표준화 된 보간 인자 (0과 1 사이).

위의 정적 slerp 메서드와 비슷하지만 숫자의 평면 배열에서 직접 작동합니다.
출처

src / math / Quaternion.js