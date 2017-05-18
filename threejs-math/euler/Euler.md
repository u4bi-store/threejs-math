Euler

A class representing Euler Angles.

Euler angles describe a rotational transformation by rotating an object on its various axes in specified amounts per axis, and a specified axis order.
Example

var a = new THREE.Euler( 0, 1, 1.57, 'XYZ' );
var b = new THREE.Vector3( 1, 0, 1 );
b.applyEuler(a);
Constructor

Euler( x, y, z, order )

x - (optional) the angle of the x axis in radians. Default is 0.
y - (optional) the angle of the y axis in radians. Default is 0.
z - (optional) the angle of the z axis in radians. Default is 0.
order - (optional) a string representing the order that the rotations are applied, defaults to 'XYZ' (must be upper case).

Properties

# .isEuler

Used to check whether this or derived classes are Eulers. Default is true.

You should not change this, as it used internally for optimisation.
# .order

The order in which to apply rotations. Default is 'XYZ', which means that the object will first be rotated around its X axis, then its Y axis and finally its Z axis. Other possibilities are: 'YZX', 'ZXY', 'XZY', 'YXZ' and 'ZYX'. These must be in upper case.

Three.js uses intrinsic (Tait-Bryan) ordering, also known as yaw, pitch and roll. This means that rotations are performed with respect to the local coordinate system. That is, for order 'XYZ', the rotation is first around world-X, then around local-Y (which may now be different from the world Y-axis), then local-Z (which may be different from the world Z-axis).

Some implementations may use extrinsic (proper) ordering, in which case rotations are performed with respect to the world coordinate system, so that for order 'XYZ', the rotations are around world-X, world-Y, and world-Z.

Converting between the two types is relatively straightforward, you just need to reverse the order and the rotation, so that an intrinsic (three.js) Euler rotation of angles a, b, c about XYZ will be equivalent to to an extrinsic Euler rotation of angles c, b, a about ZYX.

If the order is changed, onChangeCallback will be called.
# .x

The current value of the x component.

If this is changed, onChangeCallback will be called.
# .y

The current value of the y component.

If this is changed, onChangeCallback will be called.
# .z

The current value of the z component.

If this is changed, onChangeCallback will be called.
Methods

# .copy ( euler )

Copies value of euler to this euler.
# .clone ()

Returns a new Euler with the same parameters as this one.
# .equals ( euler )

Checks for strict equality of this euler and euler.
# .fromArray ( array )

array of length 3 or 4. The optional 4th argument corresponds to the order.

Assigns this euler's x angle to array[0]. 
Assigns this euler's y angle to array[1]. 
Assigns this euler's z angle to array[2]. 
Optionally assigns this euler's order to array[3].
# .onChange ( onChangeCallback )

onChangeCallback - set the value of the onChangeCallback() function.
# .onChangeCallback ( )

By default this is an empty function, however it can be set via onChange().
It gets called after changing the x, y, z or order properties, and also after calling most setter functions (see those for details).
# .reorder ( newOrder )

Resets the euler angle with a new order by creating a quaternion from this euler angle and then setting this euler angle with the quaternion and the new order. 

WARNING: this discards revolution information.
# .set ( x, y, z, order )

x - the angle of the x axis in radians.
y - the angle of the y axis in radians.
z - the angle of the z axis in radians.
order - (optional) a string representing the order that the rotations are applied.

Sets the angles of this euler transform and optionally the order and then call onChangeCallback().
# .setFromRotationMatrix ( m, order, update )

m - a Matrix4 of which the upper 3x3 of matrix is a pure rotation matrix (i.e. unscaled).
order - (optional) a string representing the order that the rotations are applied.
update - (optional) whether to call onChangeCallback() after applying the matrix.

Sets the angles of this euler transform from a pure rotation matrix based on the orientation specified by order.
# .setFromQuaternion ( q, order, update )

q - a normalized quaternion.
order - (optional) a string representing the order that the rotations are applied.
update - (optional) whether to call onChangeCallback() after applying the matrix.

Sets the angles of this euler transform from a normalized quaternion based on the orientation specified by order.
# .setFromVector3 ( vector, order )

vector - Vector3.
order - (optional) a string representing the order that the rotations are applied.

Set the x, y and z, and optionally update the order. onChangeCallback() is called after these changes are made.
# .toArray ( array, offset )

array - (optional) array to store the euler in.
offset (optional) offset in the array.
Returns an array of the form [x, y, z, order ].
# .toVector3 ()

Returns the Euler's x, y and z properties as a Vector3.
Source

src/math/Euler.js