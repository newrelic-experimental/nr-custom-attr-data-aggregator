<a href="https://opensource.newrelic.com/oss-category/#new-relic-experimental"><picture><source media="(prefers-color-scheme: dark)" srcset="https://github.com/newrelic/opensource-website/raw/main/src/images/categories/dark/Experimental.png"><source media="(prefers-color-scheme: light)" srcset="https://github.com/newrelic/opensource-website/raw/main/src/images/categories/Experimental.png"><img alt="New Relic Open Source experimental project banner." src="https://github.com/newrelic/opensource-website/raw/main/src/images/categories/Experimental.png"></picture></a>

![GitHub forks](https://img.shields.io/github/forks/newrelic-experimental/nr-custom-attr-data-aggregator?style=social)
![GitHub stars](https://img.shields.io/github/stars/newrelic-experimental/nr-custom-attr-data-aggregator?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/newrelic-experimental/nr-custom-attr-data-aggregator?style=social)

![GitHub last commit](https://img.shields.io/github/last-commit/newrelic-experimental/nr-custom-attr-data-aggregator)

![GitHub issues](https://img.shields.io/github/issues/newrelic-experimental/nr-custom-attr-data-aggregator)
![GitHub issues closed](https://img.shields.io/github/issues-closed/newrelic-experimental/nr-custom-attr-data-aggregator)
![GitHub pull requests](https://img.shields.io/github/issues-pr/newrelic-experimental/nr-custom-attr-data-aggregator)
![GitHub pull requests closed](https://img.shields.io/github/issues-pr-closed/newrelic-experimental/nr-custom-attr-data-aggregator)


## Custom attribute data aggregator

>Queries New Relic data for delimited fields, gathers unique values and reingests for use in dashboard filters.
> Intended to run in an synthetic monitor on a regular frequency, can also be run locally for testing.

# Installation

## Send the test data to your account:
```
export NR_INGEST_KEY="...NRAL"
export NR_QUERY_KEY="NRAK-..."
export NR_ACCOUNT_ID="000000"

gzip -c test_data.json | curl -X POST -H "Content-Type: application/json" -H "Api-Key: ${NR_INGEST_KEY}" -H "Content-Encoding: gzip" "https://insights-collector.newrelic.com/v1/accounts/${NR_ACCOUNT_ID}/events" --data-binary @-

gzip -c test_data2.json | curl -X POST -H "Content-Type: application/json" -H "Api-Key: ${NR_INGEST_KEY}" -H "Content-Encoding: gzip" "https://insights-collector.newrelic.com/v1/accounts/${NR_ACCOUNT_ID}/events" --data-binary @-
```

## Run the script:
```
npm install
node generateData.sh
```

# Usage

## Query the data:

```
select * from dashFilterData
```

# Support

New Relic hosts and moderates an online forum where customers can interact with New Relic employees as well as other customers to get help and share best practices. Like all official New Relic open source projects, there's a related Community topic in the New Relic Explorers Hub. You can find this project's topic/threads here:

> https://forum.newrelic.com/s/
> https://github.com/dpacheconr/nr-custom-attr-data-aggregator

# Contributing
We encourage your contributions to improve Custom attribute data aggregator! Keep in mind when you submit your pull request, you'll need to sign the CLA via the click-through using CLA-Assistant. You only have to sign the CLA one time per project.
If you have any questions, or to execute our corporate CLA, required if your contribution is on behalf of a company,  please drop us an email at opensource@newrelic.com.

**A note about vulnerabilities**

As noted in our [security policy](../../security/policy), New Relic is committed to the privacy and security of our customers and their data. We believe that providing coordinated disclosure by security researchers and engaging with the security community are important means to achieve our security goals.

If you believe you have found a security vulnerability in this project or any of New Relic's products or websites, we welcome and greatly appreciate you reporting it to New Relic through [HackerOne](https://hackerone.com/newrelic).

# License
Custom attribute data aggregator is licensed under the [Apache 2.0](http://apache.org/licenses/LICENSE-2.0.txt) License.
>The Custom attribute data aggregator also uses source code from third-party libraries. You can find full details on which libraries are used and the terms under which they are licensed in the third-party notices document.
