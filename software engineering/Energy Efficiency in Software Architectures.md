#software-architecture #software-engineering #GreenComputing 

Energy is no longer unlimited and must be considered alongside other software [[quality attributes]].

![[Pasted image 20241217111034.png]]
See: [[Quality Attributes#Quality attribute scenarios]]

**Example**: A system deallocates unused resources during non-peak periods while maintaining a maximum 2-second database query latency. This achieves 50% energy savings.

## Tactics for energy efficiency

Energy efficiency tactics are categorized into strategies to monitor, allocate, and reduce resources:

![[Pasted image 20241217165858.png]]

1. **Monitor Resources**:
    
    - **Metering**: Collect real-time energy usage data via sensors.
    - **Static Classification**: Sometimes real-time data collection is infeasible. In static classification, pre-defined energy consumption models are used for hardware resources.
    - **Dynamic Classification**: Unlike static models, dynamic models adjust estimates based on workload and transient conditions.
2. **Allocate Resources**:
    
    - **Reduce Usage**: Techniques like dimming displays or deactivating unused devices.
    - **Discovery**: Match service requests with suitable providers to minimize energy overhead.
    - **Schedule Resources**: Allocate tasks efficiently to balance performance and energy.
3. **Reduce Resource Demand**:
    
    - Techniques include managing event arrival, limiting responses, prioritizing events, and optimizing execution times.



## Energy efficient design pattern
Energy-efficient patterns include:

1. **Sensor Fusion**:
    
    - Combines data from low-power and high-power sensors to reduce energy usage.
    - **Benefits**: Saves energy by minimizing reliance on high-power sensors.
    - **Trade-offs**: Increased complexity; potential for higher overall energy usage if high-power sensors are frequently accessed.
2. **Kill Abnormal Tasks**:
    
    - Monitors apps for excessive energy use and terminates them if necessary.
    - **Benefits**: Safeguards against energy-intensive apps.
    - **Trade-offs**: May conflict with user intentions; monitoring adds system overhead.
3. **Power Monitor**:
    
    - Manages and deactivates idle system devices.
    - **Benefits**: Intelligent power savings without affecting user experience.
    - **Trade-offs**: Latency in reactivating devices; startup costs may outweigh benefits in some cases.


## Practice problems

### Spring 24
Software Project Scenario: The EV Charging Station Finder and Slot Booking software project aims to facilitate electric vehicle (EV) owners in locating available charging stations and booking slots for charging their vehicles. The application will feature a user-friendly interface accessible via mobile devices and websites.
Key features include:
Charging Station Locator: Users can search for nearby charging stations based on their current location or specified area. The application will provide real-time data on the availability of charging stations, including information on the types of chargers available and their charging capacities.

Slot Booking: Once users locate a suitable charging station, they can book available slots for charging their vehicles. Users can specify the desired charging duration and receive confirmation of their booking, ensuring convenience and efficiency in managing their charging needs.

User Profiles: Users can create profiles within the application, allowing them to save favorite charging stations, view past booking history, and receive notifications regarding upcoming bookings and charging station availability.

Integration with Payment Gateways: The application will integrate with secure payment gateways to facilitate seamless transactions for booking slots. Users can make payments securely within the application, ensuring a hassle-free experience.

Feedback and Rating System: Users can provide feedback and ratings for charging stations based on their experience, helping to improve the overall quality and reliability of the service.
  
Overall, the EV Charging Station Finder and Slot Booking software project aims to enhance the accessibility and convenience of EV charging infrastructure, promoting the adoption of electric vehicles and contributing to sustainability efforts.  
**Question:**
1. How can you allocate resources properly to make the project energy efficient? Discuss the tactics appropriately. (CO2) 
2. Can you apply the sensor fusion energy efficiency pattern in the above project? Why or why not? Explain properly. 
3. Create a minimalist utility tree for the scenario above, focusing on Availability, Deployability, and Energy Efficiency quality attributes. Each quality attribute should have only one refinement, and each refinement should have a single scenario associated with it.

**Solution:**
1. 
	**Reduce usage:** Deactivating non-essentials services during non-peak hours.
	**Scheduled resources:** Optimize the task queue for real-time updates on charging station availability to reduce redundant computations and API calls.
	**Discovery**: Match user queries with charging stations based on location and requirements, minimizing search overhead.
2.
   **Sensor Fusion** can be applied in this project but with considerations:
   #### **Why It Can Be Applied**:

- The app can integrate **low-power GPS sensors** and **network-based location services** (e.g., Wi-Fi triangulation) to determine the user's location.
- Using low-power sensors (network-based methods) for initial location data and switching to GPS only if necessary can conserve energy.

#### **Why It Might Not Be Feasible**:

- For highly accurate real-time data like charging station availability, integration of external IoT sensors or APIs is essential, which might not benefit from sensor fusion.
3. 
| **Quality Attribute** | **Refinement**                              | **Scenario**                                                                                                                                      |
| --------------------- | ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Availability**      | Real-Time Availability of Charging Stations | The system ensures real-time updates on charging slot availability with a maximum latency of 2 seconds for query responses.                       |
| **Deployability**     | Cross-Platform Accessibility                | The software can be deployed and accessed seamlessly via mobile devices and websites without requiring separate development for each platform.    |
| **Energy Efficiency** | Optimize Backend Resource Usage             | The system dynamically scales backend resources during peak and off-peak times, reducing energy consumption by 40% while maintaining performance. |


### Spring 23
What are the energy efficiency tactics for allocating resources? Explain briefly each of them.
**Ans:**
    - **Reduce Usage**: Techniques like dimming displays or deactivating unused devices.
    - **Discovery**: Match service requests with suitable providers to minimize energy overhead.
    - **Schedule Resources**: Allocate tasks efficiently to balance performance and energy.

