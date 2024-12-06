def currency_converter(amount, from_currency, to_currency):
    exchange_rates = {
        'USD': 1.0,  
        'THB': 34.5,  
        'EUR': 0.92,  
        'JPY': 147.0  
    }
    
    if from_currency not in exchange_rates or to_currency not in exchange_rates:
        return "Your selected currency information is not available."
    
    amount_in_usd = amount / exchange_rates[from_currency]
    converted_amount = amount_in_usd * exchange_rates[to_currency]
    
    return converted_amount

def main():
    print("Currency conversion program")
    print("Supported currencies: USD, THB, EUR, JPY")
    
    from_currency = input("Please enter originating currency.: ").upper()
    to_currency = input("Please enter destination currency.: ").upper()
    try:
        amount = float(input("Please enter the amount.: "))
        result = currency_converter(amount, from_currency, to_currency)
        
        if isinstance(result, str):
            print(result)
        else:
            print(f"\n{amount:.2f} {from_currency} = {result:.2f} {to_currency}")
    except ValueError:
        print("Please enter the amount in numbers.")

if __name__ == "__main__":
    main()
