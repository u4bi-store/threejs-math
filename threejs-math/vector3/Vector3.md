Vector3

Class representing a 3D vector. A 3D vector is an ordered triplet of numbers (labeled x, y, and z), which can be used to represent a number of things, such as:
A point in 3D space.
A direction and length in 3D space. In three.js the length will always be the Euclidean distance (straight-line distance) from (0, 0, 0) to (x, y, z) and the direction is also measured from (0, 0, 0) towards (x, y, z).
Any arbitrary ordered triplet of numbers.
There are other things a 3D vector can be used to represent, such as momentum vectors and so on, however these are the most common uses in three.js.
Example

var a = new THREE.Vector3( 0, 1, 0 );

//no arguments; will be initialised to (0, 0, 0)
var b = new THREE.Vector3( );

var d = a.distanceTo( b );
Constructor

Vector3( x, y, z )

x - the x value of the vector. Default is 0.
y - the y value of the vector. Default is 0.
z - the z value of the vector. Default is 0.

Creates a new Vector3.
Properties

# .isVector3

Used to check whether this or derived classes are Vector3s. Default is true.

You should not change this, as it is used internally for optimisation.
# .x

# .y

# .z

Methods

# .add ( v )

Adds v to this vector.
# .addScalar ( s )

Adds the scalar value s to this vector's x, y and z values.
# .addScaledVector ( v, s )

Adds the multiple of v and s to this vector.
# .addVectors ( a, b )

Sets this vector to a + b.
# .applyAxisAngle ( axis, angle )

axis - A normalized Vector3.
angle - An angle in radians.

Applies a rotation specified by an axis and an angle to this vector.
# .applyEuler ( euler )

Applies euler transform to this vector by converting the Euler object to a Quaternion and applying.
# .applyMatrix3 ( m )

Multiplies this vector by m
# .applyMatrix4 ( m )

Multiplies this vector (with an implicit 1 in the 4th dimension) and m, and divides by perspective.
# .applyQuaternion ( quaternion )

Applies a Quaternion transform to this vector.
# .angleTo ( v )

Returns the angle between this vector and vector v in radians.
# .ceil ()

The x, y and z components of the vector are rounded up to the nearest integer value.
# .clamp ( min, max )

min - the minimum x, y and z values.
max - the maximum x, y and z values in the desired range

If this vector's x, y or z value is greater than the max vector's x, y or z value, it is replaced by the corresponding value. 

If this vector's x, y or z value is less than the min vector's x, y or z value, it is replaced by the corresponding value.
# .clampLength ( min, max )

min - the minimum value the length will be clamped to 
max - the maximum value the length will be clamped to

If this vector's length is greater than the max value, it is replaced by the max value. 

If this vector's length is less than the min value, it is replaced by the min value.
# .clampScalar ( min, max )

min - the minimum value the components will be clamped to 
max - the maximum value the components will be clamped to

If this vector's x, y or z values are greater than the max value, they are replaced by the max value. 

If this vector's x, y or z values are less than the min value, they are replaced by the min value.
# .clone ()

Returns a new vector3 with the same x, y and z values as this one.
# .copy ( v )

Copies the values of the passed vector3's x, y and z properties to this vector3.
# .cross ( v )

Sets this vector to cross product of itself and v.
# .crossVectors ( a, b )

Sets this vector to cross product of a and b.
# .distanceTo ( v )

Computes the distance from this vector to v.
# .distanceToManhattan ( v )

Computes the Manhattan distance from this vector to v.
# .distanceToSquared ( v )

Computes the squared distance from this vector to v. If you are just comparing the distance with another distance, you should compare the distance squared instead as it is slightly more efficient to calculate.
# .divide ( v )

Divides this vector by v.
# .divideScalar ( s )

Divides this vector by scalar s.
Sets vector to ( 0, 0 ) if *s = 0*.
# .dot ( v )

Calculate the dot product of this vector and v.
# .equals ( v )

Checks for strict equality of this vector and v.
# .floor ()

The components of the vector are rounded down to the nearest integer value.
# .fromArray ( array, offset )

array - the source array.
offset - ( optional) offset into the array. Default is 0.

Sets this vector's x value to be array[ offset + 0 ], y value to be array[ offset + 1 ] and z value to be array[ offset + 2 ].
# .fromBufferAttribute ( attribute, index )

attribute - the source attribute.
index - index in the attribute.

Sets this vector's x, y and z values from the attribute.
# .getComponent ( index )

index - 0, 1 or 2.

If index equals 0 returns the x value. 
If index equals 1 returns the y value. 
If index equals 2 returns the z value.
# .length ()

Computes the Euclidean length (straight-line length) from (0, 0, 0) to (x, y, z).
# .lengthManhattan ()

Computes the Manhattan length of this vector.
# .lengthSq ()

Computes the square of the Euclidean length (straight-line length) from (0, 0, 0) to (x, y, z). If you are comparing the lengths of vectors, you should compare the length squared instead as it is slightly more efficient to calculate.
# .lerp ( v, alpha )

v - Vector3 to interpolate towards.
alpha - interpolation factor in the closed interval [0, 1].

Linearly interpolate between this vector and v, where alpha is the distance along the line - alpha = 0 will be this vector, and alpha = 1 will be v.
# .lerpVectors ( v1, v2, alpha )

v1 - the starting Vector3.
v2 - Vector3 to interpolate towards.
alpha - interpolation factor in the closed interval [0, 1].

Sets this vector to be the vector linearly interpolated between v1 and v2 where alpha is the distance along the line connecting the two vectors - alpha = 0 will be v1, and alpha = 1 will be v2.
# .negate ()

Inverts this vector - i.e. sets x = -x, y = -y and z = -z.
# .normalize ()

Convert this vector to a unit vector - that is, sets it equal to the vector with the same direction as this one, but length 1.
# .max ( v )

If this vector's x, y or z value is less than v's x, y or z value, replace that value with the corresponding max value.
# .min ( v )

If this vector's x, y or z value is greater than v's x, y or z value, replace that value with the corresponding min value.
# .multiply ( v )

Multiplies this vector by v.
# .multiplyScalar ( s )

Multiplies this vector by scalar s.
# .multiplyVectors ( a, b )

Sets this vector equal to a x b.
# .project ( camera )

camera — camera to use in the projection.

Projects the vector with the camera.
# .projectOnPlane ( planeNormal )

planeNormal - A vector representing a plane normal.

Projects this vector onto a plane by subtracting this vector projected onto the plane's normal from this vector.
# .projectOnVector ( Vector3 )

Projects this vector onto another vector.
# .reflect ( normal )

normal - the normal to the reflecting plane

Reflect the vector off of plane orthogonal to normal. Normal is assumed to have unit length.
# .round ()

The components of the vector are rounded to the nearest integer value.
# .roundToZero ()

The components of the vector are rounded towards zero (up if negative, down if positive) to an integer value.
# .set ( x, y, z )

Sets the x, y and z components of this vector.
# .setComponent ( index, value )

index - 0, 1 or 2.
value - Float

If index equals 0 set x to value.
If index equals 1 set y to value.
If index equals 2 set z to value
# .setFromCylindrical ( c )

Sets this vector from the cylindrical coordinates c.
# .setFromMatrixColumn ( matrix, index )

Sets this vector's x, y and z equal to the column of the matrix specified by the index.
# .setFromMatrixPosition ( m )

Sets this vector to the position elements of the transformation matrix m.
# .setFromMatrixScale ( m )

Sets this vector to the scale elements of the transformation matrix m.
# .setFromSpherical ( s )

Sets this vector from the spherical coordinates s.
# .setLength ( l )

Set this vector to the vector with the same direction as this one, but length l.
# .setScalar ( scalar )

Set the x, y and z values of this vector both equal to scalar.
# .setX ( x )

Replace this vector's x value with x.
# .setY ( y )

Replace this vector's y value with y.
# .setZ ( z )

Replace this vector's z value with z.
# .sub ( v )

Subtracts v from this vector.
# .subScalar ( s )

Subtracts s from this vector's x, y and z compnents.
# .subVectors ( a, b )

Sets this vector to a - b.
# .toArray ( array, offset )

array - (optional) array to store the vector to. If this is not provided a new array will be created.
offset - (optional) optional offset into the array.

Returns an array [x, y, z], or copies x, y and z into the provided array.
# .transformDirection ( m )

Transforms the direction of this vector by a matrix (the upper left 3 x 3 subset of a m) and then normalizes the result.
# .unproject ( camera )

camera — camera to use in the projection.

Unprojects the vector with the camera's projection matrix.
Source

src/math/Vector3.js