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
