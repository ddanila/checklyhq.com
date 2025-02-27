---
title: Getting started with private locations
weight: 51
menu:
  docs:
    parent: "Private Locations"
aliases:
- "/docs/private-locations/private-locations-getting-started/"
---

{{<info>}}
Note: The Checkly Agent currently only supports x86/AMD64 architecture and not ARM64. This means Apple Mac M1 systems are not currently supported.
{{</info>}}

## About Private Locations

**You must have the Owner or Admin role on your Checkly account to create private locations.**

Here are the requirements/questions before you get started:

- Container runtime (we test using Docker, but other OCI-compliant runtimes should work)
- Outbound internet access to https://agent.checklyhq.com (proxy configuration is supported)
- Access to your internal API- or browser-based application
- A Checkly account that you will use for testing Private Locations

Here's how private locations work:

A private location is similar to our existing public locations, but you have control over it. A private location can be in your own segregated network,  on-premises or cloud-based. You need one or more Checkly Agents installed in that location/network with access to your applications. Checkly checks are configured and scheduled in the Checkly cloud-based web UI as usual, but selecting a private location runs the check on the agent(s) in your infrastructure. Agents are stateless and ephemeral. As long as you have at least one operational agent, checks will run in your private location. Adding more agents will distribute the load and improve resilience automatically.

## Configuring a Private Location:

1) Log in to your Checkly account.

2) Navigate to the Private Locations settings page.

![private locations settings](/docs/images/private-locations/private_locations_settings.png)

3) Click the New Private Location button.

4) Provide a name and icon for the new private location. The ID is automatically generated ID for API access.

![new private location](/docs/images/private-locations/new_private_location.png)

5) Click Create.

6) You will receive an API key for the new location. Copy this key and keep it safe as you will need it to add agents to the location, and you won’t be able to see it again.

![private location key](/docs/images/private-locations/private_location_key.png)

7) You now see your new private location in the list with no agents installed.

![private location added](/docs/images/private-locations/private_location_added.png)

8) Follow the detailed instructions in the [installing Checkly agent guide](/docs/private-locations/checkly-agent-guide/) to install one or more Checkly agents for the private location.

9) Refresh the private locations page in the Checkly app and you will see a count of the number of running agents.

![agent running](/docs/images/private-locations/agent_running.png)

10) Create a new API or Browser check as you normally would in Checkly. You will now see your new private location in the list of available locations. Select it and deselect any other locations.

![select private location](/docs/images/private-locations/select_private_location.png)

11) Finish configuring your check and save it.

12) You can now see the results in the check results page.

![private location results](/docs/images/private-locations/private_location_results.png)
