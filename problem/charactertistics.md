# Architectural Charactertistics

## Candidate

| Characteristic  | Driver |
|-----------------|:-------|
| Availability    | International, low downtime |
| Configurability | Email integration configurations per user |
| Fault Tolerance | "max 5 minutes per month of unplanned downtime" |
| Integration	  | Multiple agencies to be integrated, presumably more over time |
| Interoperability| Variety of systems and protocols for different agencies |
| Scalability	  | 2M weekly users |

## Primary

- Fault Tolerance
- Interoperability
- Scalability

## Implicit

### Performance

Although *Performance* is explicitly stated in the brief / requirements by virtue of targets, the thresholds for UI performance, for example, are reasonably forgiving. Because they represent a reasonably "normal" set of expectations for a modern UI, and therefore it is not a primary architectural concern.

### Security

*Security* is definitely a concern, like with many systems. This system will handle personal data, but is not handling payments etc. Although security ought to be considered at all stages of development, there is no novel aspect to this domain that ought to drive an unusually high priority for security with respect to the architecture.
