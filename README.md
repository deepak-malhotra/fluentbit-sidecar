# Fluent-Bit Sidecar for Kubernetes

Run [Fluent-Bit](http://fluentbit.io/) as a sidecar to collect logs and output them to STDOUT in a Kubernetes cluster. Fluent-Bit is configured in this example to tail a named directory (for the example: /mnt/log/reference-logging.txt) and collect all logs from the file.

This example creates a Pod with 2 containers.  app-container prints to a file and sidercar container captures the file data and streams it to stdout. The sider runs fluent-bit. 

## Usage

To deploy in a Kubernetes cluster:

```kubectl -f create fluent-bit-sidecar.yaml```

The Docker image I have used is not the standard one. Fluent-bit has a minimal image which dosn't include any standard tools, however for the purpose of demo, I used the deug image.  The Dockerfile used for creating the image can be found in the repo.

## History

Previously FluentD was the de-Facto option for log generation. Fluent Bit is fully designed and built on top of the best ideas of Fluentd architecture and general design. Choosing which one to use depends on the end-user needs.
The following table describes a comparison in different areas of the projects:

![image](https://user-images.githubusercontent.com/63465751/116834542-eca34580-ac01-11eb-9e99-7f25b27150d7.png)
