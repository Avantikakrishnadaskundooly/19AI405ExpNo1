<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name:Avantika Krishnadas Kundooly</h3>
<h3>Register Number: 212224040040</h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>

#Program

```
import random

#Performance measure
performance = 0

#Hospital rooms
rooms = ["Room 1", "Room 2"]

#Randomly place the patient in one room
patient_room = random.choice(rooms)

#Agent starts from Room 1
current_room = "Room 1"

#Get patient's temperature
temperature = float(input("Enter patient's body temperature (°F): "))

print("\n===== Medicine Prescribing AI Agent =====")
print(f"Patient is in a random room.\n")

#Check each room
for room in rooms:

    # Move to another room if required
    if current_room != room:
        print(f"Moving from {current_room} to {room}...")
        performance -= 1
        current_room = room

    print(f"\nChecking {room}...")

    if room == patient_room:
        print("Patient found!")

        # Decision making based on temperature
        if temperature < 90 or temperature > 110:
            print(f"Temperature: {temperature}°F")
            print("Invalid body temperature entered.")

        elif temperature < 95:
            print(f"Temperature: {temperature}°F")
            print("Patient has Hypothermia.")
            print("Immediate medical attention required.")
            performance += 1

        elif temperature <= 99:
            print(f"Temperature: {temperature}°F")
            print("Patient is Healthy.")
            print("No medicine required.")

        elif temperature <= 102:
            print(f"Temperature: {temperature}°F")
            print("Patient has Mild Fever.")
            print("Prescribing Paracetamol.")
            performance += 1

        else:
            print(f"Temperature: {temperature}°F")
            print("Patient has High Fever.")
            print("Immediate medical treatment required.")
            print("Prescribing appropriate medicine.")
            performance += 1

    else:
        print("No patient in this room.")

print("\n===== Performance Report =====")
print("Final Performance Score:", performance)
```

# OUTPUT

<img width="620" height="678" alt="image" src="https://github.com/user-attachments/assets/b18736a5-a145-4c21-b293-7147621d9efe" />

# RESULT
The Medicine Prescribing AI Agent was successfully developed using the PEAS framework. It identified the patient's condition based on body temperature, prescribed appropriate treatment, moved between rooms to locate the patient, and measured its performance based on treatment and movement.
