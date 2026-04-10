# AtlasGraph Service Instance Deployment Documentation

## Overview

AtlasGraph is a high-performance graph database independently developed by Haizhi Xingtu. You can quickly deploy AtlasGraph on Compute Nest to build your own graph applications. This document introduces how to activate the AtlasGraph service on Compute Nest, as well as the deployment process and usage instructions.

We welcome everyone to apply for use. If you encounter any issues during usage, please feel free to provide feedback.

## Deployment Process

Before starting, you need an Alibaba Cloud account with permissions to access and create resources such as ECS and VPC.

- If you are using a personal account, you can create a service instance directly.
- If you are using a RAM user to create a service instance and it is your first time using Alibaba Cloud Compute Nest:
    - You must add the necessary resource permissions to the RAM user account before creating the service instance. For detailed operations on adding RAM permissions, please refer to [Authorize RAM Users](https://help.aliyun.com/document_detail/121945.html). The required permissions are listed in the table below.

| Permission Policy Name              | Description                                  |
|-------------------------------------|----------------------------------------------|
| AliyunECSFullAccess                 | Permissions to manage Elastic Compute Service (ECS) |
| AliyunVPCFullAccess                 | Permissions to manage Virtual Private Cloud (VPC)   |
| AliyunROSFullAccess                 | Permissions to manage Resource Orchestration Service (ROS) |
| AliyunComputeNestUserFullAccess     | User-side permissions to manage Compute Nest services |

### 1. Deployment Entry

You can search for it directly in Alibaba Cloud Compute Nest, or use the deployment link below to access it quickly.

[Deployment Link](https://computenest.console.aliyun.com/service/instance/create/cn-hangzhou?type=user&ServiceId=service-0aabc7f118d148c1bbfc)

### 2. Create AtlasGraph Service

#### 2.1 Parameter List

During the creation of the service instance, you need to configure the parameters for the service instance information as follows:

| Parameter Group               | Parameter Item   | Example          | Description                                                           |
|-------------------------------|------------------|------------------|-----------------------------------------------------------------------|
| Service Instance Name         | N/A              | atlas_graph-2v30 | The name of the instance.                                             |
| Region                        | N/A              | China North 2 (Beijing) | Select the region for the service instance. It is recommended to select the nearest region for better network latency. |
| Existing Basic Resource Config| VPC ID           | vpc-xxx          | Select the VPC ID according to actual conditions.                     |
| Availability Zone Config      | Deployment Zone  | Zone I           | Different availability zones within the region. Ensure the zone has resources. |
| Existing Basic Resource Config| vSwitch ID       | vsw-xxx          | Select the vSwitch ID according to actual conditions. If no vSwitch is found, try switching regions or availability zones. |
| Existing Basic Resource Config| K8s Cluster ID   | xxx/xxx          | Select the Container Service for Kubernetes (ACK) cluster ID according to actual conditions. |
| K8s Namespace for App Deployment | N/A           | atlasgraph       | Select a namespace that does not yet exist in the cluster.            |
| Billing Configuration         | Billing Method   | Pay-As-You-Go    | Choose Pay-As-You-Go or Subscription based on your needs.             |

#### 2.2 Specific Steps

Follow the steps below to create the service:

- Create an instance name, e.g., "atlas_graph-2v30" as shown in the figure.
- Select the region, e.g., "China North 2 (Beijing)" as shown in the figure.

- Select VPC ID.
- Select Availability Zone.
- Select vSwitch ID.

- Select K8s Cluster ID.
- Set the K8s namespace for application deployment.

- Select Billing Method.

- Click **Next** to enter the order confirmation page.
- Check the boxes for "Permission Confirmation" and "Service Terms".
- Click **Create Now** and wait for the service to deploy automatically.

### 3. Start AtlasGraph Service

- **View Service Instance**: After the service instance is created successfully, the deployment takes approximately 3 minutes. Once deployed, the corresponding service instance will be visible on the page.

- Click on the service instance to access AtlasGraph. Inside the service instance page, you can obtain the Web IP address.

- Use this web address to access the deployed AtlasGraph Web interface.

- Log in using the default username and password (`root`/`root`) to enter the AtlasGraph Web homepage.

## Frequently Asked Questions (FAQ)

### Issue 1: No Available Resources in Deployment Zone

Sometimes, the selected deployment zone (e.g., Zone G) may not have available resources for the selected package, resulting in an error as shown in the figure.

**Solution**: Try selecting a different zone, such as Zone I.

### Issue 2: Web Access Unavailable After Startup

The web service takes a short time to start. Please refresh the page after a brief wait.

## Contact Us

Welcome to visit the AtlasGraph official website ([https://www.stargraph.cn](https://www.stargraph.cn)) for more information.

Scan the QR code to follow our WeChat Official Account so you don't miss technical blogs and event notifications:
