/**
 * GitHub Portfolio Report: Sandboxed Networks
 * This TypeScript code documents the configuration, challenges, and implementation of a sandboxed network environment.
 */

// Network Architecture
const networkArchitecture = {
  subnets: [
    {
      id: 1,
      range: "192.168.13.x",
      devices: [
        { name: "Desktop 1", ip: "192.168.13.4" },
        { name: "Desktop 2", ip: "192.168.13.6" },
        { name: "Gateway Router (enp0s9)", ip: "192.168.13.1" }
      ]
    },
    {
      id: 2,
      range: "192.168.113.x",
      devices: [
        { name: "Desktop 3", ip: "192.168.113.6" },
        { name: "Server", ip: "192.168.113.4" },
        { name: "Gateway Router (enp0s8)", ip: "192.168.113.1" }
      ]
    }
  ]
};

// Configuration Steps
const configurationSteps = [
  "Configured VirtualBox adapters for NAT (Adapter 3) and Internal Network (Adapters 1 and 2).",
  "Assigned static IP addresses to devices within their respective subnets.",
  "Set up Gateway Router to route packets between Subnet 1 and Subnet 2.",
  "Enabled NAT on the Gateway Router to provide internet access.",
  "Tested connectivity using ping and traceroute.",
  "Adjusted iptables on the Gateway Router to allow inter-subnet traffic."
];

// Challenges and Resolutions
const challengesAndResolutions = [
  {
    issue: "Adapter Misconfiguration",
    resolution: "Verified adapter settings and corrected Internal Network assignments."
  },
  {
    issue: "Routing Issues",
    resolution: "Added static routes on the Gateway Router and tested with traceroute."
  },
  {
    issue: "DNS Resolution Errors",
    resolution: "Updated /etc/resolv.conf with public DNS server addresses."
  },
  {
    issue: "Firewall Restrictions",
    resolution: "Modified iptables rules to enable inter-subnet traffic and NAT masquerading."
  },
  {
    issue: "Overlapping IP Ranges",
    resolution: "Reassigned non-overlapping IP ranges to devices in different subnets."
  }
];

// Function to Display Report
function displayReport(): void {
  console.log("GitHub Portfolio Report: Sandboxed Networks");
  console.log("============================");

  console.log("\nNetwork Architecture:");
  console.log(JSON.stringify(networkArchitecture, null, 2));

  console.log("\nConfiguration Steps:");
  configurationSteps.forEach((step, index) => {
    console.log(`${index + 1}. ${step}`);
  });

  console.log("\nChallenges and Resolutions:");
  challengesAndResolutions.forEach((challenge, index) => {
    console.log(`${index + 1}. Issue: ${challenge.issue}`);
    console.log(`   Resolution: ${challenge.resolution}`);
  });
}


displayReport();


