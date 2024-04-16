# Example Production Automated Governance

This repository represents an example of how you would automate governance in a production environment driven by a GitOps workflow. 

> Automated Governance is at its best when it is part of a continuous integration and continuous deployment (CI/CD) capability. In this model, there are no human hands (no manual hand-offs) from commit to production. Thus, security, compliance, and audit needs are met 100% for every commit. With Automated Governance, there are no workarounds or shortcuts that inadvertently lead to risk and vulnerabilities. [source](https://itrevolution.com/articles/what-is-automated-governance/)

## Intended Demo
- Have a base repository housing Istio
- Talk about how this could represent production (IE GitOps)
- Generate a component-definition with some controls relevant to Istio
- Add Lula validation and the Lula action to the workflow
- Commit changes to the repository


## How to use this Repository

### Baseline
- Baseline includes workflows for deploying k3d, installing zarf and deploying istio

### Demo Workflows

#### Setup the initial workflows
- Review the repository on GitHub (previous )
- Create a demonstration branch
- Cover how this is representative of a example production environment
- Generate a component definition
- Link an `implemented-requirement` with the pre-existing validations (in the validation directory)
- Uncomment the Lula workflows in the `.github/workflows` directory
- Commit changes to the repository
- Open a PR and review workflow output
- Download the assessment-results artifact
- Store the results in the repository, commit, review with new threshold

#### Demonstrate Continuous Assessment
- Uncomment the sample webapp from the zarf.yaml
- Commit and Review the PR output
- Introduce a non-compliant state - uncomment the pod label for disabling istio injection
- Commit and Review the PR output
- Fix, commit, review the PR output
