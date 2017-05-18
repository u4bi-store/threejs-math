Matrix4

A class representing a 4x4 matrix.

The most common use of a 4x4 matrix in 3D computer graphics is as a Transformation Matrix. For an introduction to transformation matrices as used in WebGL, check out this tutorial.

This allows a Vector3 representing a point in 3D space to undergo transformations such as translation, rotation, shear, scale, reflection, orthogonal or perspective projection and so on, by being multiplied by the matrix. This is known as	applying the matrix to the vector.

Every Object3D has three associated Matrix4s:
Object3D.matrix: This stores the local transform of the object.
Object3D.matrixWorld: The global or world transform of the object. This is the object's transformation relative to its parent. If the object has no parent, then this is identical to the local transform.
Object3D.modelViewMatrix: This represents the object's transformation relative to the camera's coordinate system. An object's modelViewMatrix is the object's matrixWorld pre-multiplied by the camera's matrixWorldInverse.
Cameras have two additional Matrix4s:
Camera.matrixWorldInverse: The view matrix - the inverse of the Camera's matrixWorld.
Camera.projectionMatrix: Represents the information how to project the scene to clip space.
Note: Object3D.normalMatrix is not a Matrix4, but a Matrix3.
A Note on Row-Major and Column-Major Ordering

The set() method takes arguments in row-major order, while internally they are stored in the elements array in column-major order.

This means that calling
var m = new Matrix4();

m.set( 11, 12, 13, 14,
       21, 22, 23, 24,
       31, 32, 33, 34,
       41, 42, 43, 44 ); will result in the elements array containing:
m.elements = [ 11, 21, 31, 41,
               12, 22, 32, 42,
               13, 23, 33, 43,
               14, 24, 34, 44 ]; and internally all calculations are performed using column-major ordering. However, as the actual ordering makes no difference mathematically and most people are used to thinking about matrices in row-major order, the three.js documentation shows matrices in row-major order. Just bear in mind that if you are reading the source code, you'll have to take the [link: https://en.wikipedia.org/wiki/Transpose transpose] of any matrices outlined here to make sense of the calculations.
Constructor

Matrix4()

Creates and initializes the Matrix4 to the 4x4 identity matrix.
Properties

# .elements

A column-major list of matrix values.
# .isMatrix4

Used to check whether this or derived classes are Matrix4s. Default is true.

You should not change this, as it used internally for optimisation.
Methods

# .applyToBufferAttribute ( attribute )

attribute - An attribute of floats that represent 3D vectors.

Multiplies (applies) this matrix to every 3D vector in the attribute.
# .clone ()

Creates a new Matrix4 with identical elements to this one.
# .compose ( position, quaternion, scale )

Sets this matrix to the transformation composed of position, quaternion and scale. Internally this calls makeRotationFromQuaternion( quaternion ) followed by scale( scale ), then finally setPosition( position ).
# .copy ( m )

Copies the elements of matrix m into this matrix.
# .copyPosition ( m )

Copies the translation component of the supplied matrix m into this matrix's translation component.
# .decompose ( position, quaternion, scale )

Decomposes this matrix into it's position, quaternion and scale components.
# .determinant ()

Computes and returns the determinant of this matrix.

Based on the method outlined here.
# .equals ( m )

Return true if this matrix and m are equal.
# .extractBasis ( xAxis, yAxis, zAxis )

Extracts the basis of this matrix into the three axis vectors provided. If this matrix is:
a, b, c, d,
e, f, g, h,
i, j, k, l,
m, n, o, p then the xAxis, yAxis, zAxis will be set to:
xAxis = (a, e, i)
yAxis = (b, f, j)
zAxis = (c, g, k)
# .extractRotation ( m )

Extracts the rotation component of the supplied matrix m into this matrix's rotation component.
# .fromArray ( array, offset )

array - the array to read the elements from.
offset - ( optional ) offset into the array. Default is 0.

Sets the elements of this matrix based on an array in column-major format.
# .getInverse ( m, throwOnDegenerate )

m - the matrix to take the inverse of.
throwOnDegenerate - (optional) If true, throw an error if the matrix is degenerate (not invertible).

Set this matrix to the inverse of the passed matrix m, using the method outlined here. If throwOnDegenerate is not set and the matrix is not invertible, set this to the 4x4 identity matrix.
# .getMaxScaleOnAxis ()

Gets the maximum scale value of the 3 axes.
# .identity ()

Resets this matrix to the identity matrix.
# .lookAt ( eye, center, up, )

Constructs a rotation matrix, looking from eye towards center oriented by the up vector.
# .makeRotationAxis ( axis, theta )

axis — Rotation axis, should be normalized.
theta — Rotation angle in radians.

Sets this matrix as rotation transform around axis by theta radians.
This is a somewhat controversial but mathematically sound alternative to rotating via Quaternions. See the discussion here.
# .makeBasis ( xAxis, yAxis, zAxis )

Set this to the basis matrix consisting of the three provided basis vectors:
xAxis.x, yAxis.x, zAxis.x, 0,
xAxis.y, yAxis.y, zAxis.y, 0,
xAxis.z, yAxis.z, zAxis.z, 0,
0,       0,       0,       1
# .makePerspective ( left, right, top, bottom, near, far )

Creates a perspective projection matrix. This is used internally by PerspectiveCamera.updateProjectionMatrix()
# .makeOrthographic ( left, right, top, bottom, near, far )

Creates an orthographic projection matrix. This is used internally by OrthographicCamera.updateProjectionMatrix().
# .makeRotationFromEuler ( euler )

Sets the rotation component (the upper left 3x3 matrix) of this matrix to the rotation specified by the given Euler Angle. The rest of the matrix is set to the identity. Depending on the order of the euler, there are six possible outcomes. See this page for a complete list.
# .makeRotationFromQuaternion ( q )

Sets the rotation component of this matrix to the rotation specified by q, as outlined here. The rest of the matrix is set to the identity. So, given q = w + xi + yj + zk, the resulting matrix will be:
1-2y²-2z²    2xy-2zw    2xz-2yw    0
2xy+2zw      1-2x²-2z²  2yz-2xw    0
2xz-2yw      2yz+2xw    1-2x²-2y²  0
0            0          0          1
# .makeRotationX ( theta )

theta — Rotation angle in radians.

Sets this matrix as a rotational transformation around the X axis by theta (θ) radians. The resulting matrix will be:
1 0      0        0
0 cos(θ) -sin(θ)  0
0 sin(θ) cos(θ)   0
0 0      0        1
# .makeRotationY ( theta )

theta — Rotation angle in radians.

Sets this matrix as a rotational transformation around the Y axis by theta (θ) radians. The resulting matrix will be:
cos(θ)  0 sin(θ) 0
0       1 0      0
-sin(θ) 0 cos(θ) 0
0       0 0      1
# .makeRotationZ ( theta )

theta — Rotation angle in radians.

Sets this matrix as a rotational transformation around the Z axis by theta (θ) radians. The resulting matrix will be:
cos(θ) -sin(θ) 0 0
sin(θ) cos(θ)  0 0
0      0       1 0
0      0       0 1
# .makeScale ( x, y, z )

x - the amount to scale in the X axis.
y - the amount to scale in the Y axis.
z - the amount to scale in the Z axis.

Sets this matrix as scale transform:
x, 0, 0, 0,
0, y, 0, 0,
0, 0, z, 0,
0, 0, 0, 1
# .makeShear ( x, y, z )

x - the amount to shear in the X axis.
y - the amount to shear in the Y axis.
z - the amount to shear in the Z axis.

Sets this matrix as a shear transform:
1, y, z, 0,
x, 1, z, 0,
x, y, 1, 0,
0, 0, 0, 1
# .makeTranslation ( x, y, z )

x - the amount to translate in the X axis.
y - the amount to translate in the Y axis.
z - the amount to translate in the Z axis.

Sets this matrix as a translation transform:
1, 0, 0, x,
0, 1, 0, y,
0, 0, 1, z,
0, 0, 0, 1
# .multiply ( m )

Post-multiplies this matrix by m.
# .multiplyMatrices ( a, b )

Sets this matrix to a x b.
# .multiplyScalar ( s )

Multiplies every component of the matrix by a scalar value s.
# .premultiply ( m )

Pre-multiplies this matrix by m.
# .scale ( v )

Multiplies the columns of this matrix by vector v.
# .set ( n11, n12, n13, n14, n21, n22, n23, n24, n31, n32, n33, n34, n41, n42, n43, n44 )

Set the elements of this matrix to the supplied row-major values n11, n12, ... n44.
# .setPosition ( v )

Sets the position component for this matrix from vector v, without affecting the rest of the matrix - i.e. if the matrix is currently:
a, b, c, d,
e, f, g, h,
i, j, k, l,
m, n, o, p This becomes:
a, b, c, v.x,
e, f, g, v.y,
i, j, k, v.z,
m, n, o, p
# .toArray ( array, offset )

array - (optional) array to store the resulting vector in.
offset - (optional) offset in the array at which to put the result.

Writes the elements of this matrix to an array in column-major format.
# .transpose ()

Transposes this matrix.
Source

src/math/Matrix4.js