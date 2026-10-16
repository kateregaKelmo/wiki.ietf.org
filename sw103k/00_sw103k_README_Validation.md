# SW103K Validation – Version 1

## Purpose

This package enables datacenter to independently validate the two priority
SW103K use cases:

1. Bandwidth Usage Reduction
2. Storage Saving / Enhancement

The objective is for data center to execute the validation in its own
environment and generate its own runtime evidence.

Developer-generated logs and engineering evidence are supplied separately
as supporting technical evidence and are not intended to replace
datacenter-side execution.

## Validation principle

The primary validation evidence should be generated when datacenter runs
the supplied validation workflow.

The resulting evidence should include, where applicable:

- Input file
- Original size
- Processed/transmitted/stored size
- Reduction percentage
- Integrity verification
- Execution timestamp
- Runtime measurement
- Validation log
- Packet capture where applicable

## Source-code boundary

No SW103K source code is included in this client validation package.

Do not add:

- source code
- private keys
- passwords
- API tokens
- SSH keys
- credentials
- confidential infrastructure configuration

## Current validation scope

The immediate validation scope is:

UC-01: Bandwidth Usage Reduction
UC-02: Storage Saving / Enhancement

Additional protocol use cases can be defined later using the methodology
provided in the documentation.

## Important engineering consideration

Compression results depend on characteristics of the input data.

In particular, data entropy and redundancy can materially affect the
achievable compression ratio.

Therefore, users should not assume that every dataset will produce the
same compression percentage.

The validation should record the characteristics of the input dataset and
the actual measured result.

## Execution environment

The validation should be executed on the AfriQloud environment where
possible.

Execution speed and timing may differ between development machines and
the AfriQloud VPS.

Therefore, runtime measurements generated during AfriQloud execution
should be treated as the environment-specific measurements.

## Reproducibility

The validation package is designed so that the user can supply an input
file instead of relying on a hard-coded dataset.

Example:

./run_bandwidth_validation /path/to/myfile

./run_storage_validation /path/to/myfile

The exact SW103K runtime command should be configured in the runner for
the validated AfriQloud environment before execution.

## Future deployment capabilities

The refinement roadmap includes:

- Automated dependency installation
- User-supplied input files
- Local/non-communicating operation
- Multi-network-node communication
- Additional use-case validation
- Improved dataset/entropy suitability guidance

These improvements should be treated as engineering refinement items and
should not block the immediate validation of the two priority use cases.
