# static ot-cli-ftd
An ot-cli-ftd example, where the dataset parameters are predefined. By flashing the .hex to 2 different thread devices (must be Thunderboard Sense 2) and starting thread, both will join the same network - one device as the leader and the other as router.

In order to do so, follow the steps described below:

**1) flash the .hex to both Thunderboard Sense 2s**

**2) On the first Thunderboard Sense 2, type the following commands in the console:**
```
dataset commit active
ifconfig up
thread start
```

After a while, you should see the device as network leader, when calling "state"
```
state
> Leader
```

**3) On the second Thunderboard Sense 2, type the following commands in the console:**
```
dataset commit active
routerselectionjitter 1
ifconfig up
thread start
```
wait a couple of seconds (up to 2 minutes) and call `state`
```
state
> Router
```
Both devices will now be in the same network!
