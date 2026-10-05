DEAD RECKONING 
Dead reckoning is essentially an estimation method we use in robotics.
It is used to estimate the final position of a robot based on its initial position.
It does this by tracking the motion that occurred across a specific time interval.
Instead of needing GPS all the time, the robot just builds on where it previously was.

To actually track this motion, we mostly use sensors like IMUs, cameras, and LiDARs.
IMUs handle the rapid, split-second changes in physical acceleration.
Cameras help out by tracking visual features around the drone frame-by-frame.
LiDARs shoot out lasers to give us exact distances and a proper metric scale.
Working together, these sensors help map out a continuous trajectory for the robot.

However, the biggest issue with using dead reckoning alone is drift.
Drift refers to the tendency for the final position calculated to differ from the real final position.
As the drone flies, its estimated location gradually pulls away from where it actually is.
This deviation happens because of a major flaw called error accumulation.
Error accumulation refers to the changes in time to calculated values from real values.
It is usually caused by the interferences of sensor operations or other factors in the environment.
Since no sensor is perfect, things like vibration or poor lighting introduce tiny mistakes.
Because dead reckoning relies on the last known position, these tiny mistakes add up over time.
A tiny fraction of a degree off in an IMU measurement quickly turns into a massive gap.
While cameras and LiDARs help ground the data, they aren't totally immune to the environment either.
Blank walls or bad weather can easily mess with their readings and add to the problem.
Over longer distances, this uncorrected error accumulation makes the estimated position unreliable.
That is why dead reckoning shouldn't be fully trusted for indefinite, long-term navigation.
It is incredibly useful for short-term tracking and filling the gaps between global updates.
But for a robust system, we have to combine dead reckoning with absolute references.
Otherwise, the estimated path will always end up drifting away from reality.
