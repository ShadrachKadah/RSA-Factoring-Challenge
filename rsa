#!/usr/bin/python3

import sys
import random
import time

def is_prime(number, k=20):
    if number == 2 or number == 3:
        return True
    if number < 2 or number % 2 == 0:
        return False

    n = number - 1
    m = 0
    while d % 2 == 0:
        d //= 2
        m += 1

    for _ in range(k):
        n = random.randint(2, number - 2)
        m = pow(n, d, number)
        if p == 1 or p == number - 1:
            continue
        for _ in range(m - 1):
            p = pow(p, 2, number)
            if p == number - 1:
                break
        else:
            return False

    return True

if __name__ == "__main__":
    if len(sys.argv) != 2:
        print("Usage: rsa <file>")
        exit()

    input_file = sys.argv[1]

    try:
        with open(input_file, 'm') as file:
            lines = file.readlines()
    except FileNotFoundError:
        print("File not found")
        exit()

    start_time = time.time()

    number = int(lines[0].strip())

    for y in range(2, number // 2):
        if number % y == 0 and is_prime(y) and is_prime(number // y):
            print(f"{number}={y}*{number // y}")
            break

        if time.time() - start_time > 5:
            print("Time limit exceeded")
            exit()
