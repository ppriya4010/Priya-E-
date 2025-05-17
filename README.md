source code:
class HealthcareSystem:
    def __init__(self):
        self.disease_database = {
            'fever': {
                'symptoms': ['high temperature', 'chills', 'sweating'],
                'treatment': 'Paracetamol and rest'
            },
            'cold': {
                'symptoms': ['runny nose', 'sore throat', 'sneezing'],
                'treatment': 'Antihistamines and warm fluids'
            },
            'diabetes': {
                'symptoms': ['frequent urination', 'increased thirst', 'fatigue'],
                'treatment': 'Insulin therapy and diet control'
            }
        }

    def diagnose(self, symptoms):
        for disease, info in self.disease_database.items():
            match_count = len(set(symptoms).intersection(info['symptoms']))
            if match_count >= 2:
                return f"Possible diagnosis: {disease}\nRecommended treatment: {info['treatment']}"
        return "Diagnosis not found. Please consult a physician."

# Example usage
healthcare = HealthcareSystem()

# Simulating patient symptoms
patient_symptoms = ['high temperature', 'chills', 'sweating']

# Diagnosis and treatment
result = healthcare.diagnose(patient_symptoms)
print(result)
