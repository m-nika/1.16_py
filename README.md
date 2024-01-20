class MyClass:
    @classmethod
    def factorial(cls, number):
        if number < 0:
            raise ValueError('Number must be non-negative.')
        if number == 0 or number == 1:
            return 1
        else:
            return number * cls.factorial(number - 1)

number = 10
result = MyClass.factorial(number)
print(f"the factorial of {number} is: {result}")


class BankAccount:
    total_accounts = 0

    def __init__(self, owner, balance):
        self.owner = owner
        self.balance = balance
        BankAccount.total_accounts += 1

    def show_balance(self):
        print(f'balance of client {self.owner}: {self.balance}')

    @classmethod
    def get_total_accounts(cls):
        return cls.total_accounts

    @staticmethod
    def validate_amount(amount):
        return amount > 0

acc1 = BankAccount('mark', 1230)
acc2 = BankAccount('john', 895)

acc1.show_balance()
acc2.show_balance()

total_accounts = BankAccount.get_total_accounts()
print(f'total number of accounts: {total_accounts}')

amount1 = 589
amount2 = -12

print(f'is {amount1} a valid amount? {BankAccount.validate_amount(amount1)}')
print(f'is {amount2} a valid amount? {BankAccount.validate_amount(amount2)}')



