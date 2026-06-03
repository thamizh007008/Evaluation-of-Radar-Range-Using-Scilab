# Evaluation-of-Radar-Range-Using-Scilab
## Aim
To calculate the **maximum range of a radar system** using the **Radar Range Equation** and verify the results through **Scilab programming**.

## Theory
The **Radar Range Equation** is a key relationship used in radar system design to determine the maximum distance (**range**) at which a radar can detect a target.  

It is expressed as:

<img width="965" height="329" alt="image" src="https://github.com/user-attachments/assets/d8d311e3-5625-4a58-966c-ca75dbb5109d" />

## Algorithm

1. Initialize constants:
   - λ (wavelength) = 0.03 m  
   - σ (radar cross section) = 1 m²  

2. Vary each parameter while keeping the others constant:
   - **Pt:** 0.1 → 10  
   - **Gt:** 1 → 50  
   - **Pm:** 1e⁻¹⁵ → 1e⁻¹⁰  

3. Compute maximum range using:
   R_max = ((Pt * Gt² * λ² * σ) / ((4π)³ * Pm))¼


4. Plot the following:
   - `Pt vs Rmax` 
   - `Gt vs Rmax` 
   - `Pm vs Rmax`


## Procedure

1. **Refer to the Algorithm** and write the Scilab code for the experiment.  
2. **Open Scilab** on your system.  
3. **Create a New Editor File:**  
   - Go to `File → New → Script`.  
4. **Type Your Code** in the editor window.  
5. **Save the File** with a suitable name (e.g., `radar_range.sce`).  
6. **Execute the Code:**  
   - Press **F5** or click **Execute → File with echo**.  
7. **If Any Errors Occur:**  
   - Review and correct the code.  
   - Save and **run it again** until it executes successfully.



##  Program  
```
Pt = 1000;          
G = 50;             
lambda = 0.03;      
sigma = 1;          
R = 1000:1000:100000;
Pr = (Pt * G^2 * lambda^2 * sigma) ./ ...
     (((4 * %pi)^3) * (R.^4));
Pr_dB = 10 * log10(Pr);

figure(1);
plot(R, Pr_dB);
xlabel("Range R (m)");
ylabel("Received Power Pr (dB)");
title("Pr(dB) vs Range(R)");
xgrid();

Pr_min = 1000;

Pt_required = (Pr_min * ((4 * %pi)^3) .* (R.^4)) ./ ...
              (G^2 * lambda^2 * sigma);
Pt_dB = 10 * log10(Pt_required);

figure(2);
plot(R, Pt_dB);
xlabel("Range R (m)");
ylabel("Transmitted Power Pt (dB)");
title("Pt(dB) vs Range(R)");
xgrid();
```

## Output

<img width="1523" height="708" alt="image" src="https://github.com/user-attachments/assets/02af443b-1cda-4111-acdb-dc84a393106d" />

## Manual Calculation

<img width="1289" height="1600" alt="WhatsApp Image 2026-06-03 at 4 06 57 PM" src="https://github.com/user-attachments/assets/c3f8ca09-6bfe-4229-944a-9506bfbd5a12" />




## Result

Thus, the maximum range of a radar system calculated using the Radar Range Equation is successfully verified using Scilab programming.# RADAR-RANGE-EQUATION
