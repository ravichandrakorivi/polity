# Summary of Technical Proposal: Modelling for Transient Failures of Propulsion System

Proposed Solution: PROPULSION-TWIN Submitted by: Ajayan Consulting Pvt. Ltd. Submitted to: Indian Railways Date: 05 October 2026

## 1. Objective and problem statement

The proposal envisages developing PROPULSION-TWIN, a platform for capturing, analysing, modelling and diagnosing short-duration transient disturbances in locomotive propulsion systems.

Existing locomotive monitoring and protection systems can detect abnormalities and record fault codes. However, disturbances occurring within milliseconds or microseconds may not be captured with sufficient waveform detail to identify their actual causes.

A disturbance originating in one subsystem may propagate through several others. For example, an OHE voltage disturbance may affect the traction transformer, line converter, DC link, traction inverter and traction motor before causing a protection operation.

The proposed system aims to identify the initiating disturbance, trace its propagation, determine the probable cause and assess its impact on propulsion equipment.

## 2. Proposed solution and system architecture

PROPULSION-TWIN combines high-speed Data Acquisition (DAQ), event-triggered recording, Digital Twin simulation, physics-based modelling and Artificial Intelligence/Machine Learning (AI/ML).

The system will comprise four functional layers:

| Layer                            | Function                                                                                              |
| -------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Onboard Transient Intelligence   | High-speed signal acquisition, event detection, time synchronization and local storage                |
| Data & Event Intelligence        | Storage and correlation of waveforms, operating parameters, fault codes and maintenance records       |
| Digital Twin + AI/ML             | Transient reconstruction, simulation, anomaly detection, fault classification and root-cause analysis |
| Railway Engineering Applications | Event replay, diagnostic reports, component-health assessment and maintenance information             |

The platform will operate as a read-only, non-intrusive analytical system, without modifying existing locomotive control, protection or safety functions.

## 3. High-speed transient data acquisition

The proposed DAQ system will capture electrical, thermal, mechanical and control-related measurements from important propulsion subsystems.

These include OHE voltage/current, transformer parameters, converter and inverter measurements, DC-link voltage/ripple, traction motor current, temperature, vibration, cooling-system parameters and VCU/TCMS signals.

Instead of continuously transmitting all high-speed measurements, the system will use event-triggered recording with a circular buffer.

The circular buffer continuously retains recent measurements. When a specified disturbance or protection event occurs, the system preserves waveforms recorded before, during and after the event.

Triggering may be based on voltage/current thresholds, excessive rates of change, abnormal harmonics, protection signals or combinations of conditions.

Measurements from different subsystems will be time-synchronized to establish the sequence of disturbances. An onboard edge computer will perform initial signal analysis, store recorded events locally and transmit them for further investigation.

The final measurement points, sampling rates and synchronization requirements will be determined during the initial system audit.

## 4. Digital Twin and physics-based modelling

The proposal envisages developing a Digital Twin, a computer-based model representing the relevant electrical, control, thermal and mechanical behaviour of the locomotive propulsion system.

The Digital Twin will be used to reproduce recorded disturbances, examine their propagation and compare simulated responses with actual locomotive measurements.

The proposed modelling covers six levels:

1. System model: Overall propulsion energy flow and disturbance propagation.
2. Electrical dynamic model: Voltage/current transients, harmonics and DC-link behaviour.
3. Converter and control model: Converter/inverter control and protection interactions.
4. Switching-level model: Semiconductor switching and gate-drive abnormalities.
5. Electro-thermal model: Electrical losses, temperature rise and thermal stress.
6. Mechanical model: Motor torque, gearbox and rotational dynamics.

The Digital Twin will also allow virtual simulation of selected fault conditions that may be unsafe or difficult to reproduce on an operational locomotive.

Its models will be calibrated and validated by comparing simulated behaviour with actual locomotive measurements.

## 5. Physics-informed AI/ML and root-cause analysis

AI/ML will be used to detect abnormal signal patterns, classify known faults, correlate disturbances across subsystems and identify similar historical events.

The proposed approach will first establish normal operating behaviour under conditions such as acceleration, steady traction and braking. Recorded events will then be compared with these normal patterns to identify abnormalities.

Probable fault causes identified through AI/ML will be checked against Digital Twin simulation results.

For example, if a DC-link disturbance is suspected, the Digital Twin will simulate that condition to examine whether the resulting converter and motor-current responses match the recorded measurements.

The platform will also maintain a fault and transient library containing normal and abnormal event signatures. Each event will have an identifying fingerprint consisting of its operating conditions, waveform characteristics, protection information and diagnostic findings.

The objective is to provide probable root causes supported by engineering evidence rather than relying solely on AI-generated fault classifications.

## 6. Component stress and predictive maintenance

The proposal recognizes that repeated transient disturbances may impose electrical, thermal or mechanical stress on propulsion components without causing immediate failure.

The system will analyse the magnitude, duration, rate of change, repetition and operating conditions associated with these disturbances.

A proposed Transient Stress Index (TSI) will combine relevant validated parameters to indicate component stress and potentially developing deterioration.

This information is intended to support targeted inspection and preventive maintenance. The mathematical formulation of the TSI and its relationship with actual component degradation will require validation.

## 7. Proof of Concept and validation

The proposal recommends beginning with a limited Proof of Concept (POC) on a selected locomotive propulsion platform.

Testing will include high-speed acquisition, event detection, time synchronization, Digital Twin simulation, AI/ML fault classification, root-cause analysis and component stress assessment.

Validation will use laboratory testing, Hardware-in-the-Loop (HIL) testing, historical event replay and controlled field trials.

The principal POC success criterion will be demonstrating that a recorded transient can be reliably captured, reconstructed, reproduced or explained through the Digital Twin, and analysed to provide an evidence-supported engineering diagnosis.

Numerical performance and acceptance criteria will be finalized after the initial system audit.

## 8. Implementation schedule and cost

The proposal specifies an overall project duration of 18 months, followed by progressive fleet deployment.

| Phase   | Duration | Major activity                  |
| ------- | -------- | ------------------------------- |
| Phase 0 | 2 months | System and data audit           |
| Phase 1 | 2 months | DAQ and edge prototype          |
| Phase 2 | 4 months | Digital Twin development        |
| Phase 3 | 2 months | AI/ML development               |
| Phase 4 | 3 months | Integration and event replay    |
| Phase 5 | 4 months | Field pilot and validation      |
| Phase 6 | Ongoing  | Refinement and fleet deployment |

The durations specified for Phases 0–5 total 17 months, although the proposal states an overall duration of 18 months.

The indicative project cost is ₹3.5–4.0 crore, subject to finalization after Phase 0 based on locomotive configuration, measurement requirements, available interfaces and field deployment scope.

## 9. Expected outcomes and implementation requirements

The proposed system is expected to improve the capture and investigation of transient disturbances, identification of probable fault causes, assessment of component stress and maintenance decision-making.

It also envisages fleet-level comparison of recurring failures, equipment behaviour and operating conditions.

Implementation will depend on the availability of high-speed signals, access to VCU/TCMS and converter interfaces, accurate synchronization, suitable locomotive parameters for modelling and sufficient data for AI/ML validation.

The proposal identifies dedicated DAQ, progressive model calibration, simulation, HIL testing and locomotive-class-specific models as measures to address these challenges.

The actual improvements in locomotive reliability, availability, downtime and maintenance cost will be assessed during the field pilot.

## 10. Conclusion

PROPULSION-TWIN is proposed as an integrated platform combining high-speed transient recording, Digital Twin simulation and physics-informed AI/ML to investigate disturbances in locomotive propulsion systems.

Its primary objective is to move beyond recording fault codes and protection operations by reconstructing transient events, identifying their probable causes and assessing their effects on propulsion components.

The proposed fault library and component stress analysis are intended to support predictive maintenance and fleet-level reliability improvement.

The effectiveness of the proposed system will depend on successful demonstration of reliable transient capture, accurate modelling and evidence-supported root-cause diagnosis during the Proof of Concept and field validation.