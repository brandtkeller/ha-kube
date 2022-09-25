# ha-kube

### Current State
Documenting thoughts around this problem space. Looking to understand if this would provide value AND if there is complexity that would be overcomplicated by a single tool.

## What?
With regards to installing kubernetes, there is no single system-agnostic tool for installing highly-available kubernetes clusters. 

For cloud environments, this is not a problemdue to availability of API's to interact with to manage and configure machines.

For baremetal or virtualized machines, this may not be the case. In this scenario, configuration tools such as ansible must be used. With the configuation tooling, comes a list of dependencies that must be maintained, errors that can arise without intimate background information, and a lack of processes that can be improved to support the consumer.

## Why?
There appears to be a gap in tooling that can install kubernetes in highly-available configurations with deep introspection into what is happening. 

## How?

A tool that wraps single-node kubernetes install artifacts with focus on end-to-end highly available deployments. 

Targeting RKE2 for familiarity and the use of configuration files 

## Example workflow

### Inputs required
- Node IP addresses

### Dependencies
- SSH Access (password/key)

### CLI Execution
`ha-kube rke2`

### High-level
- Pull all configurations from a configuration file
- Hosts, transient configs, etc