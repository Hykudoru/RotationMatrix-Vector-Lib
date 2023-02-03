# RotationMatrix-Vector-Lib

A C++ library for calculating rotation matrices used in 3-dimensional Cartesian coordinate space.

## Things to Know
- Rotation matrices can be used to track the orientation of a mobile rigid-body relative to a world axis reference frame. 
- Intrinsic rotations rotate about the axes of the fixed coordinate system frame that's attached to the rigid body in motion. 
- The orientation of a frame is itself a rotation matrix.
# How To Use This Library
- Matrix multiplication A*B or Multiply(A, B) assumes A is the row matrix while B is the column matrix.
- The *= operator can be used like so: A *= B, means A = A\*B, where B is the column matrix.

## EXAMPLES:

### Z AXIS ROTATION: 
  Matrix3x3 rotation = Matrix3x3::RotZ(PI/2.0);
  
### EULER ROTATION:
  rotation \*= (Matrix3x3::RotZ(yaw) * Matrix3x3::RotY(pitch)) * Matrix3x3::RotX(roll);

### YAW-PITCH-ROLL:
  rotation \*= YPR(180*PI/180, 45*PI/180, 90*PI/180);

### Undo rotation:
  Matrix3x3 rotation = YPR(180*PI/180, 45*PI/180, 90*PI/180); 
  
  rotation \*= RPY(-180*PI/180, -45*PI/180, -90*PI/180);
