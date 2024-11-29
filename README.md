import msvcrt, os

def ExecuteOperation():
    if menu_number==1:
        
        while True:
            os.system('cls')
            print("\nMULTIPLICATION")
            print("----------------")

            n1=float(input("\nInput 1st number: "))
            n2=float(input("Input 2nd number: "))

            result = n1*n2

            print(f"\n{n1} x {n2} = {result}")

            while True:

                try_again = input("\nDo you want to try again [y/n]? ") 

                if try_again=='y' or try_again=='Y':
                    break
                elif try_again=="n" or try_again=='N':
                    return
                else:
                    print("Please select only between 'y' and 'n'.")
    
    elif menu_number==2:

        div_menu = True
        while div_menu:
            os.system('cls')

            print("\nDIVISION")
            print("----------------")

            n1=float(input("\nInput 1st number: "))
            n2=float(input("Input 2nd number: "))

            result = n1/n2

            print(f"\n{n1} / {n2} = {result}")

            yes_or_no = True
            while yes_or_no:
                    
                    try_again = input("\nDo you want to try again [y/n]? ") 

                    if try_again=='y' or try_again=='Y':
                        yes_or_no = False
                    elif try_again=="n" or try_again=='N':
                        yes_or_no = False
                        div_menu = False
                    else:
                        print("Please select only between 'y' and 'n'.")
    
    elif menu_number==3:
        print("\nADDITION")
        print("----------------")
    
    elif menu_number==4:
        print("\nSUBTRACTION")
        print("----------------")

def menu_nav():

    global menu_number
    menu_number = 1

    while True:

        os.system('cls')
        print("BASIC CALCULATOR\n")

        # if menu_number == 1:
        #     print("\033[92m►\033[0m Multiplication")
        # else:
        #     print("  Multiplication")
        
        # if menu_number == 2:
        #     print("\033[92m►\033[0m Division")
        # else:
        #     print("  Division")
        
        # if menu_number == 3:
        #     print("\033[92m►\033[0m Addition")
        # else:
        #     print("  Addition")
        
        # if menu_number == 4:
        #     print("\033[92m►\033[0m Subtraction")
        # else:
        #     print("  Subtraction")
        
        # if menu_number == 5:
        #     print("\033[92m►\033[0m Exit")
        # else:
        #     print("  Exit")


        if menu_number == 1:
            print("\033[30m\033[47mMultiplication\033[0m")
        else:
            print("Multiplication")
        
        if menu_number == 2:
            print("\033[30m\033[47mDivision\033[0m")

        else:
            print("Division")
        
        if menu_number == 3:
            print("\033[30m\033[47mAddition\033[0m")

        else:
            print("Addition")
        
        if menu_number == 4:
            print("\033[30m\033[47mSubtraction\033[0m")

        else:
            print("Subtraction")
        
        if menu_number == 5:
            print("\033[30m\033[47mExit\033[0m")

        else:
            print("Exit")


        # wait for any key pressed by the user
        key_pressed = msvcrt.getch()

        # if arrow key is pressed
        if key_pressed ==  b"\xe0":

            # check the direction of the arrow
            key_pressed = msvcrt.getch()

            # if down arrow is pressed and not yet at the bottom/last item of the menu
            if key_pressed == b"P" or key_pressed==b"M":
                
                if menu_number==5:
                    menu_number = 1
                else:
                    # increment value of menu_number by 1
                    menu_number = menu_number + 1
            
            # if up arrow is pressed and not yet at the top/first item of the menu
            elif key_pressed in [b"H",  b"K"]:
                
                if menu_number == 1:
                    
                    menu_number = 5

                else:

                    # decrement value of menu_number by 1
                    menu_number -= 1
        
        elif key_pressed == b"\r":

            if menu_number in [1,2,3,4]:
                
                ExecuteOperation()
                
            else:

                print("\nThank you for using my BASIC CALCULATOR")
                break
            


    
def main():
    menu_nav()


main()

