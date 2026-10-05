# Workflow
An active member reserves an available tool, creating a confirmed reservation. The member may cancel their own confirmed reservation. Staff may check it out only for an active member before its pickup deadline, creating a loan due exactly 168 elapsed hours after checkout commit.

At the pickup deadline, a confirmed reservation expires. Canceled and expired reservations release the tool; checkout converts its hold into a loan. Staff record returns, closing the loan and making the tool available.

Staff may suspend or reinstate a member at any time. Reinstatement restores permission to reserve and check out.

Unauthorized or invalid actions, including unavailable-tool reservations, duplicate checkouts/returns, and attempts to mutate terminal reservations, change nothing and show a reason. Failed writes roll back and show a retry message.
