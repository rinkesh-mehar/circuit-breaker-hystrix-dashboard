#What is Circuit Breaker
Circuit breaker is a design pattern used in modern software development. It is used to detect failures and encapsulates the logic of preventing a failure from constantly recurring, during maintenance, temporary external system failure or unexpected system difficulties.

##Behaviour
Depending on the state, Circuit Breaker changes its behavior. There are three states of a Circuit Breaker.

**Closed**
If Client request is sent to the actual service method only, then it is called as CLOSED CIRCUIT. Hence, this state represents that the service is running properly and providing the expected functionality.

**Open**
If Client request is redirected to Fallback method, then such case is an OPEN CIRCUIT. Hence, this state represents that service is unavailable or faulty and error rate is beyond the threshold.

**Half-Open**
Once the state becomes OPEN, we wait for some time in the OPEN state. After a certain period of time, the state becomes HALF_OPEN.
During this period, we do send some requests to Service to check if we still get the proper response. If the failure rate is below the threshold, the state would become CLOSED. If the failure rate is above the threshold, then the state becomes OPEN once again. This cycle continues till the service becomes stable.

##To open Hystrix Dashboard
http://localhost:9098/hystrix

##To monitor the circuit using dashboard
http://localhost:9098/hystrix.stream