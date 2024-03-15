**This Node-RED flow manages the charging of a Tesla car in three different ways:**

![1](https://github.com/MicheleMercuri/mickmmm/assets/97225788/99d5eae7-b79f-4f46-8f51-629926b513e9)

**1) 100% self-consumption of the photovoltaic production

2) Maintenance of the limit of the network electric meter's power (avoids disconnection)

3) Charging in F3 off-peak tariff (the cheapest rate in Italy)**

To use the code, it is necessary:

**A) Node-RED correctly installed in Home Assistant

B) A power meter for the power delivered by the wallbox (e.g., a Shelly EM)

C) A photovoltaic system integrated into HA

D) A Tesla car integrated into HA**

https://github.com/MicheleMercuri/mickmmm/assets/97225788/07e86794-1712-4aca-9351-953020a3201d

For automation no. 1 (100% self-consumption of the photovoltaic production), the Node-RED flow will check every 30 seconds that the charging power absorbs 100% of the available photovoltaic power. If the power value from the photovoltaic is higher or lower than 1A compared to the amperes set in Tesla, the flow recalculates the value and modifies it. To avoid errors in setting the amperes, the flow calculates the maximum and minimum available amperes for Tesla and the value of the volts available on the electric line at each cycle.
Automations can be managed from Lovelace; it is possible to switch from one type of charging to another, and the charging in F3 off-peak displays a countdown before starting.
The power of the meter can be set directly from Lovelace.

It is possible to set a charging percentage from 0% up to 100% for all charging modes (charging will stop when the target % is reached).

The code of the individual sensors must be adapted to the users' custom installations.
