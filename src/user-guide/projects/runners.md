<div class="breadcrumbs">
    <a href="/user-guide/task-templates/">Projects</a>
    → Runners (Pro)
</div>

# Runners (Pro)

Runners are a powerful feature in Semaphore Pro that enables distributed task execution across multiple servers. This feature allows you to run tasks on separate servers from your Semaphore UI instance, providing enhanced security, scalability, and resource management.

## Overview

Runners operate on a similar principle to GitLab or GitHub Actions runners:

- A runner is deployed on a separate server from your Semaphore UI
- The runner connects to your Semaphore instance using a secure token
- When tasks are created, Semaphore delegates them to available runners
- Runners execute the tasks and report results back to Semaphore

## Benefits

Using runners provides several key advantages:

1. **Enhanced Security**
   - Runners can be deployed in isolated environments or restricted networks
   - Sensitive operations can be executed in controlled environments
   - Better separation of concerns between UI and execution environments

2. **Improved Scalability**
   - Distribute workload across multiple servers
   - Add or remove runners based on demand
   - Better resource utilization across your infrastructure

3. **Flexible Deployment**
   - Deploy runners close to your target infrastructure
   - Run tasks in different network zones
   - Support for various deployment models (on-premises, cloud, hybrid)

## Using Runners

### Prerequisites

To use runners, you need:

1. A Semaphore Pro license
2. A separate server for running the runner
3. Network connectivity between the runner and Semaphore UI
4. Proper configuration on both the Semaphore UI and runner servers

### Configuration

1. **Semaphore UI Configuration**
   Enable remote runners in your Semaphore configuration:

   ```json
   {
     "use_remote_runner": true,
     "runner_registration_token": "your-secure-token"
   }
   ```

   Or using environment variables:

   ```bash
   SEMAPHORE_USE_REMOTE_RUNNER=True
   SEMAPHORE_RUNNER_REGISTRATION_TOKEN=your-secure-token
   ```

2. **Runner Setup**
   On your runner server:

   ```bash
   # Generate runner configuration
   semaphore runner setup --config /path/to/config.json

   # Register the runner
   semaphore runner register --config /path/to/config.json

   # Start the runner
   semaphore runner start --config /path/to/config.json
   ```

### Managing Runners

You can manage runners through the Semaphore UI:

1. Navigate to the Runners section in your project
2. View all registered runners and their status
3. Add or remove runners as needed
4. Monitor runner health and performance

### Security Considerations

- Always use HTTPS for communication between runners and Semaphore UI
- Implement proper network security between runners and Semaphore UI
- Consider using isolated environments for sensitive operations

## Best Practices

1. **Resource Planning**
   - Size your runners appropriately for your workload
   - Monitor runner resource usage
   - Scale runners based on demand

2. **Network Configuration**
   - Ensure proper network connectivity
   - Configure firewalls appropriately
   - Use secure communication channels

3. **Maintenance**
   - Regularly update runner software
   - Monitor runner health
   - Implement proper logging and monitoring
   - Have a backup strategy for runner failures

4. **Security**
   - Follow the principle of least privilege
   - Implement proper access controls
   - Regular security audits
   - Keep software up to date

## Troubleshooting

Common issues and solutions:

1. **Runner Connection Issues**
   - Verify network connectivity
   - Check firewall settings
   - Validate runner registration token
   - Ensure proper SSL/TLS configuration

2. **Task Execution Problems**
   - Check runner logs
   - Verify resource availability
   - Ensure proper permissions
   - Validate task configuration

For more detailed troubleshooting, refer to the [Troubleshooting Guide](../../administration-guide/troubleshooting.md).

