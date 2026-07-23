# 🚕 Uber NCR Ride Analytics Engine (NumPy Native)

A high-performance data engineering and analytics pipeline built entirely from scratch using native NumPy vectorization. This project processes a massive dataset of 150,000+ Uber/NCR ride bookings, demonstrating advanced array manipulation, handling missing data, and extracting business-critical metrics with zero iterative Python loops.

## 🚀 Key Engineering Paradigms Used

* **Data Imputation & Memory Management:** Extracted core vectors from raw CSVs and applied `np.nan_to_num()` to sanitize missing financial and distance records, ensuring safe mathematical operations.
* **Vectorized Feature Engineering:** Dynamically calculated derived metrics like `Revenue_Per_KM` using `np.where()` to mathematically bypass division-by-zero errors on zero-distance trips.
* **Multi-Dimensional Matrix Construction:** Vertically stacked independent 1D arrays into a consolidated 2D analytics matrix using `np.column_stack()`.
* **Complex Boolean Masking:** Deployed multi-condition bitwise operators (`&`, `|`) for targeted data filtering, such as isolating high-tier valid rides and auditing driver-customer rating anomalies via `np.abs()`.
* **Statistical Outlier Isolation:** Utilized `np.percentile()` to isolate extreme distance anomalies (99th percentile) without standard iterative checks.
* **Production Sorting & Structural Parsing:** Leveraged `np.argsort()` with reverse slicing (`[::-1][:10]`) to rank top-grossing trips and dynamically map their indices back to the master dataset for contextual feature extraction.

## 📂 Project Structure
* `project-2-numpy.ipynb`: The core Jupyter Notebook containing the zero-loop vectorized analytics pipeline.
* `ncr_ride_bookings.csv`: The raw dataset containing 150,000+ transactional ride logs.

## 🛠️ Tech Stack
* **Python 3.x**
* **NumPy** (Core Engine)
* **Pandas** (Strictly for initial file I/O operations)
