# bhuvan18
class ATM:
  def __init__(self):
    self.pin =''
    self.balance = 0
    self.menu()
#self is the dummy object
#self can be used for multiple objects
  def menu(self):
    user_input=input("""
  Hi how can I help you?
    1. Press 1 to Create/Change PIN and set initial balance.
    2. Press 2 to withdraw cash.
    3. Press 3 to deposit cash.
    4. Press 4 to check balance.
    5. Press 5 to exit.
    """)
    if user_input == '1':
       self.create_pin()
    elif user_input == '2':
      self.withdraw()
    elif user_input == '3':
      self.deposit()
    elif user_input == '4': 
      self.check_balance()
    elif user_input == '5':
      self.exit()
    else:
      print("Invalid choice. Please try again.")
      self.menu() 

  def create_pin(self):
        user_pin=input("please enter your pin: ")
        self.pin=user_pin
        user_balance=int(input("please enter your initial balance: "))
        self.balance=user_balance
        print("PIN created and balance set successfully!")
        self.menu()

  def withdraw(self):
    ask2=input("enter your pin: ")
    if ask2==self.pin:
      amount=int(input("enter your amount to withdraw: "))
      if amount>self.balance:
        print("Insufficient funds!")
      else:
       self.balance -= amount
       print(f'Collect your cash: {amount}. Your remaining balance is: {self.balance}')
       self.menu()
    else:
      print("Incorrect PIN!")
      self.menu()

  def deposit(self):
    ask3=input("enter your pin: ")
    if ask3==self.pin:
      amount2=int(input("enter the amount to deposit: "))
      self.balance=self.balance+amount2
      print(f"Your balance has been updated. Your new balance is: {self.balance}")
      self.menu()
    else:
      print("Incorrect PIN!")
      self.menu()

  def check_balance(self):
    print(f"Your current balance is: {self.balance}")
    self.menu()

  def exit(self):
    print("Thank you for using the ATM!")
    
