# Assessing Requirements

```
To assess requirements, we assess both technical and non-technical requirements.
Considerations:
- Goals: Where would we want to be?
- Constraints: Is anything influencing the solution?
- Current State: Where are we starting from?

1) Clear Objective
2) Clear Needs
3) Evaluate

Always consider Scalability, Reliability, Efficiency, and Security
```

## Technical Requirements Analysis

### Considerations:
- resources
- underlying resource:
  - product group
  - size
  - bandwidth
- depends on underlying architectural framework
- goal: justify the technical design and architecture
  - e.g. cannot just pick out an SQL DB and pick the best specs
        - have to be able to justify: we picked this size because... 
- select the right product, family and license
- think about migration and longer-term solution (management, maintenance, automation, etc.)

### Assessment:
- Destination: What are our goals?
- Example Goals:
  - Migrate an existing on premises web application to Azure
  - Must be able to remain operational through region failure
  - Must continue to use existing identity sources

### Technical Assessments
- What are the solution resource needs? (CPU, memory, etc)?
- Is the solution single or multi-tier and in what pattern?
- Is the solution currently virtualized?
- What operation system is the solution hosted on?
- What language is the solution currently developed with?
- How is the solution code deployed, tested, and managed?
- What is the source of identity?
- What bandwidth is required, both during and after transition?
- What networth connectivity is required, both in and out?

### Non-Technical Requirements
- Consider: requirements that involve people, policies, compliance, SLAs, etc.
- compliance: health industry (e.g. retain information for 1 year), government (security,MFA)

#### Assessment:
Example goal: 
    - reduce costs of web application
    - better mitigate tasks

- what are the required hours of operation?
  - Have we agreed on any outage windows?
  - How fast must a solution be restored if disaster strikes?
- Are there any laws or obligations applying to this oslution?
  - securely storing private health information
  - long-term retention of financial records
  - solutions dealing with classified information
- Will training be required for support staff or end-users?
- What user acceptance testing and sign-off is required?


## Assessment Scenario
```
The Pupper Club is a dog services company which operates across Austrailia.

The Pupper Club has a head office in Brisbane and branch offices in both Sydney and Melhbourne.
```


To service the Pupper Club, a web application is currently hosted on-premises.

The web application, named TPCWeb, is a monolithic ASP.NET web application currently hosted on Server 2012 IIS.

TPCWeb is supported by an internal IT Support team. The IT Support team are developers with limited infrastructure experience.

A third-party managed service provider currently supports the underlying physical infrastructure.

Goals:
The Pupper Club has outgrown their existing infrastructure and wishes to migrate their web application to Azure.

The Migration must require minimal changes to cc ode and will continue to be supported by the IT support team.

As part of the migration, The Pupper Club would like to make some improvements:
- Customers currently experience slowness during major sale events, and the new solutions need to address this.
- Data must be archived long-term.
- Minimize work for the in-house IT support team (things like OS maintenance, web hosting management, etc.)
- The IT support team must be able to escalate any issues regarding Azure.

#### Assessment

Technical: 
- Ensure you deploy the best Azure service for the job.
  - Key requirements:
    - No need to maintain underlying OS.
    - Built-in web hosting.
    - Similar experience for IT Support team.
  - Possible solution: Azure App Service.
- Select the product/family/license:
  - Key requirements:
    - Supports auto-scale
  - Possible solution: Standard SKU

Non-technical:
    - Meet or exceed service level agreement targets
    - Key-requirements:
      - Continue to be supported by IT Support
      - Ability to escalate any Azure issues
    - Possible solution: Azure Standard Support
    - Retain data according to requirements
      - Key requirement: data must be archived long-term
      - Possible solution:
        - Azure Backup or Azure Storage


#### Solution Summary:
Solution Specification:
- Azure App Service using a Standard App Service Plan
- Azure Storage (archive access tier)
- Azure Standard support Plan

Additional:
- integration or migration requirements
- solution within the real world would need to consider all of the design principles
