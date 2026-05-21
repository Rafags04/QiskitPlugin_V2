# SonarQiskit – SonarQube Plugin for Quantum Software Quality Analysis

![License](https://img.shields.io/badge/license-EUPL%201.2-blue)
![SonarQube](https://img.shields.io/badge/SonarQube-9.x-orange)
![Qiskit](https://img.shields.io/badge/Qiskit-supported-purple)

## 💡 Overview

SonarQiskit is a SonarQube custom plugin designed for static analysis and quality evaluation of hybrid classical-quantum software systems based on Qiskit.

The project extends SonarQube with quantum-oriented metrics, analyzability mechanisms, and quality assessment capabilities tailored to Quantum Software Engineering (QSE).

The plugin has been developed as part of ongoing research on:
- quantum software quality,
- hybrid systems maintainability,
- static analysis for quantum programs,
- and quantum software metrics.

---

## 🧩 Component Overview

### 🔹 Backend (Java)

Located under:

`src/main/java/org/sonarsource/plugins/qiskit/`

#### Plugin registration
- **QiskitPlugin.java** – Registers the plugin inside SonarQube.

#### Metric implementations (`measures/`)
The following classes compute Qiskit-related measurements:

- AuxiliaryQubits.java
- ConditionalInstructions.java  
- Depth.java  
- HighComplexityGates.java  
- InitResetOperations.java  
- LowComplexityGates.java  
- MeasureOperations.java  
- MediumComplexityGates.java
- QuantumCyclomaticComplexity.java
- Width.java  

### 🔹 Frontend (JavaScript)

Located under:

`src/main/js/`

Contains JavaScript resources used for extending or displaying UI components inside SonarQube.

---

## 🛠️ Building the Plugin

Compile the plugin using Maven:

`mvn clean package`

---

## 🚀 Installing in SonarQube

Once the JAR is generated, install the plugin in your SonarQube instance:

1. Build the plugin:

`mvn clean package`

2. Copy the generated file into the SonarQube plugins directory:

`$SONARQUBE_HOME/extensions/plugins/`

3. Restart SonarQube so the plugin is loaded.

After restarting, the plugin will appear inside the SonarQube environment.

---

## ✔ Validation

The repository includes a validation suite composed of representative quantum circuits implemented in Qiskit.

The validation dataset includes well-known quantum algorithms such as:
- Bernstein–Vazirani
- Deutsch–Jozsa
- Grover
- Shor
- Quantum Phase Estimation

The computed metrics are compared against manually validated expected values provided in:

/validation/expected_metrics.csv

This validation process was used as part of the empirical evaluation of the plugin during research activities related to quantum software quality assessment.

---

## 📚 Research Context

This project is part of ongoing research activities in:
- Quantum Software Engineering (QSE)
- Software Quality
- Static Analysis
- Maintainability Assessment
- Hybrid Classical-Quantum Systems

The plugin aims to provide tooling support for analyzability and quality evaluation of quantum software systems integrated within classical software environments.

---

## ✍ Cite This Work

If you use this plugin in academic or industrial research, please cite the associated publications.

---

## 📖 License

This project is licensed under the European Union Public Licence, version 1.2 (EUPL-1.2).
See the LICENSE file for details.
