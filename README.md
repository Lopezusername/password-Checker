# password-Checker
user freindly password checker
print("Hello User Please Create A Valid Password. \nInclude at least one lowercase character \nAt least one uppercase character \nAt least one number \nAnd at least one special character.")

# Create a password checker using 8 characters with atleast one uppercase, lowercase and special character
# special character and a minimum of 8 characters long

password = input("Type your password:")

lowercase = False                                                         # checks lowercase letters first rule
for character in password:
    if character in "abcdefghijklmnopqrstuvwxyz":
        lowercase = True

if lowercase == True:
    print("Your password contains at least 1 lowercase character.")      # if lowercase is their it's good if not
elif lowercase == False:                                                 # prints need a lowercase letter
    print("Your password needs at least 1 lowercase character.")

uppercase = False                                                        # checks for uppercase letter second rule
for character in password:                                               # checks for one uppercase letter if not
    if character in "ABCDEFGHIJKLMNOPQRSTUVWXYZ":                        # prints needs a uppercase letter
        uppercase = True

if uppercase == True:
    print("Your password contains at least 1 uppercase letter.")
elif uppercase == False:
    print("Your password needs at least 1 uppercase letter.")

numbers = False                                                          # checks for number third rule
for character in password:                                               # checks for one number if not
    if character in "0123456789":                                        # prints needs a number
        numbers = True

if numbers == True:
    print("Your password contains at least 1 number.")
elif numbers == False:
    print("Your password needs at least 1 number.")

special_character = False                                               # checks for special character fourth rule
for character in password:                                              # checks for one special character if not
    if character in "@&!%*#$?+-=()[]{}":                                           # prints need a special character
        special_character = True

if special_character == True:
    print("Your password contains at least 1 special character.")
elif special_character == False:
    print("Your password needs at least 1 special character.")

if len(password)<8:                                                     # checks to see if password is 8 characters long
    print("Your password needs at least 8 characters.")                 # if good says password has eight characters
elif len(password)>=8:                                                  # if not says passwords needs 8 characters
    print("Your password has at least 8 characters.")
    if lowercase == True:                                               # this last part checks all the rules using if
        if uppercase == True:                                           # statements and will only continue if statement
            if numbers == True:                                         # is true if all statements are true it prints
                 if special_character == True:                          # your password meets all requirements
                    print("Your password meets all requirements. \nHere is your encrypted password. \nPlease save the key somewhere safe.")

                    from cryptography.fernet import Fernet              # downloads needed files

                    key = Fernet.generate_key()                         # creating the encryption key

                    crypter = Fernet(key)

                    print(key)
