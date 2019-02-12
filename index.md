![zplanner](./zplanner.png)
# zPlanner Docs

## About zPlanner

zPlanner is a tool that is designed to monitor disk change rates to VMware virtual machines. zPlanner leverages the PowerCLI interface to get data from vCenter and store it in a local MySQL database. This data is then manipulated and presented using Grafana.

The intended purpose of zPlanner is to help architect the number of Zerto Cloud Appliances that are required as well as how much bandwidth is needed to replicate a workload.

zPlanner is a combination of two parts, there is code that makes zPlanner work (which comes from this GitHub Repo), as well as a virtual machine that has the required packages to run the code from GitHub. In order to deploy zPlanner you should download the zPlanner appliance and it will download the latest zPlanner updates during configuration.

## What does zPlanner provide?

|  Feature  |  Details |
|----|---|
| VM Change Rate | zPlanner uses metrics captured from VMware vCenter to display actual VM disk change rates, no more guessing. |
| Replication Bandwidth | Based on change rates and compression assumptions, zPlanner displays how much bandwidth you would need to replicate a workload. |
| Hot Spot Identification | Identify which VMs are causing the most data change |
| Zerto Journal size Estimation | Not sure whether to keep 1 day or 10 days of journal? There is a zPlanner dashboard for that! |
| Zerto Cloud Appliances | Easily size your workload to the proper number of Zerto Cloud Appliances. Based on your change rate, zPlanner estimates the number of ZCAs needed. |

## Next Steps

- [Download and install zPlanner](zplanner_getting_started.md)
- [Learn how to read data in Grafana](zplanner_usage.md)
- [Remove zPlanner when your done](remove/zplanner_removal.md)

## Support

It should be noted that zPlanner is not supported by Zerto Support. It is a free tool created by [Justin Paul](https://github.com/recklessop), and supported on a best effort basis. To request support you have three options:

1. [Open zPlanner GitHub Issue](https://github.com/zerto-ta-Public/zplanner/issues)
    - Used for issues pertaining to what zPlanner does (or doesn't) do
    - Recommended for feature requests, bugs, and larger asks.
2. Open a documentation issue
    - If you spot an issue with the zPlanner documentation you can submit a pull request on this repo, use the "Improve this Doc" link on the right side column on each page.
3. [JPaul.me Drift Chat](http://jpaul.me)
    - For shorter requests or quick questions please use the Drift chat box on my blog.

## Contributing

- Submit a pull request
- open an issue

## Disclaimer

### Simple version

zPlanner is written and maintained by me, not Zerto. zPlanner uses read-only access to your vCenter server and has been rigorously tested to make sure it won’t hurt anything. However, use it at your own risk. I take no responsibility if you hurt your environment with it.

Feel free to view all of the code that zPlanner uses on it's [Github repo](http://github.com/Zerto-TA-Public/zPlanner) and decide for yourself if it’s safe to use.

### Lawyer Version

zPlanner is not supported under any Zerto support program or service. The author and Zerto further disclaim all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.

In no event shall Zerto, its authors or anyone else involved in the creation, production or delivery of zPlanner be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or the inability to use zPlanner or documentation, even if the author or Zerto has been advised of the possibility of such damages. The entire risk arising out of the use or performance of zPlanner and documentation remains with you.