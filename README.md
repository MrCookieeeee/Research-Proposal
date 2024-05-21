# Elastic-data-privacy-protection-through-software-and-hardware-collaboration

## Main structure
The project has two moduels: Domain processing module and Key distribution module. The former captures and marks sensitive data, while the latter assigns memory protection key.
On x86, I utilize Intel Memory Protection Keys(MPK), on ARM I utilize MTE.
Figure bellow illustrate the main architecture of my project.
![image](https://github.com/MrCookieeeee/Research-Proposal/assets/107045624/09e5133e-320c-428f-8235-fadaaab9801e)

## Dynamically changing access permissions
When data in the source code or binary code is mapped to physical memory, the page table entry for this data is marked. Due to the processing by the sensitive data identification module and the key distribution module, a memory page has been bound to the key. By checking the PKRU register, we can determine the read/write permission of the page. When the code execution space changes, access to memory can be denied because the memory protection key is withdrawn. When the code execution time changes, you can also retrieve the key or change the key permissions to achieve access control to the memory page.
Figure bellow illustrate the deatails.
![image](https://github.com/MrCookieeeee/Research-Proposal/assets/107045624/ad9db06e-f088-4b6a-a5ed-760b3c2849da)

more details. please check ./Research Proposal.pdf
