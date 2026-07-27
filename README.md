<h1>ExpNo 1 : Developing AI Agent with PEAS Description</h1>

<h3>Name: K MONISHWAR</h3>
<h3>Register Number : 212225230188</h3>

<h3>AIM:</h3>
<br>

<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>

<br>

<h3>Theory</h3>

<h3>Medicine Prescribing Agent:</h3>

<p>
The medicine prescribing agent monitors the health condition of patients admitted in a hospital. The hospital consists of two rooms, Room A and Room B. Each room contains one patient whose body temperature is generated randomly.
</p>

<p>
The agent checks the temperature of the patient in each room. If the patient's temperature is greater than 98.5 degrees Fahrenheit, the patient is considered unhealthy. The agent prescribes medicine and treats the patient by reducing the temperature to a normal value.
</p>

<p>
After treating one room, the agent moves to the other room and repeats the same process. The movement of the agent decreases its performance, while successfully treating an unhealthy patient increases the performance.
</p>

<p>
Hence, the medicine prescribing agent identifies unhealthy patients and prescribes medicine to improve their health condition.
</p>

<hr>

<h3>PEAS DESCRIPTION:</h3>

<table border="1">
<tr>
<td><strong>Agent Type</strong></td>
<td><strong>Performance</strong></td>
<td><strong>Environment</strong></td>
<td><strong>Actuators</strong></td>
<td><strong>Sensors</strong></td>
</tr>

<tr>
<td><strong>Medicine Prescribing Agent</strong></td>
<td><strong>Treat unhealthy patients and minimize unnecessary movement</strong></td>
<td><strong>Hospital rooms and patients</strong></td>
<td><strong>Medicine prescription and treatment</strong></td>
<td><strong>Temperature sensor and room location</strong></td>
</tr>
</table>

<hr>

<h3>DESIGN STEPS</h3>

<h3>STEP 1: Identifying the input:</h3>

<p>
Patient temperature and room location.
</p>

<h3>STEP 2: Identifying the output:</h3>

<p>
Prescribe medicine if the patient's temperature is greater than 98.5 degrees Fahrenheit.
</p>

<h3>STEP 3: Developing the PEAS description:</h3>

<p>
PEAS description is developed using the performance measure, environment, actuators and sensors of the medicine prescribing agent.
</p>

<h3>STEP 4: Implementing the AI agent:</h3>

<p>
The agent checks the temperature of patients in both rooms. If the patient has a fever, the agent prescribes medicine and treats the patient. The agent then moves to the next room and repeats the process.
</p>

<h3>STEP 5:</h3>

<p>
Measure the performance parameters. For every successful treatment, the performance is incremented. For every movement between rooms, the performance is decremented.
</p>

<h3>PYTHON PROGRAM:</h3>

<pre>
import random

class MedicineAgent:
    def __init__(self):
        self.rooms = {
            "Room A": random.randint(96, 103),
            "Room B": random.randint(96, 103)
        }

        self.performance = 0

    def display_patients(self):
        print("\n--- Patient Details ---")

        for room, temp in self.rooms.items():
            print(f"{room} : Temperature = {temp}°F")

    def check_patient(self, room):
        temp = self.rooms[room]

        print(f"\nAgent moved to {room}")

        self.performance -= 1

        if temp &gt; 98.5:
            print("Patient has fever.")
            print("Medicine Prescribed: Paracetamol")

            self.performance += 2

            self.rooms[room] = 98.0

            print("Patient treated successfully.")

        else:
            print("Patient is healthy.")

    def run(self):
        print("=== Medicine Prescribing AI Agent ===")

        self.display_patients()

        room_order = list(self.rooms.keys())

        random.shuffle(room_order)

        for room in room_order:
            self.check_patient(room)

        print("\n--- Final Patient Status ---")

        for room, temp in self.rooms.items():
            print(f"{room} : Temperature = {temp}°F")

        print("\nFinal Performance Score =", self.performance)


agent = MedicineAgent()
agent.run()
</pre>

<hr>

<h3>SAMPLE OUTPUT:</h3>

<pre>
<img width="798" height="508" alt="Screenshot 2026-07-27 104157" src="https://github.com/user-attachments/assets/ef636f97-f88f-4168-8a64-697215d5a75a" />

</pre>

<hr>

<h3>RESULT:</h3>

<p>
Thus, the PEAS description for the medicine prescribing agent was developed successfully, and the AI agent was implemented to identify unhealthy patients, prescribe medicine, and measure its performance based on movement and treatment.
</p>
