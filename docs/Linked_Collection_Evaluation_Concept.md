# Linked *Ad Hoc* Collection & Evaluation Concept
This paper describes a notional use case where an _ad hoc_
collection is invoked and the status messages signaling its
completion trigger a corresponding _ad hoc_ evaluation of the
newly collected data. This approach includes use of the currently
undefined OpenC2 `notification` message type. The PACE project
provides excellent use cases for substantiating the need for this
message type.

The essential notion for this concept is that the Posture
Evaluation Service (PES) monitors the command channel for the
Posture Collection Service (PCS). Detection of collection
instructions sent to the PCS puts the PES "on deck" to perform a
corresponding evalution, and detection of a completion notice
acts as a virtual command to start the evaluation.

## Publish/Subscribe Topics

This example employs the following pub/sub topics (the naming
used here is notional and based on the in-development *OpenC2
MQTT Transfer Specification*):

* `oc2/cmd/ap/pcs` -- command channel for the PCS
  * published to by the Manager / Orchestrator
  * monitored by the PCS for tasking
  * monitored by the PES for situational awareness
* `oc2/rsp` -- response topic for OpenC2 commands
  * monitored by the Manager/Orchestrator
  * published to by any element sending an OpenC2 response
* `oc2/ntf` -- notification topic for asynchronous notification messages
  * monitored by the Manager/Orchestrator, PCS, PES, potentially other elements
  * published to by any element with status information to share

## Scenario

1. The Manager/Orchestrator determines an _ad hoc_ posture
   attribute collection is needed. It publishes collection
   instructions in the form of an OpenC2 `query` action to
   `oc2/cmd/ap/pcs`, with arguments specifying what is to be
   collected.
2. The PCS detects the `query` action, publishes an OpenC2
   response message to `oc2/rsp` acknowledging the command, and
   being the attribute collection process. The PCS may publish
   process indicator messages to the `oc2/ntf` channel as
   collection proceeds.
3. The PES detects the `query` action on `oc2/cmd/ap/pcs` and
   recognizes that an _ad hoc_ collection has started. The PES
   begins monitoring `oc2/ntf` for status messages related to the
   collection, using the OpenC2 `command_id` value to correlate
   notifications to the original command.
1. When the PCS has completed the collection of the requested
   attributes, the results are persisted to the Posture Attribute
   Repository (mechanism TBD; illustrated in the sequence diagram as an OpenC2 `store` action).
1. When the attributes have been stored in the Posture Attribute
   Repository, the PCS will publish a final notification message to `oc2/ntf` indicating completion.
1.  The Manager/Ochestator detects the final notification message and records that the _ad hoc_ posture attribute collection activity has concluded.
2.  The PES detects the final notification message and treats it as a "virtual command", performs a posture evaluation against the newly-collected attributes, and persists the results to an Evaluation Results Repository.