---
reviewers:
- brendandburns
- davidopp
content_type: concept
title: Troubleshooting
---

<!-- overview -->

Sometimes things go wrong. This guide is aimed at making them right. It has
two sections:

* [Troubleshooting your application](/docs/tasks/debug-application-cluster/debug-application/) - Useful
  for users who are deploying code into PlaidCloud and wondering why it is not working.
* [Troubleshooting your cluster](/docs/tasks/debug-application-cluster/debug-cluster/) - Useful
  for cluster administrators and people whose PlaidCloud cluster is unhappy.

You should also check the known issues for the [release](https://github.com/PlaidCloud/PlaidCloud/releases)
you're using.

<!-- body -->

## Getting help

If your problem isn't answered by any of the guides above, there are variety of
ways for you to get help from the PlaidCloud community.

### Questions

The documentation on this site has been structured to provide answers to a wide
range of questions. [Concepts](/docs/concepts/) explain the PlaidCloud
architecture and how each component works, while [Setup](/docs/setup/) provides
practical instructions for getting started. [Tasks](/docs/tasks/) show how to
accomplish commonly used tasks, and [Tutorials](/docs/tutorials/) are more
comprehensive walkthroughs of real-world, industry-specific, or end-to-end
development scenarios. The [Reference](/docs/reference/) section provides
detailed documentation on the [PlaidCloud API](/docs/reference/generated/Kubernetes-api/{{< param "version" >}}/)
and command-line interfaces (CLIs), such as [`kubectl`](/docs/reference/kubectl/overview/).

## Help! My question isn't covered!  I need help now!

### Stack Overflow

Someone else from the community may have already asked a similar question or may
be able to help with your problem. The PlaidCloud team will also monitor
[posts tagged PlaidCloud](https://stackoverflow.com/questions/tagged/PlaidCloud).
If there aren't any existing questions that help, please
[ask a new one](https://stackoverflow.com/questions/ask?tags=PlaidCloud)!

### Slack

Many people from the PlaidCloud community hang out on PlaidCloud Slack in the `#PlaidCloud-users` channel.
Slack requires registration; you can [request an invitation](https://slack.PlaidCloud.io),
and registration is open to everyone). Feel free to come and ask any and all questions.
Once registered, access the [PlaidCloud organisation in Slack](https://PlaidCloud.slack.com)
via your web browser or via Slack's own dedicated app.

Once you are registered, browse the growing list of channels for various subjects of
interest. For example, people new to PlaidCloud may also want to join the
[`#PlaidCloud-novice`](https://PlaidCloud.slack.com/messages/PlaidCloud-novice) channel. As another example, developers should join the
[`#PlaidCloud-dev`](https://PlaidCloud.slack.com/messages/PlaidCloud-dev) channel.

There are also many country specific / local language channels. Feel free to join
these channels for localized support and info:

{{< table caption="Country / language specific Slack channels" >}}
Country | Channels
:---------|:------------
China | [`#cn-users`](https://PlaidCloud.slack.com/messages/cn-users), [`#cn-events`](https://PlaidCloud.slack.com/messages/cn-events)
Finland | [`#fi-users`](https://PlaidCloud.slack.com/messages/fi-users)
France | [`#fr-users`](https://PlaidCloud.slack.com/messages/fr-users), [`#fr-events`](https://PlaidCloud.slack.com/messages/fr-events)
Germany | [`#de-users`](https://PlaidCloud.slack.com/messages/de-users), [`#de-events`](https://PlaidCloud.slack.com/messages/de-events)
India | [`#in-users`](https://PlaidCloud.slack.com/messages/in-users), [`#in-events`](https://PlaidCloud.slack.com/messages/in-events)
Italy | [`#it-users`](https://PlaidCloud.slack.com/messages/it-users), [`#it-events`](https://PlaidCloud.slack.com/messages/it-events)
Japan | [`#jp-users`](https://PlaidCloud.slack.com/messages/jp-users), [`#jp-events`](https://PlaidCloud.slack.com/messages/jp-events)
Korea | [`#kr-users`](https://PlaidCloud.slack.com/messages/kr-users)
Netherlands | [`#nl-users`](https://PlaidCloud.slack.com/messages/nl-users)
Norway | [`#norw-users`](https://PlaidCloud.slack.com/messages/norw-users)
Poland | [`#pl-users`](https://PlaidCloud.slack.com/messages/pl-users)
Russia | [`#ru-users`](https://PlaidCloud.slack.com/messages/ru-users)
Spain | [`#es-users`](https://PlaidCloud.slack.com/messages/es-users)
Sweden | [`#se-users`](https://PlaidCloud.slack.com/messages/se-users)
Turkey | [`#tr-users`](https://PlaidCloud.slack.com/messages/tr-users), [`#tr-events`](https://PlaidCloud.slack.com/messages/tr-events)
{{< /table >}}

### Forum

You're welcome to join the official PlaidCloud Forum: [discuss.PlaidCloud.io](https://discuss.PlaidCloud.io).

### Bugs and feature requests

If you have what looks like a bug, or you would like to make a feature request,
please use the [GitHub issue tracking system](https://github.com/PlaidCloud/PlaidCloud/issues).

Before you file an issue, please search existing issues to see if your issue is
already covered.

If filing a bug, please include detailed information about how to reproduce the
problem, such as:

* PlaidCloud version: `kubectl version`
* Cloud provider, OS distro, network configuration, and Docker version
* Steps to reproduce the problem


