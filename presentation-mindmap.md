```mermaid
mindmap
  root((SonarQube Enterprise))
    Why
      Security/Static Analysis
      Code coverage metrics wanted by some teams
      Company Goal to Improve Quality
        Quality Gates
      On-Prem Enterprise due to Feature Limitations between SaaS and Enterprise
      Buy vs Build
        SonarQube is very commonly used, and often seen as an Industry Standard
        Focus on Core competencies
        Annual license for 5M LoC was much less expensive than home-grown
    Good, Do Different, Improvements
      Good
        Backstage Templates
          Organic Growth & Adoption
        Onboarding Teams was welcomed, and in a few cases sought out
        CloudSQL Autoscaling was seamless and worked very well
      Bad
        Scala Code Coverage
          PoC was complicated
          Scala Upgrade broke dep tree causing coverage stats to break
        Enterprise License limited HA
        Ownership Hand-off
          Documentation and cross-training was successful, but ownership itself stagnated
            Hosted solution may have mitigated this
      Improvements
        Team Mappings
          Disconnected from Github & Buildkite Teams
          Google Groups was Okta Source
            No consistency in naming
            Over 2500 Google Groups
          Manual at Best
          Leverage Backstage as Source of Truth
        GoLang Code Coverage
          Built-in compiler coverage support is limited, and results not fully accurate
        Shared CloudSQL Instance for Dev/Test/Prod
          Use different instances
        CD
          ArgoCD
            Needed tests
              Synthetics
          Merges to main were production promotions
    Tech Stack
      Backstage Integration
      Kubernetes
        Helm
          Bugs & PRs
      Terraform
        Helm Config in HCL/Yaml
        Helm Chart Version Set in Code/Config
          Bump Pin to Upgrade
        Container Image Version Pinned in HCL
      Buildkite CI
        Shell Wrapper & Entrypoint for GoLang and Generic Projects
          Docker Image
        Merges to main were production promotions
      CloudSQL
      No ArgoCD
      Monitoring
        Elasticsearch & Kibana
        Slack Notifications
          Failure on Sonar agent
          Kubernetes Healthchecks
        Kubernetes Healthchecks
    PoC
      Contraints
        Scope
          Limited to working from personal laptop
          Gradle & Scala Support Needed
          License initially limited to free licenses
          Determine the License requirements based on LoC in our repos
        Time
          10 Weeks, allowing for interrupts
          One engineer in PoC
          No Additional Engineers Allocated for PoC
        Quality
          Hacked together initially as a Docker compose environment
  ```