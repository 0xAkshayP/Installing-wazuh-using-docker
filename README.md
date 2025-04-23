# Installing-wazuh-using-docker
  <h1>Wazuh Docker Installation Guide</h1>

  <h2>Requirements</h2>
  <ul>
    <li>Minimum 6 GB of memory on the Docker host.</li>
    <li>Linux system with amd64 architecture and kernel version 3.10 or later.</li>
    <li>Docker and Docker Compose (v1.29 or later).</li>
    <li>Root user privileges.</li>
  </ul>

  <h2>Check Your Kernel Version</h2>
  <pre><code>uname -r</code></pre>

  <h2>Set vm.max_map_count</h2>
  <pre><code>sudo sysctl -w vm.max_map_count=262144

# To make it permanent
echo 'vm.max_map_count=262144' | sudo tee -a /etc/sysctl.conf
sudo sysctl -p</code></pre>

  <h2>Install Docker</h2>
  <h3>Ubuntu/Debian</h3>
  <pre><code>curl -sSL https://get.docker.com/ | sh
sudo systemctl start docker</code></pre>

  <p>Optional: Use Docker as a non-root user</p>
  <pre><code>sudo usermod -aG docker $USER
# Log out and log back in</code></pre>

  <h2>Install Docker Compose</h2>
  <pre><code>sudo curl -L "https://github.com/docker/compose/releases/download/v2.12.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

# Check version
docker-compose --version</code></pre>

  <h2>Next Steps</h2>
  <p>Proceed with cloning the <code>wazuh-docker</code> GitHub repository and deploying your Wazuh stack using <code>docker-compose</code>.</p>

</body>
</html>
