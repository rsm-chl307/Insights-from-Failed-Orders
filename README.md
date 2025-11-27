# Insights from Failed Orders — Project Tasks

This data project is based on a take-home assignment used for data science recruiting at Gett.

Gett (formerly GetTaxi) is an Israeli-developed technology platform focused on corporate Ground Transportation Management (GTM). Clients can order taxis through the app, and drivers can accept the rides (“offers”). When a client clicks the *Order* button, the system searches for relevant drivers and offers them the order.  
In this project, we investigate matching metrics for orders that **did not complete successfully**, i.e., the customer did not end up getting a car.

---

## 📌 Assignment Tasks

### **1. Failure Reasons Distribution**
Build the distribution of failed orders according to the following categories:

- Cancellations **before** driver assignment  
- Cancellations **after** driver assignment  
- Orders **rejected** by the system  

Analyze the resulting plot and identify **which category has the highest number of failed orders**.

---

### **2. Failed Orders by Hour**
Plot the distribution of failed orders by hour of day.

Questions to analyze:
- Are there hours with unusually high failure rates?
- Which hours represent the **largest failure spikes**?
- Provide reasonable explanations for these trends.

---

### **3. Average Time to Cancellation (With vs Without Driver)**
Plot the average cancellation time (in seconds), grouped by hour, for:
- Orders **with** a driver assigned  
- Orders **without** a driver assigned  

If outliers exist, remove them for clarity.  
Discuss whether meaningful conclusions can be drawn from the plot.

---

### **4. Average ETA Distribution by Hour**
Plot the distribution of average ETA values by hour.

Explain possible interpretations of this plot (e.g., demand surges, traffic patterns, supply shortage).

---

### **5. BONUS – Hexagon Spatial Analysis**
Using the `h3` and `folium` libraries:

1. Aggregate orders into **size 8 H3 hexes**  
2. Determine how many hexes contain **80% of all orders**
3. Visualize these hexes on a map
4. Color the hexes by the **number of failed orders**

---

## 📂 Data Description

### **Dataset 1: `data_orders`**

| Column | Description |
|--------|-------------|
| `order_datetime` | Timestamp of the order |
| `origin_longitude` | Longitude of the order origin |
| `origin_latitude` | Latitude of the order origin |
| `m_order_eta` | Time (in seconds) until estimated arrival |
| `order_gk` | Order ID |
| `order_status_key` | Status code: `4` = cancelled by client, `9` = cancelled by system (reject) |
| `is_driver_assigned_key` | Whether a driver was assigned |
| `cancellation_time_in_seconds` | Time elapsed before cancellation |

---

### **Dataset 2: `data_offers`**

| Column | Description |
|--------|-------------|
| `order_gk` | Order ID (joins with `data_orders`) |
| `offer_id` | Offer ID issued to a driver |

---

## 📝 Practical Notes

Your solution must reflect the **entire analysis process**, including:
- Data loading  
- Data preparation / cleaning  
- Exploratory analysis  
- Visualization  
- Interpretation of findings  

The clarity and structure of your code are more important than just producing the final plots.

