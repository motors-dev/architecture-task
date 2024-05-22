# Email Transmission 📨

## Background:

We have a microservice that sends emails to customers. This microservice works fine for up to 10,000 emails but starts to fail and take too long beyond that. Our services are deployed in Google Cloud (GKE) with only one instance of each microservice.
Current Workflow:

- Receive REST Call: Accepts a list of customer IDs.
- Fetch Email Details: Calls another microservice over REST to fetch email details for each customer ID.
- Prepare Email: Prepares the email content for each customer.
- Send Email: Uses a REST call to the email transmission microservice to send each email.
- Record Sent Status: Logs that an email has been sent for each customer.
- Completion Log: Logs the total number of emails sent and the total processing time.

## Known Issues:

- Processing 10,000 emails takes 1 hour.
- Processing 100,000 emails is estimated to take 10 hours.
- Maximum volume before running out of memory (OOM) is around 125,000 emails.
- The business requirement is for faster email campaign delivery.
- Current logging only confirms the job is working when it completes.

## New Requirements:

- Marketing wants to increase the limit to 250,000 emails initially and up to 1 million soon after.
- Each customer should receive the email within 2 hours of starting the job.
- The system should handle unknown email addresses and failures gracefully without crashing.

## Task

Propose and discuss a revised architecture and implementation strategy to meet these new requirements. 

What risks are there to the current setup, and how would you mitigate them?

What architectural principles would you focus on in this solution?

## Expected Outcome:

- A revised architecture diagram.
- An explanation of how your proposed solution meets the new requirements.
- A discussion of the trade-offs and benefits of your approach.
- Any considerations for implementation and deployment in Google Cloud.

## Note:

Feel free to use any drawing tool you are comfortable with:

- [Draw.io](draw.io)
- [Miro.com](miro.com)
etc.
