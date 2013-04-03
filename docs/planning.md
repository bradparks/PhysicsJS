# Plans

state class

Vector position
Vector velocity
Vector acceleration
Number angularPosition
Number angularVelocity
Number angularAcceleration

geometry class

Array[Vector] vertices = body.geometry.getVertices()
Array[Arc] arcs = body.geometry.getArcs()

// arc collision

Arc arc1 = body1.geometry.getArcs()[0]
Arc arc2 = body2.geometry.getArcs()[0]
Vector center1 = arc1.center // clone here
Vector center2 = arc2.center

Vector c12 = center2.vsub( center1 )

Number rot1 = body.state.angularPosition

Number ang = c12.angle();

if ( ang >= (arc1.min - rot1) && ang <= (arc1.max - rot1) )
    then c12 intersects arc