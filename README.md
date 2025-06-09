from  tkinter import *

#частина коду для роботи калькулятора
def add_digit(digit):  # функція, що додає цифру або символ до поля вводу
    entry.insert(END, digit)  # вставляє передану цифру/символ в кінець рядка у полі вводу

def calculate():  # функція, яка виконує обчислення виразу, введеного в поле
    try:
        result = eval(entry.get())  # отримує текст з поля вводу та обчислює його як математичний вираз
        entry.delete(0, END)  # очищає поле вводу
        entry.insert(END, str(result))  # вставляє результат обчислення назад у поле вводу як текст
    except:  # якщо сталася помилка під час обчислення (наприклад, неправильний вираз)
        entry.delete(0, END)  # очищає поле вводу
        entry.insert(END, "Помилка")  # виводить слово "Помилка" у поле вводу

def clear():  # функція для очищення поля вводу
    entry.delete(0, END)  # видаляє весь текст у полі вводу (від позиції 0 до кінця)

Window = Tk()
Window.title("Калькулятор") #назва вікна 
Window.geometry("320x365") #розміри вікна

#________________________________________________________________________________________________________________________________________________________________#
#інтерфейс калькулятора
entry = Entry(Window, width=16, font=('Arial', 24), bd=5, justify='right')# Поле для відображення введених чисел і результату
entry.grid(row=0, column=0, columnspan=4, pady=10)

#книпки
#ряд 1
btn7 = Button(Window, text="7", width=5, height=2, font=("Arial", 18), command= lambda: add_digit("7")) #додає цифру 7 в рядок
btn7.grid(row=1, column=0)
btn8 = Button(Window, text="8", width=5, height=2, font=("Arial", 18), command= lambda: add_digit("8")) #додає цифру 8 в рядок
btn8.grid(row=1, column=1)
btn9 = Button(Window, text="9", width=5, height=2, font=("Arial", 18), command= lambda: add_digit("9")) #додає цифру 9 в рядок
btn9.grid(row=1, column=2)
btn_plus = Button(Window, text="+", width=5, height=2, font=("Arial", 18), command= lambda: add_digit("+")) #додавання
btn_plus.grid(row=1, column=3)

#ряд 2
btn4 = Button(Window, text="4", width=5, height=2, font=("Arial", 18), command= lambda: add_digit("4")) #додає цифру 4 в рядок
btn4.grid(row=2, column=0)
btn5 = Button(Window, text="5", width=5, height=2, font=("Arial", 18), command= lambda: add_digit("5")) #додає цифру 5 в рядок
btn5.grid(row=2, column=1)
btn6 = Button(Window, text="6", width=5, height=2, font=("Arial", 18), command= lambda: add_digit("6")) #додає цифру 6 в рядок
btn6.grid(row=2, column=2)
btn_minus = Button(Window, text="-", width=5, height=2, font=("Arial", 18), command= lambda: add_digit("-")) #віднімання
btn_minus.grid(row=2, column=3)

#ряд 3 
btn1 = Button(Window, text="1", width=5, height=2, font=("Arial", 18),command= lambda: add_digit("1")) #додає цифру 1 в рядок
btn1.grid(row=3, column=0)
btn2 = Button(Window, text="2", width=5, height=2, font=("Arial", 18), command= lambda: add_digit("2")) #додає цифру 2 в рядок
btn2.grid(row=3, column=1)
btn3 = Button(Window, text="3", width=5, height=2, font=("Arial", 18), command= lambda: add_digit("3")) #додає цифру 3 в рядок
btn3.grid(row=3, column=2)
btn_division = Button(Window, text="/", width=5, height=2, font=("Arial", 18), command= lambda: add_digit("/")) #ділення
btn_division.grid(row=3, column=3)

#ряд 4
multiplication = Button(Window, text="*", width=5, height=2, font=("Arial", 18), command= lambda: add_digit("*")) #множення
multiplication.grid(row=4, column=3)
C = Button(Window, text="C", width=5, height=2, font=("Arial", 18), command=clear) #повністю очищує рядок
C.grid(row=4, column=0)
btn0 = Button(Window, text="0", width=5, height=2, font=("Arial", 18), command= lambda: add_digit("0")) #додає цифру 0 в рядок
btn0.grid(row=4, column=1)
end = Button(Window, text="=", width=5, height=2, font=("Arial", 18), command=calculate) #обчислює рядок
end.grid(row=4, column=2)
#________________________________________________________________________________________________________________________________________________________________#

Window.mainloop() #закриваєм вікно
