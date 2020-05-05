# Cloud Computing - Laboratory 05: Cloud Pricing

Authors : Baptiste Hardrick & David Jaquet

## Task 1: Compute pricing

We analyze the price of the global big three cloud providers and a regional cloud provider by using the price calculator available on the site of each provider. Theses providers are [Amazon Web Services](https://calculator.s3.amazonaws.com/index.html), [Google Cloud Platform](https://cloud.google.com/products/calculator), [Microsoft Azure](https://azure.microsoft.com/en-us/pricing/calculator/) and the regional one is [Exoscale](https://www.exoscale.com/pricing/). The price calculator is available on each links.

Exoscale gave us the price in Euros. We convert this price in dollars to have the same currency for every providers. To do that, we use the calculator [XE](https://www.xe.com/). It is the reference for the interbank exchange rate.

The laboratory asked us to find the price for a Virtual Machin with disk with the following characteristics:

- 4 virtual CPUs
- 16 GiB memory
- 320 GB SSD

Furthermore, as asked in the laboratory, we make the following assumptions :

- General purpose instance type, not optimized for memory, compute, disk I/O or any other specific task.
- Linux operating system on the VM, no license fee for a proprietary operating system such as Windows.
- On-demand or pay-as-you-go pricing, no upfront payment for receiving price reductions (such as "reserved instances").
- If several regions are available and prices differ, we took the region that is shown by default.
- We do not take into account special introductory offers (such as the AWS Free Tier or similar).

We have not found a Virtual Machine with the characteristics identical as the one asked for every provider. So in the table below, the choice made for each provider is in the **Remarks** column. When we had a choice between two similar options from the same cloud provider, we tried to choose the cheapest one.

| Cloud provider        | Price per month   | Remarks                                                      |
| --------------------- | ----------------- | ------------------------------------------------------------ |
| Amazon Web Services   | $150.80           | The instance is the Linux on `m5ad.xlarge` with a 150 GB of SSD |
| Google Cloud Platform | $127.09           | 15 GB of memory and 375 GB of SSD disk                       |
| Microsoft Azure       | $163.94           | The instance is the `B4MS` with 32 GB of Temporary storage and we add a 256 GiB of SSD |
| Exoscale              | €145.70 = $159.34 |                                                              |

For the Amazon Web Services, we chose the version with 150 GB of SSD disk. We made this decision because our other option was a 1250 SSD disk (and this disk is obviously more expensive).

The highest monthly price is **Microsoft** with a cost of **$163.94** and the lowest is **Google Cloud Platform** with a cost of **$127.09**. So the monthly price of Google Cloud Platform is **~77.5%** cheaper than Microsoft Azure. It is interesting to notice that the solution with the 375 GB of SSD disk from Google is cheaper than an instance with 320 GB from an another cloud provider.

## Task 2: Data pricing

For this task, we compared only two cloud provider ; Amazon Web Services and Google Cloud Platform. We use the same calculator than the one for previous task.

### Data storage

This part is a comparison of the cost of storing 1 TB of data for a month.

| Storage method                         | Price per month | Remarks                                                      |
| -------------------------------------- | --------------- | ------------------------------------------------------------ |
| Amazon Elastic Block Store             | $102.40         |                                                              |
| Google Compute Engine Persistent Disks | $174.08         |                                                              |
| Amazon S3                              | $23.56          |                                                              |
| Google Cloud Storage                   | $20.48          |                                                              |
| SSD Disk bought at Digitec             | $3.25           | We choose [this disk](https://www.digitec.ch/fr/s1/product/samsung-860-qvo-1000go-25-ssd-10212273). The price has been convert in dollar ($117.11) and amortize on 3 years. |

Amazon S3 stores datas and objects, but Amazon Elastic Block Store (EBS) is a block storage system and can deal with different tasks (like databases, containerized applications, big data analysis engines, ...). The EBS service of Amazon is more expensive than the S3 service for this reason.

Google has the same difference. Instead of the S3 service from Amazon, we have the Google Cloud Storage and instead of the EBS, we have the Google Compute Engine Persistent Disks. This is why we cannot compare the four services together. However, we can compare Amazon Elastic Block Search with Google Compute Engine Persistent Disks (and we can see that Amazon is cheaper than Google) and we can make a second comparison between Amazon S3 and Google Cloud Storage (and we can see, this time, that Google is cheaper than Amazon).

Furthermore, the comparison of the services mentioned above and the SSD disk bought is not relevant either. It is obviously cheaper to have a disk, but we do not have all other services and benefits offered by a cloud provider.

### Data transfer

This  part is a comparison of the cost of transferring 1 TB of data from the Internet to the cloud object store service ("transfer in") and from the cloud store service to the Internet ("transfer out"). As asked, we assume that we transfer not more than 1 TB per month, so we ignore the decrease of the prices.

| Cloud Provider           | Price per month | Remarks |
| ------------------------ | --------------- | ------- |
| Amazon 1 TB transfer in  | Free            |         |
| Google 1 TB transfer in  | Free            |         |
| Amazon 1 TB transfer out | $92.07          |         |
| Google 1 TB transfer out | $122.76         |         |

