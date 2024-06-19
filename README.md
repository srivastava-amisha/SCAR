# SCAR: Power Side-Channel Analysis at RTL Level

SCAR is a graph neural network-based framework designed for RTL-level Power Side-Channel (PSC) analysis. Its goal is to detect locations vulnerable to power side-channel attacks in the RTL design for cryptographic algorithms. The framework employs Control Data Flow Graphs (CDFGs) extracted from RTL designs of encryption hardware to identify components or modules vulnerable to PSC attacks. This README provides a high-level overview of the framework, its inputs, and outputs.

Inputs
The SCAR framework requires the following inputs:

RTL Design: Only the RTL designs of encryption algorithms are utilized, with AES_Comp (a composite field implementation of the AES encryption algorithm) being the primary training dataset.

CDFG of RTL Design: The CDFG is generated using the GOLDMINE tool. Any other similar tool capable of generating CDFGs from RTL designs can also be used.

Features of CDFG Nodes: Features extracted from the CDFG nodes are crucial for analysis. Key features include:

Number of Vulnerable Paths: Indicates potential leakage points related to the encryption key.
Node Degree: Reflects the connectivity of each node, identifying potential links to vulnerable neighbors.
Hamming Distance: Used to measure bit flips and their impact on dynamic power consumption.
Operation Type: Identifies logic operations like XOR, OR, AND, and MUX, which contribute to dynamic power changes.

Output
The output of the GNN is the identification of leaky modules within the RTL design, highlighting potential security vulnerabilities.

Sample Code and Data
The included sample code and data are based on the PRESENT Cipher design. The CDFG and features specific to its RTL design are used to demonstrate the functionality of the SCAR framework.

Installation and Usage
To set up the SCAR framework, run the provided sample code with the required files specified in the code blocks. The provided example is te test GNN model on the PRESENT Cipher design, given the model is trained on an implementation of AES, known as AES_Comp.

Note
This framework is part of ongoing research and is intended for academic and professional use in the field of cryptographic hardware analysis. The methodology and examples provided are based on specific datasets and may require adaptation for different encryption algorithms and RTL designs.
