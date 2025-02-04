# Theoretical Portion for Los Angeles Wildfire Detection and Burn Severity Mapping  
### Using VIIRS and Landsat 9 Data in Google Earth Engine  

## Introduction  
Wildfires are a recurring natural hazard, significantly impacting ecosystems, human settlements, and air quality. Understanding the extent and severity of wildfires is crucial for effective post-fire management, ecological restoration, and climate change mitigation. Remote sensing techniques offer a reliable and efficient means of wildfire detection and burn severity assessment.  

This study leverages satellite-based data from the **Visible Infrared Imaging Radiometer Suite (VIIRS)** and **Landsat 9** to detect wildfire activity and quantify its impact on vegetation in Los Angeles, California.  

## Objectives  
The primary objectives of this analysis are:  
1. Detect active wildfire regions using VIIRS data.  
2. Map pre- and post-fire conditions using Landsat 9 imagery.  
3. Compute indices such as **Normalized Difference Vegetation Index (NDVI)** and **Normalized Burn Ratio (NBR)** to quantify burn severity and vegetation loss.  
4. Estimate the total burned area and export results for further analysis.  

## Study Area  
The region of interest (ROI) includes parts of Los Angeles, California, defined by polygon coordinates. This region is prone to wildfires due to its **Mediterranean climate**, characterized by hot, dry summers and strong **Santa Ana winds**, which exacerbate fire risks.  

## Data and Methodology  

### Dataset Selection  
- **VIIRS:** High temporal resolution data used for detecting active fire regions during the specified date range (*January 7–14, 2025*).  
- **Landsat 9:** High spatial resolution imagery used for assessing pre- and post-fire conditions, focusing on surface reflectance bands.  

### Preprocessing  
- VIIRS and Landsat 9 datasets were filtered by date and clipped to the ROI.  
- Water bodies were masked using the **Dynamic World dataset** to prevent misinterpretation of water reflectance as vegetation loss.  

### Vegetation Analysis  

#### Normalized Difference Vegetation Index (NDVI)  
NDVI is calculated to assess vegetation health before and after the wildfire.  

**Formula:**  
$$
NDVI = \frac{NIR - Red}{NIR + Red}
$$  

Where:  
- **NIR (Near-Infrared):** Reflectance in the near-infrared band.  
- **Red:** Reflectance in the red band.  

NDVI values range between **-1** and **1**:  
- **Higher values:** Indicate healthier vegetation.  
- **Lower or negative values:** Indicate sparse vegetation, bare soil, or water bodies.  

#### NDVI Change  
The difference between pre- and post-fire NDVI highlights vegetation loss caused by the wildfire.  

### Burn Severity Mapping  

#### Normalized Burn Ratio (NBR)  
NBR is used to identify burn severity.  

**Formula:**  
$$
NBR = \frac{NIR - SWIR}{NIR + SWIR}
$$  

Where:  
- **SWIR (Shortwave-Infrared):** Reflectance in the shortwave-infrared band.  

#### NBR Change  
The difference between pre- and post-fire NBR quantifies burn severity and helps delineate burned areas.  
- **Lower NBR values post-fire:** Indicate higher burn severity.  

### Burned Area Estimation  
A threshold was applied to the NBR change map to identify burned areas.  
- Pixel areas were summed to estimate the total burned area in square kilometers.  

### Data Export  
The results, including **NDVI change**, **NBR change**, and **VIIRS fire detection data**, were exported as images for further analysis.  

## Results and Expected Outcomes  

1. **Fire Detection:**  
   - VIIRS data provides real-time detection of active fires during the study period, aiding rapid response and disaster management.  

2. **Vegetation Loss:**  
   - NDVI change highlights the extent of vegetation loss, with high-resolution Landsat 9 data capturing localized impacts.  

3. **Burn Severity:**  
   - NBR change maps provide detailed information on the severity of burns, distinguishing between severely and mildly affected areas.  

4. **Burned Area Extent:**  
   - The analysis estimates the total burned area in the ROI, providing quantitative data for post-fire recovery planning.  

## Significance  
This analysis demonstrates the integration of multi-source remote sensing data for wildfire monitoring and impact assessment. It highlights the importance of satellite-based technologies in addressing environmental challenges, offering valuable insights for:  
- **Emergency response and disaster management.**  
- **Ecosystem restoration and resource allocation.**  
- **Long-term environmental monitoring and climate change studies.**  

## Conclusion  
Wildfire detection and severity mapping using VIIRS and Landsat 9 data in Google Earth Engine provides a scalable and efficient solution for monitoring wildfire impacts. The results can inform decision-making processes, enabling timely and effective recovery efforts. This study underscores the critical role of geospatial technology in environmental management and disaster resilience.  
