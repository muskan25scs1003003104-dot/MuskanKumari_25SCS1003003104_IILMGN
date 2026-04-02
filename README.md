# MuskanKumari_25SCS1003003104_IILMGN
import random

# ---------------------------------------------------------
# Stage 1: Initial Assessment and Targeting
# ---------------------------------------------------------

def integrate_data():
    """
    Step 1: Integrate healthcare, agriculture, and environmental data.
    (This uses simulated values for demonstration.)
    """
    data = {
        "healthcare_usage": random.randint(50, 150),
        "agriculture_usage": random.randint(80, 200),
        "water_antibiotic_level": random.uniform(0.5, 5.0),
        "soil_antibiotic_level": random.uniform(0.3, 4.0),
        "ARG_level": random.uniform(1.0, 10.0)  # Antibiotic Resistance Genes
    }
    print("\n[1] Integrated Data:", data)
    return data


def identify_risks(data):
    """
    Step 2: Identify hotspots and prioritize risks.
    """
    risk_score = data["water_antibiotic_level"] + data["soil_antibiotic_level"] + (data["ARG_level"] / 2)

    if risk_score > 10:
        hotspot = "High-risk hotspot detected (urgent priority)"
    elif risk_score > 6:
        hotspot = "Moderate-risk hotspot detected"
    else:
        hotspot = "Low-risk area"

    print("[2] Risk Analysis:", hotspot)
    return risk_score


# ---------------------------------------------------------
# Stage 2: Regulatory Framework
# ---------------------------------------------------------

def set_PNEC(risk_score):
    """
    Step 3: Set Predicted No Effect Concentration (PNEC).
    """
    PNEC = max(0.5, 10 - risk_score)  # Lower risk → higher PNEC
    print(f"[3] Assigned PNEC limit: {PNEC:.2f}")
    return PNEC


def regulate_manufacturing(PNEC):
    """
    Step 4: Check manufacturing discharge levels vs PNEC.
    """
    discharge = random.uniform(0.5, 8.0)
    status = "COMPLIANT" if discharge <= PNEC else "NON-COMPLIANT"
    print(f"[4] Manufacturing Discharge = {discharge:.2f} → {status}")
    return status


def regulate_agriculture():
    """
    Step 5: Agriculture regulation simulation.
    """
    misuse_detected = random.choice([True, False])
    if misuse_detected:
        print("[5] Agriculture: Misuse detected → Enforce stricter controls")
    else:
        print("[5] Agriculture: Proper usage & manure management")


def regulate_healthcare():
    """
    Step 6: Healthcare regulation simulation.
    """
    misuse = random.choice([True, False])
    if misuse:
        print("[6] Healthcare: Over-prescription detected → Enforce ASP")
    else:
        print("[6] Healthcare: Good stewardship practices")


# ---------------------------------------------------------
# Stage 3: Implementation, Enforcement, and Feedback
# ---------------------------------------------------------

def incentives_support():
    """
    Step 7: Provide incentives.
    """
    print("[7] Providing subsidies & training to support compliance")


def enforcement():
    """
    Step 8: Enforcement & audits.
    """
    compliant = random.choice([True, False])
    if compliant:
        print("[8] Audit Result: Fully compliant")
    else:
        print("[8] Audit Result: NON-COMPLIANT → Penalty imposed")


def feedback_loop():
    """
    Step 9: Feedback loop to adjust regulations.
    """
    levels_declining = random.choice([True, False])
    if levels_declining:
        print("[9] Pollution levels declining → Maintain current regulations")
    else:
        print("[9] Pollution not improving → Tightening standards")


# ---------------------------------------------------------
# MASTER FUNCTION (Runs the Full Algorithm)
# ---------------------------------------------------------

def run_antibiotic_regulation_model():
    print("\n========== ANTIBIOTIC POLLUTION REGULATION MODEL ==========")

    data = integrate_data()
    risk = identify_risks(data)
    PNEC = set_PNEC(risk)
    regulate_manufacturing(PNEC)
    regulate_agriculture()
    regulate_healthcare()
    incentives_support()
    enforcement()
    feedback_loop()


# ---------------------------------------------------------
# RUN THE MODEL
# ---------------------------------------------------------

run_antibiotic_regulation_model()
