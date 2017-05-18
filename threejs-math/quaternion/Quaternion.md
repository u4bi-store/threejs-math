Quaternion

Implementation of a quaternion. This is used for rotating things without encountering the dreaded gimbal lock issue, amongst other advantages.
Example

var quaternion = new THREE.Quaternion();
quaternion.setFromAxisAngle( new THREE.Vector3( 0, 1, 0 ), Math.PI / 2 );

var vector = new THREE.Vector3( 1, 0, 0 );
vector.applyQuaternion( quaternion );
Constructor

Quaternion( x, y, z, w )

x - x coordinate
y - y coordinate
z - z coordinate
w - w coordinate
Properties

# .x

Changing this property will result in onChangeCallback being called.
# .y

Changing this property will result in onChangeCallback being called.
# .z

Changing this property will result in onChangeCallback being called.
# .w

Changing this property will result in onChangeCallback being called.
Methods

# .clone ()

Creates a new Quaternion with identical x, y, z and w properties to this one.
# .conjugate ()

Returns the rotational conjugate of this quaternion. The conjugate of a quaternion represents the same rotation in the opposite direction about the rotational axis.
# .copy ( q )

Copies the x, y,	z and w properties of q into this quaternion.
# .equals ( v )

v - Quaternion that this quaternion will be compared to.

Compares the x, y,	z and w properties of v to the equivalent properties of this quaternion to determine if they represent the same rotation.
# .dot ( v )

Calculates the dot product of quaternions v and this one.
# .fromArray ( array, offset )

array - array of format (x, y, z, w) used to construct the quaternion.
offset - (optional) an offset into the array.

Sets this quaternion's x, y,	z and w properties from an array.
# .inverse ()

Inverts this quaternion - calculate the conjugate and then normalizes the result.
# .length ()

Computes the Euclidean length (straight-line length) of this quaternion, considered as a 4 dimensional vector.
# .lengthSq ()

Computes the Euclidean length (straight-line length) of this quaternion, considered as a 4 dimensional vector. This can be useful if you are comparing the lengths of two quaternions, as this is a slightly more efficient calculation than length().
# .normalize ()

Normalizes this quaternion - that is, calculated the quaternion that performs the same rotation as this one, but has length equal to 1.
# .multiply ( q )

Multiplies this quaternion by q.
# .multiplyQuaternions ( a, b )

Sets this quaternion to a x b.
Adapted from the method outlined here.
# .onChange ( onChangeCallback )

Sets the onChangeCallback() method.
# .onChangeCallback ( )

This function is called whenever any of the following occurs:
The x, y, z or w properties are changed.
The set(), copy(), clone(), setFromAxisAngle(), setFromRotationMatrix(), conjugate(), normalize(), multiplyQuaternions(), slerp() or fromArray() functions are called.
setFromEuler() function is called with its update argument set to true.
By default it is the empty function, however you can change it if needed using onChange( onChangeCallback ).
# .premultiply ( q )

Pre-multiplies this quaternion by q.
# .slerp ( qb, t )

qb - The other quaternion rotation
t - interpolation factor in the closed interval [0, 1].

Handles the spherical linear interpolation between quaternions. t represents the amount of rotation between this quaternion (where t is 0) and qb (where t is 1). This quaternion is set to the result. Also see the static version of the slerp below.
// rotate a mesh towards a target quaternion
	mesh.quaternion.slerp( endQuaternion, 0.01 );
# .set ( x, y, z, w )

Sets x, y, z, w properties of this quaternion.
# .setFromAxisAngle ( axis, angle )

Sets this quaternion from rotation specified by axis and angle.
Adapted from the method here.
Axis is assumed to be normalized, angle is in radians.
# .setFromEuler ( euler )

Sets this quaternion from the rotation specified by Euler angle.
# .setFromRotationMatrix ( m )

Sets this quaternion from rotation component of m.
Adapted from the method here.
# .setFromUnitVectors ( vFrom, vTo )

Sets this quaternion to the rotation required to rotate direction vector vFrom to direction vector vTo.
Adapted from the method here.
vFrom and vTo are assumed to be normalized.
# .toArray ( array, offset )

array - An optional array to store the quaternion. If not specified, a new array will be created.
offset - (optional) if specified, the result will be copied into this Array.

Returns the numerical elements of this quaternion in an array of format [x, y, z, w].
Static Methods

Static methods (as opposed to instance methods) are designed to be called directly from the class, rather than from a specific instance. So to use the static version of, call it like so:
THREE.Quaternion.slerp( qStart, qEnd, qTarget, t ); By contrast, to call the 'normal' or instanced slerp method, you would do the following:
//instantiate a quaternion with default values
var q = new THREE.Quaternion();

//call the instanced slerp method
q.slerp( qb, t )
# .slerp ( qStart, qEnd, qTarget, t )

qStart - The starting quaternion (where t is 0)
qEnd - The ending quaternion (where t is 1)
qTarget - The target quaternion that gets set with the result
t - interpolation factor in the closed interval [0, 1].

Unlike the normal method, the static version of slerp sets a target quaternion to the result of the slerp operation.
// Code setup
	var startQuaternion = new THREE.Quaternion().set( 0, 0, 0, 1 ).normalize();
	var endQuaternion = new THREE.Quaternion().set( 1, 1, 1, 1 ).normalize();
	var t = 0;

	// Update a mesh's rotation in the loop
	t = ( t + 0.01 ) % 1; // constant angular momentum
	THREE.Quaternion.slerp( startQuaternion, endQuaternion, mesh.quaternion, t );
# .slerpFlat ( dst, dstOffset, src0, srcOffset0, src1, srcOffset1, t )

dst - The output array.
dstOffset - An offset into the output array.
src0 - The source array of the starting quaternion.
srcOffset0 - An offset into the array src0.
src1 - The source array of the target quatnerion.
srcOffset1 - An offset into the array src1.
t - Normalized interpolation factor (between 0 and 1).

Like the static slerp method above, but operates directly on flat arrays of numbers.
Source

src/math/Quaternion.js