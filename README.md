## I. Labeling Convention

| Class ID | Class Name     | Description                                                                 |
|----------|----------------|-----------------------------------------------------------------------------|
| 0        | Motorbike       | All types of 2-wheeled motor vehicles regardless of engine capacity.         |
| 1        | Car             | Passenger vehicles such as sedan, hatchback, SUV, crossover, pickup, van.   |
| 2        | Bus             | Includes public buses and long-distance coaches.                            |
| 3        | Truck   Trailer Truck        | Cargo vehicles: small, medium trucks, and large cargo vans; Container trucks, tractor-trailers, and articulated vehicles.               |

---

## II. Labeling Guidelines

### **0 - Motorbike**
- **Key features**: Two wheels, often with a visible rider (helmeted or not).
- **Rules**:
  - Label all two-wheeled motor vehicles.
  - Only label when both wheels are clearly identifiable.
  - Bounding box should include both the vehicle and the rider.

### **1 - Car**
- **Key features**: Four wheels, compact or mid-size.
- **Rules**:
  - Includes sedan, hatchback, SUV, crossover, small passenger vans, pickup trucks.
  - Excludes large cargo vans and trucks.
  - Bounding box must fully contain the entire vehicle.

### **2 - Bus**
- **Key features**: Large body, long chassis, many windows.
- **Rules**:
  - Includes city buses and coaches (29–45 seats).
  - Must distinguish from long vans or large cargo trucks.
  - Bounding box should closely fit the whole bus body.

### **3 - Truck**
- **Key features**: Cargo body, often taller than standard cars, enclosed or open cargo area; large cabin with attached or towed cargo unit.
- **Rules**:
  - Includes small to medium trucks (1.25–3 tons), cargo vans.
  - Excludes trailer trucks or container haulers.
  - Differentiate from pickups based on cargo compartment size.
  - Includes tractor-trailers, containers, and all large articulated cargo vehicles.
  - Bounding box must cover both the truck head and the trailer if connected

---

## III. Model Performance Summary

### 📌 YOLOv10 Models Comparison (Input Size: 512x512, Batch: 16)

| Version      | Model       | Epochs | Data Size         | mAP@0.5 | mAP@0.5:0.95 |
|--------------|-------------|--------|--------------------|---------|--------------|
| `model_ver1` | yolov10s.pt | 50     | Original dataset    | 0.888   | 0.747        |
| `model_ver2` | yolov10s.pt | 100    | Original dataset    | 0.9116  | 0.7686       |
| `model_ver3` | yolov10s.pt | 200    | Original dataset    | 0.9341  | 0.7974       |
| `model_ver4` | yolov10n.pt | 200    | Original dataset    | 0.8929  | 0.7484       |
| `model_ver5` | yolov10n.pt | 300    | New data (1K images) | 0.8864  | 0.707        |
| `model_ver6` | yolov10s.pt | 200    | New data (1K images) | 0.953   | 0.768        |
| `model_ver7` | yolov10m.pt | 180    | New data (1K images) | 0.8356  | 0.7997       |

> - `mAP@0.5`: Mean Average Precision at IoU threshold 0.5  
> - `mAP@0.5:0.95`: Averaged across multiple IoU thresholds (stricter evaluation)

---

Feel free to adjust depending on your target audience (developers, researchers, etc.).
