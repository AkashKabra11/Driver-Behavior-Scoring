**AIM**

Given the Live on board data of various drivers, a score corresponding to each driver is to be formulated, which will help insurance companies to rate a Driver. 

**FEATURES USED**

All internal features which help to predict driver behavior are used. 

    • Harsh Acceleration : Harsh acceleration is when a driver applies more force than normal to the vehicle's accelerator. This can be an indicator of aggressive or unsafe driving.
      
    • Harsh braking : Harsh braking is when a driver applies more force than normal to the
      vehicle's brake. This again indicates rash driving. 
      
    • Harsh cornering : Harsh cornering is when a driver enters a corner at a speed greater than that requiredto make the turn safely. This can result in a dangerous situation due to oversteer or roll-over of the vehicle.
      
    • Overspeeding: Overspeeding currently is defined for an event as: 
    - OS = (v-a)/a   if v>a
    - OS = 0         otherwise 
      Where a = speed limit, v = instantaneous velocity.
      
    • Velocity * Acceleration : Another interesting feature obtained is v*a. Consider the following cases:
          1) a = 0, v = constant : v*a =0
          2) a = constant, v = 0 : v*a =0
          3) a = high, v = high : v*a = high
          4) a = low, v = low : v*a = low.
      So, whenever this parameter has high value, there is an issue in Driver Behavior,
      otherwise it’s the desired condition.

**METHODOLOGY:**

    1. Normalize each feature.
    2. Apply k-means clustering algorithm and get optimal number of clusters.
    3. After everything is marked, identify which driving instances are good and which are poor.
    4. Using these clusters, we can derieve various results. For instance: if driver fall in Harsh Braking Cluster, he needs to work upon  his braking events and maintain speed. 
    5. Also, a score can be generated for each driver using these good/poor instances, which will serve the insurance companies for rating each driver.
       
**RESULTS**

After applying k- means clustering on a dataset of 1.2 lakh data points of a vehicle for
over 4 days, results obtained were impressive. Following five clusters are obtained each of which
represent different driving behaviors.
 - Cluster 1: It contains most of the Harsh Cornering Events, v*a is low.
 - Cluster 2: It contains most of the Harsh Braking Events, v*a is very low.
 - Cluster 3: It contains most of the Harsh Acceleration Events v*a is pretty high.
 - Cluster 4: It contains most of the overspeeding events, v*a is low.
 - Cluster 5: It is the best driving behavior cluster obtained.

