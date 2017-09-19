A graphical tower defense game similar to plants vs zombies.

In each turn, new bees may enter the ant colony. Then, new ants are placed.
Finally, all insects (ants, then bees) take individual actions: bees sting ants,
and ants throw leaves at bees. The game ends either when a bee reaches the ant
queen, or all the bees are vanquished.

The Colony. The colony consists of several places that are chained together.

Placing Ants. There are two constraints that limit ant production. Placing an ant uses up some amount of the colony's
food, a different amount for each type of ant. Also, only one ant can occupy each Place.

Bees. When it is time to act, a bee either moves to the exit of its current Place if no ant blocks its path, or stings an
ant that blocks its path.

Ants. Each type of ant takes a different action and requires a different amount of food to place. The two most basic ant
types are the HarvesterAnt, which adds one food to the colony during each turn, and the ThrowerAnt, which throws a leaf
at a bee each turn.

Ants
class HarvesterAnt(Ant):
    """HarvesterAnt produces 1 additional food per turn for the colony."""

class ThrowerAnt(Ant):
    """ThrowerAnt throws a leaf each turn at the nearest Bee in its range."""

class FireAnt(Ant):
    """FireAnt cooks any Bee in its Place when it expires."""

class LongThrower(ThrowerAnt):
    """A ThrowerAnt that only throws leaves at Bees at least 5 places away."""

class ShortThrower(ThrowerAnt):
    """A ThrowerAnt that only throws leaves at Bees at most 3 places away."""

class WallAnt(Ant):
    """Ant that acts as a barrier. """

class NinjaAnt(Ant):
    """NinjaAnt does not block the path and damages all bees in its place."""

class ScubaThrower(ThrowerAnt):
    """Thrower ant in water."""

class HungryAnt(Ant):
    """HungryAnt will take three turns to digest a Bee in its place.
    While digesting, the HungryAnt can't eat another Bee.

class BodyguardAnt(Ant):
    """BodyguardAnt provides protection to other Ants."""

class TankAnt(BodyguardAnt):
    """TankAnt provides both offensive and defensive capabilities."""

class QueenAnt(ScubaThrower):  # You should change this line
    """The Queen of the colony.  The game is over if a bee enters her place."""