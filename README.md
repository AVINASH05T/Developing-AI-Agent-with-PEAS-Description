# ExpNo 1 :Developing AI Agent with PEAS Description 
### Name: AVINASH T
### Register Number: 212223230026

## AIM: 

To find the PEAS description for the given AI problem and develop an AI agent. 

## Theory 
### Medicine prescribing agent:

Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.

<img width="921" height="163" alt="image" src="https://github.com/user-attachments/assets/3eb8106b-8a77-4a84-91f4-c58552e45bbd" />



## DESIGN STEPS 

STEP 1:

Identifying the input: Temperature from patients, Location. 

STEP 2:

Identifying the output: Prescribe medicine if the patient in a random has a fever. 

STEP 3:

Developing the PEAS description: Rooms, Patient Medicine, Treatment Sensors Location, Temperature of patient PEAS description is developed by the performance, environment, actuators, and sensors in an agent. 

STEP 4:

Implementing the AI agent: Treat unhealthy patients in each room. And check for the unhealthy patients in random room 

STEP 5: 

Measure the performance parameters: For each treatment performance incremented, for each movement performance decremente


## Program :
```c
import random 
class MedicineAgent:
  def __init__(self):        
    self.location = "Room A"        
    self.performance = 0    
  def act(self, environment):  
    temp = environment[self.location]["temperature"]                
    if temp > 98.5:            
      print(f"Patient in {self.location} unhealthy ({temp:.1f}°F). Giving medicine.")            
      self.performance += 10            
      environment[self.location]["temperature"] = 98.0        
    else:            
      print(f"Patient in {self.location} healthy ({temp:.1f}°F).")        
    self.location = "Room B" if self.location == "Room A" else "Room A"        
    self.performance -= 1        
    print(f"Moving to {self.location}. Performance: {self.performance}")        
    print("-" * 30)

def main():    
  environment = {        
      "Room A": {"temperature": random.uniform(97.0, 102.0)},        
      "Room B": {"temperature": random.uniform(97.0, 102.0)}    
  }    
  agent = MedicineAgent()

  print("Starting simulation.")    
  print("-" * 30)    
  for step in range(5):        
    print(f"--- Step {step + 1} ---")        
    agent.act(environment)                
    random_room = random.choice(["Room A", "Room B"])        
    environment[random_room]["temperature"] = random.uniform(99.0, 103.0)        
    print("Simulation finished.") 
if __name__ == "__main__":    
  main()

```

## Output:

<img width="950" height="481" alt="image" src="https://github.com/user-attachments/assets/f61236e4-d18b-4cce-8de0-540dbdab95d2" />


## Result :
Thus the developing AI Agent with PEAS Description was implemented using Python Programming Successfully.

