# Onyx Mail

Onyx Mail is a modern email platform built with Next.js, designed to provide a seamless, secure, and efficient email experience.

Onyx Mail combines a clean and intuitive interface with custom-built mail infrastructure, giving users everything they need to send, receive, organize, and manage email from one platform.

Our long-term goal is to operate our own mail infrastructure through **OnyxEngine** and **Onyx MTA**, reducing our reliance on third-party email delivery services and giving Onyx Mail greater control over security, reliability, and message delivery.

## Features

- Real-time email updates
- Customizable themes
- Advanced search capabilities
- User-friendly interface
- Cross-platform support
- Secure and private email management
- Custom domain support
- Customizable email signatures
- Email filtering and organization
- Folder and label management
- Email scheduling
- Email templates
- Multi-language support
- Integration with popular email services such as Gmail, Outlook, and Yahoo — Coming Soon!

## Mail Infrastructure

Onyx Mail is building its own dedicated infrastructure for receiving, processing, and delivering email.

Our mail infrastructure is separated into two primary systems:

### OnyxEngine

**OnyxEngine** is the inbound mail engine powering Onyx Mail.

It is responsible for receiving and processing email delivered to Onyx Mail, including:

- SMTP reception
- STARTTLS encrypted connections
- MIME message parsing
- Mailbox ingestion
- Message processing
- Attachment processing
- Mail storage

Our production SMTP infrastructure currently supports trusted STARTTLS connections through `smtp.onyxmail.io`.

### Onyx MTA — Coming Soon

**Onyx MTA** is our custom outbound Mail Transfer Agent currently under development.

Rather than permanently relying on third-party SMTP infrastructure, Onyx MTA is being designed to allow Onyx Mail to deliver email directly to mail servers across the Internet.

Planned capabilities include:

- Direct SMTP delivery
- DNS and MX resolution
- STARTTLS encrypted delivery
- DKIM message signing
- Outbound delivery queues
- Automatic retries and delivery backoff
- MX failover
- Bounce and failure processing
- Delivery status tracking
- SMTP delivery logging
- Sender validation
- Rate limiting
- Abuse and spam prevention

The goal is to give Onyx Mail complete control over the lifecycle of an email:

```text
                         Onyx Mail
                             │
                ┌────────────┴────────────┐
                │                         │
                ▼                         ▼
           OnyxEngine                  Onyx MTA
             Inbound                   Outbound
                │                         │
                ▼                         ▼
       Internet → Onyx Mail       Onyx Mail → Internet
```

## Current Outbound Delivery

While Onyx MTA is under development and testing, Onyx Mail currently uses ByteSend for production outbound email delivery.

ByteSend provides the SMTP infrastructure used to securely relay outbound messages while our own direct-delivery infrastructure is being developed.

Once Onyx MTA has reached the required levels of reliability, security, abuse prevention, and deliverability, outbound mail will gradually transition to our own infrastructure.

## Development

Development of Onyx Mail, OnyxEngine, and Onyx MTA is ongoing.

We're continuously improving the user experience while expanding the infrastructure behind the platform.

Our goal is to make Onyx Mail increasingly self-sufficient, with our own systems responsible for both sides of email delivery:

**Receiving mail with OnyxEngine. Sending mail with Onyx MTA.**

Stay tuned for future updates and releases.
