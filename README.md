password = input("Enter a password: ")

score = 0
tips = []

if len(password) >= 8:
    score += 1
else:
    tips.append("Use at least 8 characters")

if any(c.islower() for c in password):
    score += 1
else:
    tips.append("Add lowercase letters")

if any(c.isupper() for c in password):
    score += 1
else:
    tips.append("Add uppercase letters")

if any(c.isdigit() for c in password):
    score += 1
else:
    tips.append("Add numbers")

if any(not c.isalnum() for c in password):
    score += 1
else:
    tips.append("Add symbols like @ # $")

if score <= 2:
    print("Weak")
elif score <= 4:
    print("Medium")
else:
    print("Strong")

for tip in tips:
    print("Tip:", tip)