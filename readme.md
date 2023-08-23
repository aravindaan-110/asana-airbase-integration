# Asana and Airtable Integration

This project enables integration between Asana and Airtable using a webhook. It listens for new task additions in Asana, captures relevant task details, and adds them to an Airtable base.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Webhook Workflow](#webhook-workflow)
- [Endpoints](#endpoints)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

## Prerequisites

- Node.js and npm
- Asana account
- Airtable account
- [Asana Personal Access Token](https://developers.asana.com/docs/personal-access-token)
- [Airtable API Key](https://support.airtable.com/hc/en-us/articles/219046777-How-to-create-an-API-key)
- Webhook configuration in Asana (To send events to your server)
- Knowledge of setting up an Airtable base and table to store task details

## Installation

1. Clone this repository to your local machine.
2. Navigate to the project directory using the terminal.
3. Install the dependencies by running:

   ```bash
   npm install
   ```

## Configuration

1. Create a `.env` file in the root of the project.
2. Add your configuration variables to the `.env` file:

   ```env
   PORT=8080
   TOKEN=your-asana-personal-access-token
   BASEID=your-airtable-base-id
   TABLEID=your-airtable-table-id
   AIRTABLETOKEN=your-airtable-api-key
   ```

## Usage

1. Start the server:

   ```bash
   npm start
   ```

2. Your server should now be running at `http://localhost:3000`.

## Webhook Workflow

1. Create a webhook in Asana and configure it to send events to your server's `/receiveWebhook` endpoint.
2. When a new task is added in Asana, Asana will send an event to your server.
3. Your server will validate the event's signature, fetch task details, and add them to Airtable.

## Endpoints

- `/receiveWebhook`: Endpoint to receive events from the Asana webhook.

## Testing

You can test your server by visiting the root URL in your web browser:

- `http://localhost:PORT`