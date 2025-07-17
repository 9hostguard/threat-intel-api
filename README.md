// SPDX-License-Identifier: MIT
pragma solidity 0.8.19;
import "@chainlink/contracts-ccip/src/v0.8/ccip/applications/CCIPReceiver.sol";

contract ThreatReporter is CCIPReceiver {
  event ThreatDetected(string message);
  
  constructor(address router) CCIPReceiver(router) {}
  
  function reportThreat(string memory threatData) external {
    emit ThreatDetected(threatData);
  }
}
