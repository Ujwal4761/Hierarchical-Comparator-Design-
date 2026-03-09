DESIGN OPTIMIZATION FOR STRUCTURED CIRCUITS: COMPARATOR

The truth table has been made available 
<img width="1225" height="1047" alt="image" src="https://github.com/user-attachments/assets/f44d15f6-bf1e-4474-a8ca-cdafd9c0319f" />

The comparator has two main components:
full-comparator cells (FCC) 
half-comparator cell (HCC)

- Design-1: using only primitive complementary gates (INV, NAND, NOR).
 - Design-2: by starting with design-1 and identifying opportunities for sharing logic and/or for using complex complementary gates (e.g., XOR, XNOR, AOI (AND-ORINVERT), AOI, …). 
- Design-3: by using a mix of complementary-switch based multiplexors in combination with primitive and complex complementary gates.

HCC_D1 (design 1)
<img width="940" height="484" alt="image" src="https://github.com/user-attachments/assets/16e1da67-0951-48b9-ae40-99b1ca9b91bc" />
 

HCC_D2(design 2)
 <img width="990" height="504" alt="image" src="https://github.com/user-attachments/assets/a4714781-0a7f-4b64-85e7-35837b059cb2" />

HCC_D3(design 3)
 <img width="993" height="508" alt="image" src="https://github.com/user-attachments/assets/2509fa83-e272-492d-9243-1cb3a863e956" />


on separate note:
MUX has been designed using transmission gates
 <img width="982" height="502" alt="image" src="https://github.com/user-attachments/assets/8b9f84aa-9ad8-4582-a092-7bb5c4a73ae7" />

 <img width="940" height="482" alt="image" src="https://github.com/user-attachments/assets/953a9d41-e6e8-4a09-989e-ea602ae816fb" />


FCC_D1(design 1)
 <img width="983" height="505" alt="image" src="https://github.com/user-attachments/assets/a4c23cab-08dc-4e71-b46c-4d7d18bf1baf" />





FCC_D2(design 2)
 <img width="940" height="482" alt="image" src="https://github.com/user-attachments/assets/5bb1f944-3bde-4587-8ecf-18f9335977c1" />


FCC_D3(design 3)
 <img width="1000" height="511" alt="image" src="https://github.com/user-attachments/assets/61fd6c1a-aa58-4585-b6d7-110131f6a92c" />


Comparator_D1 (HCC_D1+ FCC_D1 + FCC_D1(dummy))
<img width="1029" height="600" alt="image" src="https://github.com/user-attachments/assets/f5cc65e5-4509-499c-86a1-1ed8ded1509b" />
 
Comparator_D2 (HCC_D2+ FCC_D2 + FCC_D2(dummy))
<img width="1031" height="524" alt="image" src="https://github.com/user-attachments/assets/4290aab3-90f8-404a-978b-390b1f5cc88d" />
 

HCC_D3 layout design
 <img width="940" height="542" alt="image" src="https://github.com/user-attachments/assets/f47811a5-65c0-4334-a1dd-1aee5521f446" />


DRC and LVS is clean
 <img width="940" height="700" alt="image" src="https://github.com/user-attachments/assets/13241eb6-9dad-434a-a1c2-546cd172243e" />
 <img width="940" height="496" alt="image" src="https://github.com/user-attachments/assets/62cdce3a-57c1-4fa5-92a5-59c37e85b3a0" />
<img width="940" height="503" alt="image" src="https://github.com/user-attachments/assets/e9b98b17-e908-4203-a342-58b1391e92d8" />

AV extraction is done for this cell
 <img width="1006" height="413" alt="image" src="https://github.com/user-attachments/assets/5fe874d1-591a-4952-b395-ed3c36c32df7" />



FCC_D3 layout is complete
<img width="1046" height="315" alt="image" src="https://github.com/user-attachments/assets/67e7f17d-d392-411b-ab00-f799e5fd5202" />
 

with no DRC and LVS errors
 <img width="940" height="694" alt="image" src="https://github.com/user-attachments/assets/6f183989-9f14-4008-adc9-35a00e1db43a" />
<img width="940" height="500" alt="image" src="https://github.com/user-attachments/assets/3da3375e-430f-4c70-a44a-403a2bf327c2" />
<img width="940" height="502" alt="image" src="https://github.com/user-attachments/assets/8e062314-3b97-4b5b-ba45-97578bd0220e" />

AV extractions is also complete for this
<img width="965" height="374" alt="image" src="https://github.com/user-attachments/assets/9302d7fb-988c-4113-85b4-050e3e46e229" />
 

FCC_D2 (design 2)
 <img width="971" height="379" alt="image" src="https://github.com/user-attachments/assets/0beaba6b-7f64-4af3-9101-244b71cb735c" />
 
no DRC and LVS errors reported

Note: 
All tabulations have been done in excel 
delay calculations for all all designs

For all testbenches I have chosen my inputs to be :
A =0011010
B =0110100
to observe the rising and falling edge.

The worst-case vector was chosen as A=0x34, B=0x6C to observe both rising and falling edges across multiple bit positions, testing the ripple propagation through all FCC stages.
Extracted view delays differ from schematic delays due to: (1) parasitic capacitances from metal interconnects which increase the load on each gate output, and (2) parasitic resistance in metal wires creating additional RC delay not modeled in schematic simulation
