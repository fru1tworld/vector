The custom `ObservabilityService/Health` RPC on the observability API (port 8686) has been replaced
with the standard `grpc.health.v1.Health` service. This enables native Kubernetes gRPC health probes,
`grpc-health-probe`, and other standard gRPC health-checking tooling to work out of the box.

Clients that previously called `ObservabilityService/Health` should switch to the standard
`grpc.health.v1.Health/Check` RPC with an empty service name.
