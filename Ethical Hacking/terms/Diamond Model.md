# Diamond Model

The Diamond Model of Intrusion Analysis is a conceptual framework used for understanding and analyzing cybersecurity incidents. It provides a systematic approach to intrusion analysis by breaking down an attack into four core components: adversary, capability, infrastructure, and victim. This model helps cybersecurity professionals to dissect and understand the nature of an intrusion, facilitating better detection, response, and mitigation strategies.

Here are the key components of the Diamond Model:

1. **Adversary**: The entity responsible for conducting the attack. This could be an individual, group, or organization with malicious intent.

- It is essential to know the distinction between adversary operator and adversary customer because it will help you understand intent, attribution, adaptability, and persistence by helping to frame the relationship between an adversary and victim pair.  

- **Adversary Operator** is the “hacker” or person(s) conducting the intrusion activity.

- **Adversary Customer** is the entity that stands to benefit from the activity conducted in the intrusion. It may be the same person who stands behind the adversary operator, or it may be a separate person or group.

- As an example, an adversary customer could control different operators simultaneously. Each operator might have its capabilities and infrastructure.

2. **Capability**: The tools, techniques, and procedures (TTPs) that the adversary uses to carry out the attack. This includes malware, exploits, and other resources.

- **Capability Capacity** is all of the vulnerabilities and exposures that the individual capability can use. 

- **Adversary Arsenal** is a set of capabilities that belong to an adversary. The combined capacities of an adversary's capabilities make it the adversary's arsenal.

3. **Infrastructure**: The physical and virtual resources used by the adversary to deliver the capability to the victim. This could include command and control servers, compromised systems, and delivery mechanisms.

- Type 1 Infrastructure is the infrastructure controlled or owned by the adversary. 

- Type 2 Infrastructure is the infrastructure controlled by an intermediary. Sometimes the intermediary might or might not be aware of it. This is the infrastructure that a victim will see as the adversary. Type 2 Infrastructure has the purpose of obfuscating the source and attribution of the activity.

- Service Providers are organizations that provide services considered critical for the adversary availability of Type 1 and Type 2 Infrastructures, for example, Internet Service Providers, domain registrars, and webmail providers.

4. **Victim**: The target of the attack. This could be an individual, organization, or system that is being exploited or attacked.

- **Victim Personae** are the people and organizations being targeted and whose assets are being attacked and exploited. These can be organization names, people’s names, industries, job roles, interests, etc.

- **Victim Assets** are the attack surface and include the set of systems, networks, email addresses, hosts, IP addresses, social networking accounts, etc., to which the adversary will direct their capabilities.

Additionally, the Diamond Model incorporates more features that provide context and depth to the analysis:

- **Meta-Features**: These include aspects like timestamp, phase, result, direction, methodology, and resources. Meta-features are not required, but they can add some valuable information or intelligence to the Diamond Model.

- **Activity Threads**: These are sequences of events that link together to form a narrative of the attack. They help in understanding the progression and timeline of the intrusion.
