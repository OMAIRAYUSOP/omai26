# Book class
from multiprocessing.util import is_abstract_socket_namespace


class Book:
    def __init__(self, title, author, year, isbn, pages):
        self.title=title
        self.author=author
        self.year=year
        self.isbn=isbn
        
    def __str__(self):
        return f" Title:{self.title}, Author:{self.author}, Year:{self.year}, ISBN:{self.isbn}"
    
# Library Management System
class Library:
    def __init__(self):
        self.book=[]
        
    def __add_book(self, title, author, year, isbn):
        new_book=Book(title, author, year, isbn)
        self.book.append(new_book)
        print("Book added successfully!\n")
        
    def display_books(self):
        if not self.books:
            print("No books in the library.\n")
        else:
            print("Books in the library:")
            for book in self.books:
                print(book)
                print()
             
    def search_books(self, title):
        found_books=[book for book in self.books if title.lower()in book.title.lower()]
        if not found_books:
            print("No matching book found.\n")
        else:
            print("Search Results:")
            for book in found_books:
                print(book)
                print()
                
#Main Program
def main():
    library=Library()
    
while True:
    print("\nLibrary Book Management System")
    print("1. Add Book")
    print("2. Display All Books")
    print("3. Search Book by Title")
    print("4. Exit")
    choice=input("Enter your choice (1-4):")
    
    if choice=="1":
        title=input("Enter book title:")
        author=input("Enter author name:")
        year=int(input("enter year publication:"))
        isbn=input("Enter International Standard Book Number:")
        library.add_book(title, author, year, isbn)
    elif choice=="2":
        library.display_books()
    elif choice=="3":
        search_title=input("Enter title to search:")
        library.search_books(search_title)
    elif choice=="4":
        print("Thank you for using the library management system.")
        break
    else:
        print("Invalid choice! Please try again.\n")
        if __name__=="__main__":
            main()
            
            
        


