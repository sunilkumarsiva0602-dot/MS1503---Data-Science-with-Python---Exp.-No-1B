# Experiment 1.B : Product Price Analysis Using Python Functions

## Aim
To analyze quarterly product sales data across multiple products and quarters using 2D NumPy arrays and Python statistical functions.

## Algorithm

1. **Start** the program.
2. **Import Library**: Import the `numpy` module as `np` for numerical array operations.
3. **Initialize 2D Sales Matrix**: Create a $3 \times 4$ NumPy array `sales` containing quarterly sales figures for 3 products across 4 quarters.
4. **Compute Product-Wise Totals**: Calculate the sum of sales across columns (`axis=1`) for each product using `np.sum(sales, axis=1)`.
5. **Compute Quarter-Wise Totals**: Calculate the sum of sales across rows (`axis=0`) for each quarter using `np.sum(sales, axis=0)`.
6. **Compute Overall Statistical Metrics**:
   * Calculate the overall mean sales across all entries using `np.mean(sales)`.
   * Identify the maximum sales figure using `np.max(sales)`.
   * Identify the minimum sales figure using `np.min(sales)`.
7. **Display Analysis Summary**: Print the original sales matrix, product-wise totals, quarter-wise totals, overall average, highest sale, and lowest sale.
8. **Stop** the program.
## Program
    
    import numpy as np
    
    
    def analyze_sales(sales):
        product_totals = np.sum(sales, axis=1)
        quarter_totals = np.sum(sales, axis=0)
        mean_sales = np.mean(sales)
        max_sales = np.max(sales)
        min_sales = np.min(sales)

    return {
        "product_totals": product_totals,
        "quarter_totals": quarter_totals,
        "mean_sales": mean_sales,
        "max_sales": max_sales,
        "min_sales": min_sales,
    }


    def main():
        # Step 1: Create 2D array (Rows = Products, Columns = Quarters)
        sales = np.array([
            [12000, 15000, 14000, 16000],  # Product 1 (Q1-Q4)
            [9500, 11000, 10500, 12500],   # Product 2 (Q1-Q4)
            [18000, 17500, 19000, 21000],  # Product 3 (Q1-Q4)
        ])

    # Step 2: Calculate Aggregations and Summary Statistics
    stats = analyze_sales(sales)

    # Step 3: Display Summary
    print("=== Quarterly Product Sales Analysis ===\n")
    print("Sales Matrix (Rows = Products, Columns = Q1..Q4):")
    print(sales)

    print("\nProduct-Wise Total Sales:")
    for idx, total in enumerate(stats["product_totals"], start=1):
        print(f"  Product {idx}: {total:.2f}")

    print("\nQuarter-Wise Total Sales:")
    for q_idx, total in enumerate(stats["quarter_totals"], start=1):
        print(f"  Q{q_idx}: {total:.2f}")

    print("\nOverall Summary Statistics:")
    print(f"  Overall Mean Sales : {stats['mean_sales']:.2f}")
    print(f"  Highest Sale       : {stats['max_sales']:.2f}")
    print(f"  Lowest Sale        : {stats['min_sales']:.2f}")


if __name__ == "__main__":
    main()

## Output
<img width="537" height="522" alt="image" src="https://github.com/user-attachments/assets/92b0a277-4fb0-49b7-9c84-1619147e756b" />


## Result

The program successfully analyzes quarterly product sales using 2D NumPy arrays and Python statistical aggregation functions.
