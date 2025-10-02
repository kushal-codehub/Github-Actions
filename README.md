<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
</head>
<body>

  <p> <h2>
    This repository contains <strong>GitHub Actions workflows</strong> that automate tasks such as 
    validating files, deploying to AWS S3, and managing Nginx on EC2 instances. </h2>
  </p>

  <h2>📌 Workflows</h2>

  <h3>1. First Workflow (<code>First_workflow.yml</code>)</h3>
  <p><strong>Triggered on:</strong></p>
  <ul>
    <li>Push events to the <strong>main</strong> branch</li>
    <li>Manual workflow dispatch</li>
  </ul>
  <p><strong>What it does:</strong></p>
  <ul>
    <li>Clones the repository.</li>
    <li>Checks if <code>index.html</code> exists in the root directory.</li>
    <li>Fails the workflow if the file is missing.</li>
    <li>Runs success steps only if the file exists.</li>
  </ul>

  <h3>2. Second Workflow (<code>second_workflow.yml</code>)</h3>
  <p><strong>Triggered on:</strong></p>
  <ul>
    <li>Manual workflow dispatch</li>
  </ul>
  <p><strong>What it does:</strong></p>
  <ul>
    <li>Clones the repository.</li>
    <li>Configures AWS credentials using repository secrets.</li>
    <li>Uploads <code>index.html</code> to an <strong>S3 bucket</strong> (<code>homework-1212</code>).</li>
    <li>Uses <strong>AWS SSM (Systems Manager)</strong> to:
      <ul>
        <li>Install and start <strong>Nginx</strong> on an EC2 instance.</li>
        <li>Copy <code>index.html</code> from S3 to <code>/usr/share/nginx/html/</code> on the EC2 instance.</li>
        <li>Serve the file via Nginx.</li>
      </ul>
    </li>
  </ul>

  <h2>🔑 Secrets Required</h2>
  <p>Configure these <strong>GitHub Secrets</strong> in your repository:</p>
  <ul>
    <li><code>AWS_ACCESS_KEY_ID</code></li>
    <li><code>AWS_SECRET_ACCESS_KEY</code></li>
    <li><code>AWS_REGION</code></li>
    <li><code>EC2_INSTANCE_ID</code></li>
  </ul>

  <h2>📂 Files</h2>
  <ul>
    <li><code>First_workflow.yml</code> → Validates <code>index.html</code> presence.</li>
    <li><code>second_workflow.yml</code> → Deploys the file to AWS S3 & EC2.</li>
  </ul>

</body>
</html>
