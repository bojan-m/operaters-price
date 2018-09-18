#test values
operators =  {'Operator A' : {'1' : 0.9, '268' : 5.1, '46' : 0.17, '4620' : 0.23},
              'Operator B' : {'1' : 0.8, '2' : 1.3, '44' : 0.5, '46' : 0.2 }}

if __name__ == "__main__":
    #Input number
    input_number = input("Enter a number to dial: ")
    #Initializing values for the final result
    operator = None
    cheapestCall = [['111111111', 9999.9]]
    #Loop through dictionary items
    for value in operators.items():
        j=1 #reset the while counter for every new item in list
        while j < len(input_number)+1: #while loop for the length of the number
            if input_number[0:j] in value[1].keys(): #searching for the part of the prefix in prefix keys
                # checking if the value of the key is lower than the previous value in the final list
                # and if the previous entry has shorter prefix (When several prefixes match the same number, the longest one should be used)
                if value[1][input_number[0:j]] < cheapestCall[-1][1] and len(input_number[0:j]) <= len(cheapestCall[-1][0]):
                    cheapestCall.append([input_number[0:j], value[1][input_number[0:j]]])
                    operator = value[0]
                elif len(input_number[0:j]) > len(cheapestCall[-1][0]):
                    cheapestCall.append([input_number[0:j], value[1][input_number[0:j]]])
                    operator = value[0]
            j += 1
    #checking the content of operator after for loop to see if we have a match
    if operator == None:
        print('There isn\'t an operater in our database that can route a call to desired number.')
    else:
        print('The chepest operator to call the desired number is ' + operator + ' for the price of: ' + str(cheapestCall[-1][1]) + '/min')


