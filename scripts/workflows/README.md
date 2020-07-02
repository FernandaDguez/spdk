## NVMe device performance testing workflow with Popper

[Popper](https://github.com/getpopper/popper) is a container-native workflow execution and task automation engine for defining and executing container-native workflows in Docker, as well as other container engines. 
More details about Popper can be found [here](https://popper.readthedocs.io/).

This folder contains a `wf.yml` file that defines a Popper workflow for automatically run benchmarks for a NVMe device with two different I/O engines: Linux-native asynchronous I/O access library (libaio) engine against the [SPDK block device layer](https://spdk.io/doc/bdev.html) through the [fio](https://fio.readthedocs.io/en/latest/fio_doc.html) tool, similarly to the tests presented in the [SPDK NVMe BDEV Performance Report Release 18.04](https://ci.spdk.io/download/performance-reports/SPDK_nvme_bdev_perf_report_18.04.pdf), and plots the results.


### Instructions:

1. Install [Docker](https://docs.docker.com/get-docker/) if you don't have it already.


2. Install Popper
```
curl -sSfL https://raw.githubusercontent.com/getpopper/popper/master/install.sh | sh
```

3. Clone the repository.
```
git clone https://github.com/spdk/spdk.git
```

4. Run the workflow.
```
cd spdk/
popper run -f scripts/workflows/wf.yml -c scripts/workflows/config.yml
```
