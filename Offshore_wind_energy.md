# 1st Project Report: Wind Renewable Energy

**Author:** Guisela  
**Date:** April 2025  

---

# Wind Power Metrics and Variability Measures

## 1. Introduction
Main steps and equations to calculate wind power density and estimate energy production.

## 2. Methods

### Wind Power density

For calculate the wind power density (power output), it is necessary to have the wind speed in the same height of a wind turbine. Generally the wind speed measurements available are at 10 m from the surface, requiring wind speed to be estimate at the hub altitude. To estimate wind speed at 100 m, usual turbine height, the logarithmic power law (Equation 1) is applied, where \( U_{10} \) is the wind speed at 10 m, \( z_{100} \) and \( z_{10} \) are the respective heights (100 m and 10 m), and \( \alpha \) is the friction coefficient. Over open water, a typical value of \( \alpha = 0.1 \) is used [@manwell2009].

$$
U_{100} = U_{10} \cdot \left(\frac{z_{100}}{z_{10}}\right)^{\alpha}
$$

**Eq 1**: Logarithmic power law used to estimate wind speed at 100 m.

Wind power density (\( P_w \)), expressed in \( \mathrm{W/m^2} \), quantifies the wind kinetic energy per unit area available for conversion to electricity. It is calculated as Equation 2 below:

$$
P_w = \frac{1}{2} \, \rho_{100} \, U_{100}^3
$$

**Eq 2**: Wind power density calculated from air density and wind speed at 100 m.

Here \( \rho_{100} \) is the air density at 100 m height, estimated using the ideal gas law (Equation 3 below):

$$
\rho_{100} = \frac{P_{\mathrm{air}}}{R_d \cdot T}
$$

**Eq 3**: Air density at 100 m based on the ideal gas law.

Where, \( P_{\mathrm{air}} \) is the air pressure, \( T \) is the temperature (in Kelvin), and \( R_d \) is the specific gas constant for dry air (287.05 \( \mathrm{J \cdot kg^{-1} \cdot K^{-1}} \)). Both \( P_{\mathrm{air}} \) and \( T \) need to be adjusted to the hub reference height using the standard atmosphere model [@ISO1975].

### Energy production and variability

Wind energy production in a wind turbine site can be estimated by a linear interpolation of a measured power curve from a wind turbine to hourly wind data at the hub height. There is a power curve publicly available on [link text](https://en.wind-turbine-models.com/turbines). 

The capacity factor (CF) indicates the quality of the site's wind resource and how effectively the turbine is utilised. It is calculated as the ratio of the actual energy produced to the maximum possible energy output over the same period [@gipe2004]. Equation 4 below shows the formula used for CF:

$$
\mathrm{CF} = \frac{E_{\mathrm{total}}}{P_{\mathrm{rated}} \times H \times N_{\mathrm{years}}}
$$

**Eq. 4**: Capacity factor as a function of energy output and rated capacity.

\( E_{\mathrm{total}} \) is the total electrical energy produced usually expressed in GWh. \( P_{\mathrm{rated}} \) is the rated power capacity of the turbine that depends of the wind turbine choosen for the estimation. The term H corresponds to the number of hours in one year (8760 for a non leap year), and \( N_{\mathrm{years}} \) is the number of years over which the energy production is evaluated.

The coefficient of variation (CV) quantifies the relative temporal variability of wind speed, where a high CV indicates greater fluctuations that can impact grid integration and storage needs [@jowder2009; @carta2013]. It is defined by Equation 5, where \( \sigma_P \) is the standard deviation of power output normalised by the mean power production \( \overline{P}_w \):

$$
CV = \frac{\sigma_P}{\overline{P}_w}
$$

**Eq. 5**: Coefficient of variation of the power output.



## 3. Results format
Results will be presented by tables, histograms and time series for each declared offshore wind region. Spatial plots around Australia inside the EEZ will be also produced. 


## 4. References
Carta, J., Ramírez, P. & Velázquez, S., 2013. A review of the use of the coefficient of variation in the analysis of wind energy variability. Renewable and Sustainable Energy Reviews, 26, pp.439–446.

Gipe, P., 2004. Wind Power: Renewable Energy for Home, Farm, and Business. Chelsea Green Publishing.

International Organization for Standardization, 1975. International Standard Atmosphere. ISO 2533:1975.

Jowder, F.A., 2009. Wind power analysis and site matching using probability distribution functions. Renewable Energy, 34(9), pp.2174–2181.

Manwell, J.F., McGowan, J.G. & Rogers, A.L., 2009. Wind Energy Explained: Theory, Design and Application. 2nd ed. Wiley.
