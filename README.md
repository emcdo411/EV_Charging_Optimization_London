# **EV Charging Optimization in Greater London - A Case Study**

## **Overview**
This case study demonstrates how advanced data analysis and machine learning techniques can optimize the electric vehicle (EV) charging infrastructure in Greater London. With a focus on reducing costs, enhancing the customer experience, and improving the environmental sustainability of the EV network, this project models three critical components: **Optimized Charging Network**, **Cost Reductions for Customers**, and **Environmental Benefits of Renewable Energy Integration**.

The aim of this study is to present actionable insights for EV network operators, like **Hitachi Digital Services**, on how to improve the EV charging ecosystem through smarter systems and data-driven decisions.

---

## **What Was Accomplished**

This case study utilizes mock data and generates three different visualizations to model the state of EV charging networks, cost savings for customers, and the impact of renewable energy sources on the network's environmental footprint. The following goals were achieved:

- **Optimized Charging Network**: Visualized charging demand over time to help identify patterns and opportunities for optimization.
- **Cost Reductions for Customers**: Created a 3D scatter plot representing the relationship between energy usage, cost savings, and time of day.
- **Environmental Benefits**: Mapped the renewable energy usage across different charging stations to gauge the environmental impact of the network.

These visualizations provide valuable insights for stakeholders, enabling them to make more informed decisions about EV charging infrastructure investments, pricing models, and environmental strategies.

---

## **Why It Matters**

As electric vehicle adoption continues to rise globally, optimizing the charging infrastructure becomes paramount to support the increasing demand for EVs. For cities like London, ensuring that charging stations are strategically located, cost-efficient, and integrated with renewable energy sources can significantly reduce operational costs, decrease carbon emissions, and improve the customer experience. This case study showcases how data analytics can directly contribute to these improvements by providing clear, actionable insights.

### **Key Benefits of This Case Study**
- **Cost Reduction**: By analyzing demand patterns and cost savings data, charging networks can optimize their infrastructure, leading to lower costs for consumers.
- **Sustainability**: Integrating renewable energy sources into the EV network reduces the environmental impact of the growing EV sector.
- **Data-Driven Decision Making**: The project emphasizes the power of data analytics in shaping the future of energy and transportation systems.

---

## **Visualizations**

### **1. Optimized Charging Network Demand Over Time**
The first graph visualizes the energy demand at charging stations over the course of 30 days. This line plot helps identify demand spikes, providing insights into when charging stations are under the most stress and need to be optimized.

```r
# Line plot for Optimized Charging Network (Charging Demand over Time)
ggplot(charging_network, aes(x = day, y = demand)) +
  geom_line(color = "blue", size = 1) +
  labs(title = "Optimized Charging Network Demand", x = "Date", y = "Energy Demand (kWh)") +
  theme_minimal()
```

### **2. Cost Reductions for Customers - 3D Plot**
This 3D scatter plot represents the relationship between energy used (in kWh), the cost savings (in GBP), and the time of day. By visualizing the data in three dimensions, we can better understand how charging behaviors vary throughout the day and how these differences impact cost savings.

```r
# 3D Scatter plot for Cost Reductions with Energy Usage, Cost Savings, and Time of Day
fig <- plot_ly(cost_reductions, 
               x = ~energy_used_kWh, 
               y = ~cost_savings, 
               z = ~time_of_day, 
               type = "scatter3d", 
               mode = "markers",
               color = ~time_of_day,
               colors = c('red', 'green', 'blue'),
               marker = list(size = 5))

fig <- fig %>% layout(title = "Cost Reductions for Customers",
                      scene = list(xaxis = list(title = 'Energy Used (kWh)'),
                                   yaxis = list(title = 'Cost Savings (GBP)'),
                                   zaxis = list(title = 'Time of Day')))
fig
```

### **3. Environmental Benefits of Renewable Energy - 2D Map**
Using a 2D map of Greater London, this visualization shows the distribution of EV charging stations with renewable energy percentages. It highlights which stations are using high amounts of renewable energy and how this can contribute to environmental sustainability.

```r
# Map showing Charging Stations and Renewable Energy Percentages using leaflet
leaflet(charging_stations_sf) %>%
  addTiles() %>%
  addCircleMarkers(radius = 8, 
                   color = ~ifelse(renewable_energy_pct > 50, "green", "red"), 
                   popup = ~paste("Station", station_id, "<br>", 
                                  "Renewable Energy: ", round(renewable_energy_pct, 2), "%")) %>%
  addLegend(position = "topright", 
            colors = c("green", "red"), 
            labels = c("High Renewable Energy", "Low Renewable Energy"),
            title = "Renewable Energy %")
```

---

## **Conclusion**

This case study highlights the significant potential of data science and machine learning in optimizing the electric vehicle infrastructure. By applying advanced techniques to analyze charging demand, customer costs, and the environmental impact of renewable energy, we can make informed decisions that improve efficiency, reduce costs, and minimize carbon footprints.

The insights derived from these visualizations are crucial for stakeholders like **Hitachi Digital Services** and other organizations involved in the energy and transportation sectors. The findings empower them to make smarter investments in EV infrastructure, contributing to a greener, more sustainable future.

---

## **Getting Started**

### **Prerequisites**
To run the analysis and generate the visualizations, ensure that the following R packages are installed:
- `ggplot2`
- `plotly`
- `dplyr`
- `sf`
- `leaflet`

You can install them using the following command in R:

```r
install.packages(c("ggplot2", "plotly", "dplyr", "sf", "leaflet"))
```

### **Running the Code**
1. Clone this repository.
2. Open the provided R script in RStudio.
3. Run each section of code to generate the visualizations.

For detailed instructions on how to set up and run the code, refer to the [README.md](https://github.com/your-username/EV_Charging_Optimization_London/blob/main/README.md).

---

## **Acknowledgments**
- Data used in this case study is simulated for the purpose of demonstration. In a real-world scenario, data from EV network operators would be required.
- Special thanks to **Hitachi Digital Services** for the opportunity to present this case study.

---

## **Contact**
For more information or questions, feel free to reach out to me at [moe.mcdonald@gmail.com](moe.mcdonald@gmail.com). 

--- 

**#EVCharging #DataScience #MachineLearning #EnergyOptimization #Sustainability #RenewableEnergy #HitachiDigitalServices #TransportationTech**
