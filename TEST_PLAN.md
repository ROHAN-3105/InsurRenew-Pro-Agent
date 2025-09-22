# Test Plan for Edge Cases

[cite_start]This test plan outlines the expected agent behavior for various edge cases as specified in the hackathon document[cite: 81, 82].

| Scenario / Edge Case | Expected Agent Behavior | Acceptance Check |
| :--- | :--- | :--- |
| [cite_start]**angry_customer** [cite: 92] | Agent detects negative sentiment, apologizes, de-escalates, and executes the `EscalateToHuman` action to notify support via Slack. | Agent provides a polite handoff message and a notification appears in Slack. |
| [cite_start]**silent_line_or_dead_air** [cite: 93] | The agent will reprompt twice after 10 seconds of silence. If there is still no reply, it will offer to send an SMS link or schedule a callback. | The agent follows the reprompt and offer flow correctly. |
| [cite_start]**wrong_language** [cite: 95] | If the customer speaks Hindi, the agent's System Prompt instructs it to seamlessly switch its responses to Hindi to continue the conversation. | Agent correctly detects and switches language. |
| [cite_start]**policy_already_expired** [cite: 88] | The agent will check the `expiry_date`. If it is in the past, it will explain the options for policy reinstatement or purchasing a new policy instead of offering renewal. | Agent provides the correct alternative options. |
| [cite_start]**payment_gateway_timeout** [cite: 96] | If the `GenerateAndSendPaymentLink` action fails, the agent will reassure the customer, retry once, and if it fails again, will share the link via a separate SMS. | The agent handles the failure gracefully without ending the conversation. |
| [cite_start]**upsell_policy_not_eligible** [cite: 97] | If the `eligible_upsell` variable is empty, the agent's System Prompt rule prevents it from making any upsell offer. | The agent concludes the conversation after payment confirmation without attempting an upsell. |