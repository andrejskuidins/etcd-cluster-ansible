# HA etcd Cluster Deployment with Ansible
This repository contains Ansible playbooks and roles to deploy a highly available (HA) etcd cluster across multiple nodes. The setup includes PKI for secure communication, interface isolation, and multi-tenancy support.

## Features
Highly Available etcd Cluster: Deployed across multiple nodes for fault tolerance.

PKI Enabled: Secure communication using TLS certificates.

Interface Isolation: etcd listens on specific network interfaces for peer and client communication.

Multi-Tenancy: Support for tenant roles and users with granular permissions.

Authentication: Root and tenant users with role-based access control (RBAC).

## Configuration
Interface Isolation
etcd is configured to listen on specific network interfaces for peer and client communication.

Replace enp39s0 with the appropriate network interface for each node.

## PKI and Certificates
CA Certificate: Used to sign server and client certificates.

Server Certificates: Unique certificates for each etcd node.

Client Certificates: Used for secure communication with etcd.

Certificates are stored in /etc/etcd/ssl/ on each node.

### Authentication
Root User: The root user is created with full access to the etcd cluster.

Tenant Users: Tenant-specific users are created with restricted permissions based on their roles.

### Multi-Tenancy
Tenant Roles: Roles are created with specific permissions (e.g., readwrite access to a tenant-specific prefix).

Tenant Users: Users are granted roles to access their respective prefixes.

## Deployment
Prerequisites
Ansible installed on the control machine.

SSH access to all etcd nodes.

Certificates pre-generated and available for deployment.