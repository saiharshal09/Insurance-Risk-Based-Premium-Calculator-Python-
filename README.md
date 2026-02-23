# Insurance-Risk-Based-Premium-Calculator-Python-
you can just know your premiums within seconds
base_premium = 5000

age = int(input("Enter age: "))
smoker = input("Smoker? (yes/no): ").lower()
claims = int(input("Number of past claims: "))

risk_score = 0

if age < 25:
    risk_score += 2
elif age < 40:
    risk_score += 1
else:
    risk_score += 0

if smoker == "yes":
    risk_score += 2


if claims > 2:
    risk_score += 2
elif claims > 0:
    risk_score += 1


risk_levels = {
    0: "Low Risk",
    1: "Low Risk",
    2: "Medium Risk",
    3: "Medium Risk",
    4: "High Risk",
    5: "High Risk",
    6: "High Risk"
}

risk_category = risk_levels.get(risk_score, "High Risk")

final_premium = base_premium + (risk_score * 1000)

print("\nRisk Category:", risk_category)
print("Suggested Premium:", final_premium)
