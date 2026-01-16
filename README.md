# my-gitops-demo
testing modern way CI/CD+gitOps+Helm+K8S 
1. Dev modifica app/index.html
2. Commit + push su GitHub (branch main)
3. GitHub Actions trigger:
   - Build Docker image
   - Tag: my-cats-app:SHA_COMMIT o my-cats-app:v1.2.3
   - Push su Docker Hub/Registry
   - Modifica values.yaml con nuovo tag
   - Commit automatico values.yaml
4. ArgoCD rileva cambio in values.yaml
5. ArgoCD fa helm upgrade automatico
