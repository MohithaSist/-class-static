# -class-static

class Book:
    rs=500
    def __init__(self,name,author,publish):
        self.name=name
        self.author=author
        self.publish=publish
    def shop(self):
        buy=f"name : {self.name}\nauthor : {self.author}\npublish : {self.publish}"
        return(buy)
    def rate(self,amount):
        self.rs=self.rs-amount

    @classmethod
    def change_rate(cls,amount):
        cls.rs=amount
    @classmethod
    def book_data(cls,data):
        name,author,publish=data.split(",")
        return cls(name,author,publish)
    @staticmethod
    def book_dep(dep):
        available_dep=['ECE','IT']
        if dep in available_dep:
            return True
        else:
             return False
    
    
data=("AIC,Mohitha,2030")
book3=Book.book_data(data)
Book.change_rate(700)


#book1.change_rate(700)        
#data=("name,author,publish").split(" ")

#name,author,publish= "AIC,Mohitha,2030".split(",")
#book3=Book(name,author,publish)
    
book1=Book("control systems","Naggor kani",1993)
book2=Book("Dsp","Nagrath",1999)
book1.rate(200)
print(book1.name)
print(book2.publish)
print(book1.shop())
print(book1.rs)
print(book2.rs)
#print(name,author,publish)
print(book3.author)
print(book3.publish)
print(book1.book_dep('ECE'))
print(book1.book_dep("IT"))
print(book1.book_dep('mech'))
