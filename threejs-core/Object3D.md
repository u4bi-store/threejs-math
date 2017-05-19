Object3D

This is the base class for most objects in three.js and provides a set of properties and methods for manipulating objects in 3D space.

Note that this can be used for grouping objects via the .add( object ) method which adds the object as a child, however it is better to use Group for this.
Constructor

Object3D()

The constructor takes no arguments.
Properties

# .castShadow

Whether the object gets rendered into shadow map. Default is false.
# .children

Array with object's children. See Group for info on manually grouping objects.
# .frustumCulled

When this is set, it checks every frame if the object is in the frustum of the camera before rendering the object. Otherwise the object gets renderered every frame even if it isn't visible. Default is true.
# .id

readonly – Unique number for this object instance.
# .isObject

Used to check whether this or derived classes are Object3Ds. Default is true.

You should not change this, as it is used internally for optimisation.
# .layers

The layer membership of the object. The object is only visible if it has at least one layer in common with the Camera in use.
# .matrix

The local transform matrix.
# .matrixAutoUpdate

When this is set, it calculates the matrix of position, (rotation or quaternion) and scale every frame and also recalculates the matrixWorld property. Default is Object3D.DefaultMatrixAutoUpdate (true).
# .matrixWorld

The global transform of the object. If the Object3D has no parent, then it's identical to the local transform .matrix.
# .matrixWorldNeedsUpdate

When this is set, it calculates the matrixWorld in that frame and resets this property to false. Default is false.
# .modelViewMatrix

This is passed to the shader and used to calculate the position of the object.
# .name

Optional name of the object (doesn't need to be unique). Default is an empty string.
# .normalMatrix

This is passed to the shader and used to calculate lighting for the object. It is the transpose of the inverse of the upper left 3x3 sub-matrix of this object's modelViewMatrix.

The reason for this special matrix is that simply using the modelViewMatrix could result in a non-unit length of normals (on scaling) or in a non-perpendicular direction (on non-uniform scaling).

On the other hand the translation part of the modelViewMatrix is not relevant for the calculation of normals. Thus a Matrix3 is sufficient.
# .onAfterRender

An optional callback that is executed immediately after the Object3D is rendered. This function is called with the following parameters: renderer, scene, camera, geometry, material, group.
# .onBeforeRender

An optional callback that is executed immediately before the Object3D is rendered. This function is called with the following parameters: renderer, scene, camera, geometry, material, group.
# .parent

Object's parent in the scene graph.
# .position

The object's local position.
# .quaternion

Object's local rotation as a Quaternion.
# .receiveShadow

Whether the material receives shadows. Default is false.
# .renderOrder

This value allows the default rendering order of scene graph objects to be overridden although opaque and transparent objects remain sorted independently. Sorting is from lowest to highest renderOrder. Default value is 0.
# .rotation

Object's local rotation (see Euler angles), in radians.
# .scale

The object's local # .scale . Default is Vector3( 1, 1, 1 ).
# .up

This is used by the lookAt method, for example, to determine the orientation of the result.
Default is Object3D.DefaultUp - that is, ( 0, 1, 0 ).
# .userData

An object that can be used to store custom data about the Object3D. It should not hold references to functions as these will not be cloned.
# .uuid

UUID of this object instance. This gets automatically assigned, so this shouldn't be edited.
# .visible

Object gets rendered if true. Default is true.
Static Properties

Static properties and methods are defined per class rather than per instance of that class. This means that changing Object3D.DefaultUp or Object3D.DefaultMatrixAutoUpdate will change the values of up and matrixAutoUpdate for every instance of Object3D (or derived classes) created after the change has been made (already created Object3Ds will not be affected).
# .DefaultUp

The default up direction for objects, also used as the default position for DirectionalLight, HemisphereLight and Spotlight (which creates lights shining from the top down).
Set to ( 0, 1, 0 ) by default.
# .DefaultMatrixAutoUpdate

The default setting for matrixAutoUpdate for newly created Object3Ds.
Methods

EventDispatcher methods are available on this class.

# .add ( object, ... )

Adds object as child of this object. An arbitrary number of objects may be added.

See Group for info on manually grouping objects.
# .applyMatrix ( matrix )

This updates the position, rotation and scale with the matrix.
# .clone ( recursive )

recursive -- if true, descendants of the object are also cloned. Default is true.

Returns a clone of this object and optionally all descendants.
# .copy ( object, recursive )

recursive -- if true, descendants of the object are also copied. Default is true.

Copy the given object into this object.
# .getObjectById ( id )

id -- Unique number of the object instance

Searches through the object's children and returns the first with a matching id.
Note that ids are assigned in chronological order: 1, 2, 3, ..., incrementing by one for each new object.
# .getObjectByName ( name )

name -- String to match to the children's Object3D.name property. 

Searches through the object's children and returns the first with a matching name.
Note that for most objects the # .name is an empty string by default. You will have to set it manually to make use of this method.
# .getObjectByProperty ( name, value )

name -- the property name to search for. 
value -- value of the given property. 

Searches through the object's children and returns the first with a property that matches the value given.
# .getWorldPosition ( optionalTarget )

optionalTarget — (optional) target to set the result. Otherwise, a new Vector3 is instantiated. 

Returns a vector representing the position of the object in world space.
# .getWorldQuaternion ( optionalTarget )

optionalTarget — (optional) if specified, the result will be copied into this Quaternion, otherwise a new Quaternion will be created. 

Returns a quaternion representing the rotation of the object in world space.
# .getWorldRotation ( optionalTarget )

optionalTarget — (optional) if specified, the result will be copied into this Euler, otherwise a new Euler will be created. 

Returns the euler angles representing the rotation of the object in world space.
# .getWorldScale ( optionalTarget )

optionalTarget — (optional) if specified, the result will be copied into this Vector3, otherwise a new Vector3 will be created. 

Returns a vector of the scaling factors applied to the object for each axis in world space.
# .getWorldDirection ( optionalTarget )

optionalTarget — (optional) if specified, the result will be copied into this Vector3, otherwise a new Vector3 will be created. 

Returns a vector representing the direction of object's positive z-axis in world space.
# .localToWorld ( vector )

vector - A vector representing a position in local (object) space.

Converts the vector from local space to world space.
# .lookAt ( vector )

vector - A vector representing a position in world space.

Rotates the object to face a point in world space.
# .raycast ( raycaster, intersects )

Abstract (empty) method to get intersections between a casted ray and this object. Subclasses such as Mesh, Line, and Points implement this method in order to use raycasting.
# .remove ( object, ... )

Removes object as child of this object. An arbitrary number of objects may be removed.
# .rotateOnAxis ( axis, angle )

axis -- A normalized vector in object space. 
angle -- The angle in radians.

Rotate an object along an axis in object space. The axis is assumed to be normalized.
# .rotateX ( rad )

rad - the angle to rotate in radians.

Rotates the object around x axis in local space.
# .rotateY ( rad )

rad - the angle to rotate in radians.

Rotates the object around y axis in local space.
# .rotateZ ( rad )

rad - the angle to rotate in radians.

Rotates the object around z axis in local space.
# .setRotationFromAxisAngle ( axis, angle )

axis -- A normalized vector in object space. 
angle -- angle in radians

Calls setFromAxisAngle( axis, angle ) on the .quaternion.
# .setRotationFromEuler ( euler )

euler -- Euler angle specifying rotation amount.
Calls setRotationFromEuler( euler) on the .quaternion.
# .setRotationFromMatrix ( m )

m -- rotate the quaternion by the rotation component of the matrix.
Calls setFromRotationMatrix( m) on the .quaternion.

Note that this assumes that the upper 3x3 of m is a pure rotation matrix (i.e, unscaled).
# .setRotationFromQuaternion ( q )

q -- normalized Quaternion.

Copy the given quaternion into .quaternion.
# .toJSON ( q )

Convert the object to JSON format.
# .translateOnAxis ( axis, distance )

axis -- A normalized vector in object space.
distance -- The distance to translate.

Translate an object by distance along an axis in object space. The axis is assumed to be normalized.
# .translateX ( distance )

Translates object along x axis by distance units.
# .translateY ( distance )

Translates object along y axis by distance units.
# .translateZ ( distance )

Translates object along z axis by distance units.
# .traverse ( callback )

callback - A function with as first argument an object3D object.

Executes the callback on this object and all descendants.
# .traverseVisible ( callback )

callback - A function with as first argument an object3D object.

Like traverse, but the callback will only be executed for visible objects. Descendants of invisible objects are not traversed.
# .traverseAncestors ( callback )

callback - A function with as first argument an object3D object.

Executes the callback on all ancestors.
# .updateMatrix ()

Update the local transform.
# .updateMatrixWorld ( force )

Update the global transform of the object and its children.
# .worldToLocal ( vector )

vector - A world vector.

Updates the vector from world space to local space.
Source

src/core/Object3D.js