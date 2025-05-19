# Message Delivery Service

## Overview
This BPMN process defines a Message Delivery Service that uses AI-powered task agents and various tools to handle customer requests and send messages through different channels.

![Process](./img/HawkHelperProcess.gif)

## Process Flow
1. The process starts with a user input.
2. A script task creates a prompt based on the input.
3. An AI Task Agent processes the prompt and determines the next steps.
4. Based on the AI agent's decision, the process either ends or continues to use various tools.

## Key Components

### AI Task Agent
- Utilizes Bedrock's Claude 3 Sonnet model for processing requests.
- Makes decisions on which tools to use based on the context.

### Niall's Tools
This is an ad-hoc subprocess containing various tools:

1. **Get Info**: A user task to gather information or documents.
2. **Send an Email**: Uses SendGrid to send emails.
3. **Send Slack Message**: Sends messages to specific Slack channels.

## Configuration

### AI Task Agent
- Provider: Bedrock
- Model: Claude 3 Sonnet
- Authentication: AWS credentials

### SendGrid Email
- Sender email: community@camunda.com
- Available channels: #good-news, #bad-news, #other-news

## Usage
1. Start the process with user input.
2. The AI agent will process the request and determine the appropriate action.
3. If tools are needed, they will be executed within the "Niall's Tools" subprocess.
4. The process ends when the request is fulfilled or no further action is required.

## Note
This process is designed to handle various customer requests and deliver messages through appropriate channels based on AI-driven decisions.