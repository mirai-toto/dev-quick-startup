# dev-quick-startup

Installs and configures a development environment with various tools and utilities. Uses Ansible to automate installation and setup.

## Features

Installs essential tools and configuration for the development environment:

- **npm**
- **Python 3**
- **Java 21**
- **Docker**
- **k3s** or **kubeadm**
- **k9s**
- **Helm**
- Sets proxy values for the WSL instance.
- Configures WSL settings in `wsl.conf`.

## Installation

To use Dev Quick Startup, follow these steps:

1. Clone this repository.

2. Review and edit the `group_vars/all` file to fit your environment.

3. Run the Ansible playbook:

   ```bash
   ansible-playbook -i hosts.ini setup-wsl.yml
   ```

## Configuration

Below are the variables you can configure in `group_vars/all`:

| Name               | Description                                                        | Example   |
| ------------------ | ------------------------------------------------------------------ | --------- |
| `use_k3s`          | Determines whether to use k3s (lightweight Kubernetes) or kubeadm. | `true`    |
| `dev_user`         | The username to create in the environment.                         | `my-user` |
| `create_user`      | Boolean value indicating whether to create a user.                 | `true`    |
| `dev_password`     | The password for the user created.                                 | `root`    |
| `proxy_parameters` | Configuration for proxy usage.                                     | See below |

### Proxy Parameters

| Name          | Description                    | Example                          |
| ------------- | ------------------------------ | -------------------------------- |
| `use_proxy`   | Enable or disable proxy usage. | `false`                          |
| `http_proxy`  | HTTP proxy URL.                | `http://proxy.example.com:8080`  |
| `https_proxy` | HTTPS proxy URL.               | `https://proxy.example.com:8080` |
| `no_proxy`    | No proxy URLs                  | `localhost,127.0.0.1`            |

## Support

If you have any questions or issues with Dev Quick Startup, please create a new issue in the [GitHub repository](https://github.com/mirai-toto/dev-quick-startup/issues).

## License

Dev Quick Startup is released under the [MIT License](LICENSE).

## Credits

Dev Quick Startup was created by [mirai-toto](https://github.com/mirai-toto).

## Acknowledgements

Special thanks to the contributors of the open-source tools used in this project, including Ansible, Docker, k3s, kubeadm, k9s and Helm.
