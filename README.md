# Example Production Automated Governance

This repository represents an example of how you would automate governance in a production environment driven by a GitOps workflow. 

> Automated Governance is at its best when it is part of a continuous integration and continuous deployment (CI/CD) capability. In this model, there are no human hands (no manual hand-offs) from commit to production. Thus, security, compliance, and audit needs are met 100% for every commit. With Automated Governance, there are no workarounds or shortcuts that inadvertently lead to risk and vulnerabilities. [source](https://itrevolution.com/articles/what-is-automated-governance/)

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


## Component Generation
```bash
lula generate component -c https://raw.githubusercontent.com/usnistgov/oscal-content/master/nist.gov/SP800-53/rev5/json/NIST_SP-800-53_rev5_catalog.json -r ac-3,ac-4 -o oscal-component.yaml
```

## Links
Add the following links to an `implemented-requirement` in order for Lula to provide validation
```yaml
links:
  - href: file:./validations/validations.yaml
    rel: lula
    resource-fragment: '#07b19199-d4b6-42b7-8130-633c51517279'
  - href: file:./validations/validations.yaml
    rel: lula
    resource-fragment: '#96cd25e3-fdfa-451e-8dbd-3fb2ff211d40'
```