# bank_system_simple
How to create a bank system to check your balance, deposit and do withdrawls.

menu = """[d] Deposit [w] Withdraw [s] Statement [q] Quit

=> """

balance = 0
limit = 500
statement = ""
withdraw = 0
limit_withdraw = 3

while True:
    
    option = input(menu)
    
    if option == "d":
       value = float(input("Inform the valur of deposit: "))
       if value >0:
            balance += value 
            statement += f"Deposit: $ {value:.2f}\n"
       else:
            print ("Operation failed!The value informed is invalid.")
    
    elif option == "w":
            value = float(input("Informe the withdraw value: "))
            balance_exceeded = value > balance
            
            limit_exceeded = value > limit
            
            withdraw_exceeded = withdraw >= limit_withdraw
            
            if balance_exceeded:
                print("Operation failed! You don't have balance enough.")
            elif limit_exceeded:
                print("Operation failed! You don't have limit enough")
            elif withdraw_exceeded:
                print ("Operation failed! Maximum limit of withdraw exceeded.")
        
            elif value > 0:
                balance -= value
                statement += f"Saque: $ {value:.2f}\n"
                withdraw += 1
            else:
                print("Operation failed! The value informed is invalid.")
    
    elif option == "s":
        print("\n============ STATEMENT ============")
        print("Movements were not realized" if not statement else statement)
        print(f"\nBalance: $ {balance:.2f}")
        print("===================================")
        
    elif option == "q":
        break
    
    else:
        print("Invalid operation, please select again an operation valid")
    
    
            
        
            
            
    
    
