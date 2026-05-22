# SonarQiskit – SonarQube Plugin for Quantum Software Quality Analysis

![License](https://img.shields.io/badge/license-EUPL%201.2-blue)
![SonarQube](https://img.shields.io/badge/SonarQube-9.x-orange)
![Qiskit](https://img.shields.io/badge/Qiskit-supported-purple)

---

## 💡 Overview

SonarQiskit is a SonarQube custom plugin designed for static analysis and quality evaluation of hybrid classical-quantum software systems based on Qiskit.

The project extends SonarQube with quantum-oriented metrics, analyzability mechanisms, and quality assessment capabilities tailored to Quantum Software Engineering (QSE).

The plugin has been developed as part of ongoing research on:
- quantum software quality,
- hybrid systems maintainability,
- static analysis for quantum programs,
- and quantum software metrics.

This repository contains the research artifact associated with the SonarQiskit research line on quantum software quality and static analysis.

---

## 📖 Scientific Publications

The plugin has been developed and used as part of several research works on Quantum Software Engineering, software quality, hybrid systems, and quantum software evaluation.

### Information and Software Technology (IST)

**Service engineering for quantum computing: Ensuring high-quality quantum services**

- https://www.sciencedirect.com/science/article/abs/pii/S0950584924002489

### SoftwareX (Research Artifact Associated with this Repository)

**SonarQiskit: Extending SonarQube for Quantum Code Quality Analysis**

- SSRN preprint: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=6029171

### Science of Computer Programming (SCP)

**Implementing an environment for hybrid software evaluation**

- https://www.sciencedirect.com/science/article/abs/pii/S0167642324000327

### Journal of Universal Computer Science (JUCS)

**Towards a set of metrics for hybrid (quantum/classical) systems maintainability**

- https://lib.jucs.org/article/99348/

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

If you use this plugin in academic or industrial research, please cite the associated publications listed above.

### BibTeX

```bibtex
@article{diazmunoz2024environment,
  title = {Implementing an environment for hybrid software evaluation},
  author = {D{\'i}az-Mu{\~n}oz, Ana and Rodr{\'i}guez, Mois{\'e}s and Piattini, Mario},
  journal = {Science of Computer Programming},
  volume = {236},
  pages = {103109},
  year = {2024},
  issn = {0167-6423},
  doi = {10.1016/j.scico.2024.103109},
  publisher = {Elsevier},
  note = {Part of special issue: Quantum Programming for Software Engineering},
  url = {https://www.sciencedirect.com/science/article/pii/S0167642324000327}
}

@article{diazmunoz2026sonarqiskit,
  title = {SonarQiskit: Extending SonarQube for Quantum Code Quality Analysis},
  author = {D{\'i}az-Mu{\~n}oz, Ana and Oviedo, Jes{\'u}s Ram{\'o}n and Verdugo, Javier and Rodr{\'i}guez, Mois{\'e}s and Cruz-Lemus, Jos{\'e} A.},
  year = {2026},
  publisher = {SSRN},
  doi = {10.2139/ssrn.6029171},
  url = {https://ssrn.com/abstract=6029171},
  note = {Available at SSRN}
}

@article{diazmunoz2025quantumservice,
  title = {Service engineering for quantum computing: Ensuring high-quality quantum services},
  author = {D{\'i}az, Ana and Alvarado-Valiente, Jaime and Romero-\'Alvarez, Javier and Moguel, Enrique and Garcia-Alonso, Jose and Rodr{\'i}guez, Mois{\'e}s and Garc{\'i}a-Rodr{\'i}guez, Ignacio and Murillo, Juan M.},
  journal = {Information and Software Technology},
  volume = {179},
  pages = {107643},
  year = {2025},
  issn = {0950-5849},
  doi = {10.1016/j.infsof.2024.107643},
  publisher = {Elsevier},
  url = {https://www.sciencedirect.com/science/article/pii/S0950584924002489}
}

@article{diazmunoz2024metrics,
  title = {Towards a set of metrics for hybrid (quantum/classical) systems maintainability},
  author = {Mu{\~n}oz, Ana D{\'i}az and Monje, M. Rodr{\'i}guez and Velthuis, M. G. P.},
  journal = {Journal of Universal Computer Science},
  volume = {30},
  number = {1},
  pages = {25--48},
  year = {2024},
  doi = {10.3897/jucs.99348},
  url = {https://lib.jucs.org/article/99348/}
}
```

---

## 📖 License

This project is licensed under the European Union Public Licence, version 1.2 (EUPL-1.2).
See the LICENSE file for details.
