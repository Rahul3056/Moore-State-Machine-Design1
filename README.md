### **Moore State Machine Design**  

#### **Concept Overview**  
A **Moore State Machine** is a **Finite State Machine (FSM)** where the **output depends only on the current state** and not on the input. The output is stable throughout the clock cycle, making Moore machines **easier to design and debug**.  

#### **Detailed Explanation**  
- **Components of a Moore Machine:**  
  1. **States (Q):** Represents different conditions of the system.  
  2. **Inputs (X):** External signals that affect state transitions.  
  3. **State Transition Function (δ):** Defines how states change based on inputs.  
  4. **Output Function (λ):** Outputs are derived only from the current state.  
  5. **Clock:** Controls state transitions at defined intervals.  
  6. **Reset:** Initializes the machine to a known state.  

- **Difference Between Moore and Mealy FSMs:**  
  - **Moore FSM:** Output depends only on the state.  
  - **Mealy FSM:** Output depends on both state and input.  

#### **Example: 2-bit Sequence Detector (Detecting "10")**  
- **States Definition:**  
  - `S0`: Initial state (No bits detected)  
  - `S1`: '1' detected  
  - `S2`: '10' detected (output = 1)  

- **State Transition Table:**  

| Current State | Input (X) | Next State | Output (Z) |  
|--------------|----------|------------|------------|  
| S0 (Initial) | 0        | S0         | 0          |  
| S0          | 1        | S1         | 0          |  
| S1          | 0        | S2         | 0          |  
| S1          | 1        | S1         | 0          |  
| S2          | 0        | S0         | 1          |  
| S2          | 1        | S1         | 1          |  

#### **State Diagram Representation**  
- **S0 → S1 on input 1**  
- **S1 → S2 on input 0**  
- **S2 → S0 with output 1**  

#### **Boolean Expressions**  
- **Next State Logic:**  
  `S1 = S0 • X`  
  `S2 = S1 • X̅`  
- **Output Logic:**  
  `Z = S2`  

#### **Applications**  
- Sequence detection  
- Traffic light control  
- Elevator control systems  

#### **Execution Steps**  
1. Open **QuestaSim/Xilinx ISE/Vivado**.  
2. Write the **Verilog code** for the Moore FSM.  
3. Create a **testbench** to verify the state transitions.  
4. Simulate and observe the **waveform**.  

#### **Real-World Example for Practice**  
Design a **Moore FSM for a vending machine** that dispenses an item when it detects a valid coin sequence.  

#### **Further Enhancements**  
- Modify the FSM to detect other sequences (e.g., "101").  
- Implement a **3-bit sequence detector** using a Moore FSM.
