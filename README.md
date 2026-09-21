# silver-umbrella
My prep for WeThinkCode_ bootcamp
# SASSA Grant Calculator 
# Southhills area

# Dictionary - SASSA grants 2025/2026
sassa_grants = {
    "old age": 2310,
    "old age 75+": 2330,
    "disability": 2310,
    "child support": 530,
    "child support top-up": 750,
    "foster care": 1210,
    "care dependency": 2310,
    "war veterans": 2330,
    "SRD": 370
}

print("SASSA GRANT CALCULATOR")
print("Available grants:")
for grant, amount in sassa_grants.items():
    print(f"- {grant}: R{amount}")

print("\n------------------------------")

# Ask user
grant_type = input("Enter grant type (e.g., child support): ").lower().strip()
num_people = int(input("How many people get this grant in your house? "))

if grant_type in sassa_grants:
    amount_per_person = sassa_grants[grant_type]
    total = amount_per_person * num_people
    
    print("\n--- RESULT ---")
    print(f"Grant: {grant_type.title()}")
    print(f"Amount per person: R{amount_per_person}")
    print(f"Number of people: {num_people}")
    print(f"TOTAL PER MONTH: R{total}")
    
    # Extra for Southhills example
    if total < 1000:
        print("Note: This is low, family may need more support")
    else:
        print("Note: This helps family with food and school")
else:
    print(f"Sorry, '{grant_type}' not found. Try: {list(sassa_grants.keys())}")
