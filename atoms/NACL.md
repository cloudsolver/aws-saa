Network Access Control List

- Operates at the subnet level
- Supports allow rules and deny rules
- Stateless: return traffic must be explicitly allowed by rules (think of Ephemeral ports)
- Rules are evaluated in order (lowest number to highest) - first match wins.
- Automatically applies to all EC2 instances in the subnet
- Default NACL accepts everything inbound and outbound
- #BestPractice create a custom NACL instead of modifying the default
