# Assessment of Operating Envelopes to Orchestrate DERs - OE Algorithm 4: Asset Capacity & Delta Voltage
This repository is part of the project [Assessing the Benefits of Using Operating Envelopes to Orchestrate DERs Across Australia](https://electrical.eng.unimelb.edu.au/power-energy/projects/assessing-the-benefits-of-OEs-across-Australia) funded by CSIRO. This project provided key metrics and recommendations for distribution companies (known as Distribution Network Service Providers [DNSPs] in Australia) and AEMO (the Australian system operator) to assist them in their decision-making process when defining the most suitable Operating Envelope (OE) implementations in a given distribution area.

In this repository, we use interactive code via Jupyter Notebook and Python as well as a realistic residential low voltage (LV) network to demonstrate the process and necessary calculations for the *Asset Capacity & Delta Voltage OE Algorithm* produced by The University of Melbourne. This demonstration is useful for different stakeholders (e.g., DNSPs, AEMO, CSIRO, regulators, consultancy companies, technology providers) as it can help them familiarise with the corresponding algorithm and the required inputs as well as the pros and cons.

## Asset Capacity & Delta Voltage OE
The Asset Capacity & Delta Voltage OE is more advanced than the The Asset Capacity & Critical Voltage OE as it can capture better the daily voltage variations due to interactions with the upstream HV network. At a given moment in time, it considers the spare thermal capacity of the distribution transformer (i.e., thermal capacity minus net demand of all the customers) and splits it among active customers. Then, using the spare capacity allocated to the critical customer (i.e., the customer located furthest from the distribution transformer), it estimates the voltage at the critical customer via two sensitivity curves, one that relates the aggregated P at the distribution transformer to its voltage magnitude and another that relates the aggregated P at the distribution transformer to the delta voltage between the distribution transformer and the critical customer.
- Required Monitoring: At the secondary of the transformer (aggregated P, aggregated Q, and voltage magnitude, all per phase), and at the critical customer (voltage magnitude).
- Required Electrical Models: None.

For simplicity, the case study used to demonstrate the OE algorithm corresponds to a low voltage (LV) network without modelling the upstream high voltage (HV) network. Although some adaptations have been made to ensure realistic voltage fluctuations at the distribution transformer of the LV network, the results are not exactly the same as those presented in the Final Report of the project (which used an integrated HV-LV network model). Nevertheless, the behaviour of the OE algorithm and the qualitative nature of the results remain the same.

## Pre-Requisites
- Python (Anaconda) and Jupyter Notebook (comes with Anaconda). For download links and more info: https://www.anaconda.com/download. Note that you must install the Anaconda that is compatible with your operating system (e.g., Windows, Mac). Also note that this repository is meant to be used by individuals (who can get free access to Anaconda).
- dss_python module. We use this Python-native module to run power flows based on OpenDSS (https://sourceforge.net/projects/electricdss/). To install, run `pip install dss_python` in the Anaconda Prompt. For more info: https://github.com/Team-Nando/Tutorial-DERHostingCapacity-0-dss_python#part-0-using-dss_python.
- To guarantee that you have all the necessary packages you can also run the **`requirements.txt`** file using **`pip install -r requirements.txt`** in the Anaconda prompt.

## Run the Code
Make sure you have installed all the pre-requisites (Anaconda, dss_python, requirements). Otherwise, you will not be able to go through the repository.

1. Download all the files using the green **`<> Code`** button at the top right.
   - You will get a ZIP file with a folder that contains all the files.
   - Unzip the file and place the folder somewhere on your computer/laptop.
2. To open the Jupyter Notebook file (extension **`ipynb`**) you need to:
   - Open Anaconda Navigator
   - Click on Launch Jupyter Notebook (it will open in your browser)
   - Upload the unzipped folder (with all the corresponding files) to Jupyter Notebook (the location is up to you)
   - Go inside the folder and open the **`ipynb`** file

All the instructions will be in the **`ipynb`** file.

## Credits
Arthur Gonçalves Givisiez (a.goncalvesgivisiez@unimelb.edu.au)

Nando Ochoa (luis.ochoa@unimelb.edu.au ; https://sites.google.com/view/luisfochoa)

## Licenses
Since this repository uses dss_python which is based on OpenDSS, both licenses have been included. This repository uses the BSD 3-Clause "New" or "Revised" license. Check all corresponding files (`LICENSE-OpenDSS`, `LICENSE-dss_python`, `LICENSE`).
