# Elastic-data-privacy-protection-through-software-and-hardware-collaboration

## Main structure
The project consists of two modules: the Domain Processing Module and the Key Distribution Module. The former captures and marks sensitive data, while the latter assigns memory protection keys.
On x86 systems, Intel Memory Protection Keys (MPK) are utilized, and on ARM systems, Memory Tagging Extension (MTE) is used.
The figure below illustrates the main architecture of the project.
![image](https://github.com/MrCookieeeee/Research-Proposal/assets/107045624/09e5133e-320c-428f-8235-fadaaab9801e)

## Dynamically changing access permissions
When data in the source code or binary code is mapped to physical memory, the page table entry for this data is marked. Due to the processing by the sensitive data identification module and the key distribution module, a memory page is bound to a specific key. By checking the PKRU register, we can determine the read/write permissions of the page.
When the code execution space changes, access to memory can be denied because the memory protection key is withdrawn. When the code execution context changes, the key can be retrieved or the key permissions can be altered to achieve access control over the memory page.
The figure below illustrates the details.
![image](https://github.com/MrCookieeeee/Research-Proposal/assets/107045624/ad9db06e-f088-4b6a-a5ed-760b3c2849da)

more details. please check ./Research Proposal.pdf
