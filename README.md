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

We have not find a Virtual Machine with the characteristics identical as the one asked for every provider. So in the table below, the choice made for each provider is in the **Remarks** column.

| Cloud provider        | Price per month   | Remarks                                                      |
| --------------------- | ----------------- | ------------------------------------------------------------ |
| Amazon Web Services   | $150.80           | Instance type: Linux on `m5ad.xlarge`                        |
| Google Cloud Platform | $127.09           | R                                                            |
| Microsoft Azure       | $163.94           | The instance is the `B4MS` with 32 GB of Temporary storage and we add a 256 GiB SSD |
| Exoscale              | €145.70 = $159.34 |                                                              |

The highest monthly price is **Microsoft** with a cost of **$163.94** and the lowest is **Google Cloud Platform** with a cost of **$127.09**. So the monthly price of Google Cloud Platform is **~77.5%** cheaper than Microsoft Azure.

## Task 2: Data pricing

