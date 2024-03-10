# CI/CD Attacks

## PPE

This type of attack involves compromising a component or stage in the SDLC. For this attack to work, it takes advantage of the trust boundaries established within the supply chain, which is extremely common in CI/CD, where automation is everywhere.

When an attacker has access to version control systems and can manipulate the build process by injecting malicious code into the pipeline, they don't need access to the build environment. This is where the "poisoned" pipelines come into play. It's crucial to have effective, secure gates and guardrails to prevent malicious code from getting far if there is an account compromise.

## Indirect Poisoned Pipeline Execution

If an attacker doesn't have direct write access (to a main-protected or branch-protected repository, for example), it's possible they have write access to other repositories that could indirectly modify the behaviour of the pipeline execution. 

If an environment is employing a development pipeline, a configuration file must be defined for the steps the build system must take. If a repository contains all the necessary source and build files, and another repository contains the pipeline files, write permissions could differ between the two, resulting in an indirect PPE vulnerability. 
