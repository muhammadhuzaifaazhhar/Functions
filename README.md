# Functions
def calculate_total(quantity, price):
    total = quantity * price
    if total > 10000.00:
        total *= 0.9  # Apply a 10% discount for totals over $10,000.00
    return total

def main():
    extended_price = 0.0

    try:
        while True:
            # User input for quantity and price
            quantity = int(input("Enter quantity (Ctrl+Z to stop): "))
            price = float(input("Enter price: $"))

            # Calculate total
            total = calculate_total(quantity, price)

            # Display quantity, price, and total
            print(f"Quantity: {quantity}, Price: ${price:.2f}, Total: ${total:.2f}")

            # Update the extended price
            extended_price += total

    except EOFError:
        # Display the extended price when the user stops input (Ctrl+Z)
        print(f"\nExtended Price: ${extended_price:.2f}")

if __name__ == "__main__":
    main()
