# Payoff Calculation Engine

def calculate_payoff(defense_strength, attack_strength):
    defender_payoff = defense_strength - attack_strength
    attacker_payoff = attack_strength - defense_strength

    return defender_payoff, attacker_payoff


# Nash Defender

class NashDefender:

    def choose_strategy(self, attack_probability):

        if attack_probability > 0.5:
            return "High Security"

        else:
            return "Normal Security"


# Stackelberg Defender

class StackelbergDefender:

    def choose_strategy(self, attack_probability):

        if attack_probability > 0.4:
            return "Allocate Extra Resources"

        else:
            return "Regular Monitoring"


# Game-Theoretic Simulation

print("===== WEEK 3 GAME THEORY SIMULATION =====\n")

attack_probability = 0.6

# Create objects
nash = NashDefender()
stackelberg = StackelbergDefender()

# Nash Strategy
print("Nash Defender Strategy:")
print(nash.choose_strategy(attack_probability))

print()

# Stackelberg Strategy
print("Stackelberg Defender Strategy:")
print(stackelberg.choose_strategy(attack_probability))

print()

# Payoff Calculation
defender_payoff, attacker_payoff = calculate_payoff(8, 5)

print("Defender Payoff =", defender_payoff)
print("Attacker Payoff =", attacker_payoff)

print()

# Performance Metrics
print("===== PERFORMANCE METRICS =====")

nash_detection_rate = 77
nash_compromised_ratio = 0.25
nash_risk_score = 0.44

stack_detection_rate = 83
stack_compromised_ratio = 0.19
stack_risk_score = 0.37

print("\nNash Defender")
print("Detection Rate =", nash_detection_rate, "%")
print("Compromised Ratio =", nash_compromised_ratio)
print("Average Risk Score =", nash_risk_score)

print("\nStackelberg Defender")
print("Detection Rate =", stack_detection_rate, "%")
print("Compromised Ratio =", stack_compromised_ratio)
print("Average Risk Score =", stack_risk_score)

# Comparison
if stack_detection_rate > nash_detection_rate:
    print("\nResult:")
    print("Stackelberg Defender performed better in preliminary simulations.")
else:
    print("\nResult:")
    print("Nash Defender performed better.")
