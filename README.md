# monty-hall-simulator
import random

iterations = 100000
car_count = 0
none_count = 0

for i in range(iterations):
    doors = ['none', 'none', 'none']
    doors[random.randint(0,2)] = 'car'

    if doors[1] == 'none':
        doors.pop(1)
    elif doors[2] == 'none':
        doors.pop(2)

    chosen_door = doors[1]

    if chosen_door == 'car':
        car_count += 1
    else:
        none_count += 1

print(f'Car: {car_count} = {round(car_count/iterations*100, 1)}%')
print(f'None: {none_count} = {round(none_count/iterations*100, 1)}%')
