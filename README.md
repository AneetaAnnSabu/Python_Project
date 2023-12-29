https://drive.google.com/file/d/1moeNkRI_YkvMkkn9LzVkwcP43vhUmJH_/view?usp=drive_link
class Banking_system:
    def __init__(self,pin):
        self.account={}
        self.transaction_history=[]
        self.balance=0
        self.pin = pin
    def creating(self,account_number,holder_name,entered_pin,balance=0):
        if account_number in self.account:
            print('Account already existed')
        else:
            self.account[account_number] = {"holder_name": holder_name, "balance": balance}
            print('New account created successfully')

    def login(self,account_number,entered_pin):
            if self.pin == entered_pin:
                print('Logged in successfully')
            else:
                raise 'Incorrect Pin'
    def deposit(self,account_number,amount):
        self.balance+=amount
        if amount>=1:
            print(f"deposited{amount}")
            print(f'Current balance:{self.balance}')
            self.transaction_history.append(f'deposited:{amount}')
    def withdraw(self,account_number,amount):
        self.balance-=amount
        if amount<=0:
            print('Enter a positive amount')
        elif self.balance<amount:
            print('Insufficient balance')
        else:
            print(f'Withdrawal successful')
            print(f'Current balance :{self.balance}')
            self.transaction_history.append(f'Withdrawn:{amount}')
    def display_transaction_history(self):
        print("transaction history :")
        for i in self.transaction_history:
            print(i)
object1=Banking_system(1234)
object1.creating(1234567,'Aneeta',1234)
object1.login(123456,1234)
object1.deposit(1234567,2000)
object1.withdraw(1234567,1000)
object1.display_transaction_history()

