<div align="center">
    <h2 align="center"><a href="https://fossorial.io"><img alt="pangolin" src="public/logo//word_mark.png" width="400" /></a></h2>

[![Documentation](https://img.shields.io/badge/docs-latest-blue.svg?style=flat-square)](https://docs.fossorial.io/)
[![Docker](https://img.shields.io/docker/pulls/fosrl/pangolin?style=flat-square)](https://hub.docker.com/r/fosrl/pangolin)
![Stars](https://img.shields.io/github/stars/fosrl/pangolin?style=flat-square)
[![Discord](https://img.shields.io/discord/1325658630518865980?logo=discord&style=flat-square)](https://discord.gg/HCJR8Xhme4)
[![Youtube](https://img.shields.io/badge/YouTube-red?logo=youtube&logoColor=white&style=flat-square)](https://www.youtube.com/@fossorial-app)

</div>

<h3 align="center">Tunneled Mesh Reverse Proxy Server with Access Control</h3>
<div align="center">

_Your own self-hosted zero trust tunnel._

</div>

<div align="center">
  <h5>
      <a href="https://fossorial.io">
        Website
      </a>
      <span> | </span>
      <a href="https://docs.fossorial.io/Getting%20Started/quick-install">
        Install Guide
      </a>
      <span> | </span>
      <a href="mailto:numbat@fossorial.io">
        Contact Us
      </a>
  </h5>
</div>

Pangolin is a self-hosted tunneled reverse proxy server with identity and access control, designed to securely expose private resources on distributed networks. Acting as a central hub, it connects isolated networks — even those behind restrictive firewalls — through encrypted tunnels, enabling easy access to remote services without opening ports.

<img src="public/screenshots/sites.png" alt="Preview"/>

_Sites page of Pangolin dashboard (dark mode) showing multiple tunnels connected to the central server._

## Key Features

### Reverse Proxy Through WireGuard Tunnel

-   Expose private resources on your network **without opening ports** (firewall punching).
-   Secure and easy to configure site-to-site connectivity via a custom **user space WireGuard client**, [Newt](https://github.com/fosrl/newt).
-   Built-in support for any WireGuard client.
-   Automated **SSL certificates** (https) via [LetsEncrypt](https://letsencrypt.org/).
-   Support for HTTP/HTTPS and **raw TCP/UDP services**.
-   Load balancing.

### Identity & Access Management

-   Centralized authentication system using platform SSO. **Users will only have to manage one login.**
-   **Define access control rules for IPs, IP ranges, and URL paths per resource.**
-   TOTP with backup codes for two-factor authentication.
-   Create organizations, each with multiple sites, users, and roles.
-   **Role-based access control** to manage resource access permissions.
-   Additional authentication options include:
    -   Email whitelisting with **one-time passcodes.**
    -   **Temporary, self-destructing share links.**
    -   Resource specific pin codes.
    -   Resource specific passwords.

### Simple Dashboard UI

-   Manage sites, users, and roles with a clean and intuitive UI.
-   Monitor site usage and connectivity.
-   Light and dark mode options.
-   Mobile friendly.

### Easy Deployment

-   Run on any cloud provider or on-premises.
-   **Docker Compose based setup** for simplified deployment.
-   Future-proof installation script for streamlined setup and feature additions.
-   Use any WireGuard client to connect, or use **Newt, our custom user space client** for the best experience.

### Modular Design

-   Extend functionality with existing [Traefik](https://github.com/traefik/traefik) plugins, such as [CrowdSec](https://plugins.traefik.io/plugins/6335346ca4caa9ddeffda116/crowdsec-bouncer-traefik-plugin) and [Geoblock](https://github.com/PascalMinder/geoblock).
    - **Automatically install and configure Crowdsec via Pangolin's installer script.**
-   Attach as many sites to the central server as you wish.

<img src="public/screenshots/collage.png" alt="Collage"/>

## Deployment and Usage Example

1. **Deploy the Central Server**:

   - Deploy the Docker Compose stack onto a VPS hosted on a cloud platform like RackNerd, Amazon EC2, DigitalOcean Droplet, or similar. There are many cheap VPS hosting options available to suit your needs.
   
> [!TIP]
> Many of our users have had a great experience with [RackNerd](https://my.racknerd.com/aff.php?aff=13788). Depending on promotions, you can likely get a **VPS with 1 vCPU, 1GB RAM, and ~20GB SSD for just around $12/year**. That's a great deal!
> We are part of the [RackNerd](https://my.racknerd.com/aff.php?aff=13788) affiliate program, so if you purchase through [our link](https://my.racknerd.com/aff.php?aff=13788), we receive a small commission which helps us maintain the project and keep it free for everyone.

2. **Domain Configuration**:

    - Point your domain name to the VPS and configure Pangolin with your preferred settings.

3. **Connect Private Sites**:

    - Install Newt or use another WireGuard client on private sites.
    - Automatically establish a connection from these sites to the central server.

4. **Expose Resources**:

    - Add resources to the central server and configure access control rules.
    - Access these resources securely from anywhere.

**Use Case Example - Bypassing Port Restrictions in Home Lab**:  
 Imagine private sites where the ISP restricts port forwarding. By connecting these sites to Pangolin via WireGuard, you can securely expose HTTP and HTTPS resources on the private network without any networking complexity.

**Use Case Example - IoT Networks**:  
 IoT networks are often fragmented and difficult to manage. By deploying Pangolin on a central server, you can connect all your IoT sites via Newt or another WireGuard client. This creates a simple, secure, and centralized way to access IoT resources without the need for intricate networking setups.


<img src="public/screenshots/resources.png" alt="Resources"/>

_Resources page of Pangolin dashboard (dark mode) showing HTTPS and TCP resources with access control rules._

## Similar Projects and Inspirations

**Cloudflare Tunnels**:  
    A similar approach to proxying private resources securely, but Pangolin is a self-hosted alternative, giving you full control over your infrastructure.

**Authentik and Authelia**:  
    These projects inspired Pangolin’s centralized authentication system for proxies, enabling robust user and role management.

## Project Development / Roadmap

> [!NOTE]
> Pangolin is under heavy development. The roadmap is subject to change as we fix bugs, add new features, and make improvements.

View the [project board](https://github.com/orgs/fosrl/projects/1) for more detailed info.

## Licensing

Pangolin is dual licensed under the AGPL-3 and the Fossorial Commercial license. To see our commercial offerings, please see our [website](https://fossorial.io) for details. For inquiries about commercial licensing, please contact us at [numbat@fossorial.io](mailto:numbat@fossorial.io).

## Contributions

Please see [CONTRIBUTING](./CONTRIBUTING.md) in the repository for guidelines and best practices.

Please post bug reports and other functional issues in the [Issues](https://github.com/fosrl/pangolin/issues) section of the repository.
For all feature requests, or other ideas, please use the [Discussions](https://github.com/orgs/fosrl/discussions) section.
