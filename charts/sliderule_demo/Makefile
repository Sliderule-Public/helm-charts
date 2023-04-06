.ONESHELL:

install:
	@helm -n shieldrule-demo install shieldrule --create-namespace -f values.yaml .

upgrade:
	@helm -n shieldrule-demo upgrade shieldrule -f values.yaml .

use_aws_cluster:
	@aws eks update-kubeconfig --region $(region) --name $(cluster)

set_namespace:
	@kubens $(env)

rollout:
	@kubectl rollout restart deployment/shieldrule-$(service) # Start rollout
	@kubectl rollout status -w deployment/shieldrule-$(service) # Watch rollout

uninstall:
	@helm -n shieldrule-demo uninstall shieldrule

describe:
	@echo "deployments:"
	@kubectl get deployments
	@echo "pods:"
	@kubectl get pods -n
	@echo "services:"
	@kubectl get services
	@echo "ingress:"
	@kubectl get ingress

tail_api_logs:
	@kubectl logs -f deployment/shieldrule-api -c shieldrule-api --since=10m