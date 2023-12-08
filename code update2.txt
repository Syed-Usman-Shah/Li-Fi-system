#pip install xlrd
import pandas as pd

df = pd.read_excel('Light_data.xls')

# print(df.head())
# print(df['Illuminance (lx)'])
all_data = df['Illuminance (lx)']
all_data2 = list(all_data.values)
print(all_data)
# print(df)

message = ""
previous_alphabet = ""
for val in all_data:
    if val >= 0 and val <= 10:
        received_alphabet = "S"
        if received_alphabet != previous_alphabet:
            message = message + received_alphabet
            previous_alphabet = "S"

    elif val >= 20 and val <= 25:
        received_alphabet = "V"
        if received_alphabet != previous_alphabet:
            message = message + received_alphabet
            previous_alphabet = "V"

    elif val >= 30 and val <= 38:
        received_alphabet = "M"
        if received_alphabet != previous_alphabet:
            message = message + received_alphabet
            previous_alphabet = "M"

    elif val >= 60 and val <= 70:
        received_alphabet = "A"
        if received_alphabet != previous_alphabet:
            message = message + received_alphabet
            previous_alphabet = "A"

    elif val >= 85 and val <= 100:
        received_alphabet = "I"
        if received_alphabet != previous_alphabet:
            message = message + received_alphabet
            previous_alphabet = "I"

    elif val >= 101 and val <= 110:
        received_alphabet = "D"
        if received_alphabet != previous_alphabet:
            message = message + received_alphabet
            previous_alphabet = "D"


    elif val >= 175 and val <= 180:
        received_alphabet = "E"
        if received_alphabet != previous_alphabet:
            message = message + received_alphabet
            previous_alphabet = "E"

print("All data decoded successfully")
print("Received data is :",message)
