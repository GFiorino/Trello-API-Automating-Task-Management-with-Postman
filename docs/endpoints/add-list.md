<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Guide for adding lists using Trello API. Includes request details, required parameters, and troubleshooting tips.">
    <title>Trello API: Add List</title>
    <link rel="stylesheet" type="text/css" href="/Trello-API-Automating-Task-Management-with-Postman/Content/Resources/Stylesheets/Styles.css">
    <style>
      /* Highlight active navbar link */
      .navbar a.active {
        color: #ccc; /* Gray color for active link */
      }

      /* Clean code block styling */
      pre code {
        background-color: #f4f4f4;
        border: 1px solid #ddd;
        border-radius: 4px;
        padding: 10px;
        display: block;
        font-family: monospace;
        color: #333;
        overflow-x: auto;
      }

      /* Navigation Links Styling */
      .footer-nav {
        display: flex;
        justify-content: space-between;
        margin-top: 40px;
        font-size: 0.95rem;
      }

      .footer-nav a {
        color: #0056b3;
        font-weight: bold;
        text-decoration: none;
        padding: 10px 15px;
        border: 1px solid #ddd;
        border-radius: 5px;
        background-color: #f9f9f9;
        transition: all 0.3s ease;
      }

      .footer-nav a:hover {
        background-color: #0056b3;
        color: #fff;
      }

      /* Trello Logo Styling */
      .trello-logo {
        display: block;
        margin: 20px auto 40px;
        max-width: 150px;
        height: auto;
      }
    </style>
  </head>
  <body>
    <nav>
      <ul class="navbar">
        <li><a href="/Trello-API-Automating-Task-Management-with-Postman/index.htm">Home</a></li>
        <li><a href="/Trello-API-Automating-Task-Management-with-Postman/Content/Authentication/Setting%20Up%20API%20Authentication.htm">Authentication</a></li>
        <li>
          <a href="#" class="active">End-Points</a>
          <ul class="dropdown">
            <li><a href="/Trello-API-Automating-Task-Management-with-Postman/Content/Endpoints/Add%20Card.htm">Add Card</a></li>
            <li><a href="/Trello-API-Automating-Task-Management-with-Postman/Content/Endpoints/Add%20List.htm" class="active">Add List</a></li>
            <li><a href="/Trello-API-Automating-Task-Management-with-Postman/Content/Endpoints/Create%20Board.htm">Create Board</a></li>
          </ul>
        </li>
        <li>
          <a href="#">User-Cases</a>
          <ul class="dropdown">
            <li><a href="/Trello-API-Automating-Task-Management-with-Postman/Content/Real-World%20User%20Cases/Automating%20Task%20Creation.htm">Automating Task Creation</a></li>
            <li><a href="/Trello-API-Automating-Task-Management-with-Postman/Content/Real-World%20User%20Cases/Deleting%20a%20Card%20or%20List.htm">Deleting a Card or List</a></li>
            <li><a href="/Trello-API-Automating-Task-Management-with-Postman/Content/Real-World%20User%20Cases/Managing%20Cards%20and%20Lists.htm">Managing Cards and Lists</a></li>
          </ul>
        </li>
      </ul>
    </nav>

    <!-- Trello Logo -->
    <img src="/Trello-API-Automating-Task-Management-with-Postman/Content/Resources/Images/trello_Logo.png" alt="Trello Logo" class="trello-logo">

    <main>
      <h1 class="spaced-title">Trello API: Add List</h1>
      <p>The Add List endpoint allows you to create a new list on an existing board. You need to provide the board ID and the list name to use this endpoint.</p>

      <h2>Request Details</h2>
      <ul>
        <li><b>Method:</b> POST</li>
        <li><b>Endpoint URL:</b> <code>https://api.trello.com/1/lists</code></li>
        <li><b>Authentication:</b> Requires <code>key</code> and <code>token</code> as query parameters.</li>
      </ul>

      <h2>Required Parameters</h2>
      <table>
        <thead>
          <tr>
            <th>Parameter</th>
            <th>Type</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>name</td>
            <td>String</td>
            <td>The name of the list.</td>
          </tr>
          <tr>
            <td>idBoard</td>
            <td>String</td>
            <td>The ID of the board where the list will be created.</td>
          </tr>
        </tbody>
      </table>

      <h2>Example Request</h2>
      <pre><code>POST https://api.trello.com/1/lists
Content-Type: application/json

{
  "name": "New List Example",
  "idBoard": "12345abcdef",
  "pos": "top",
  "key": "your_api_key",
  "token": "your_access_token"
}</code></pre>

      <h2>Example Response</h2>
      <pre><code>{
  "id": "60d21b4967d0d810b8f8b456",
  "name": "New List Example",
  "idBoard": "12345abcdef",
  "pos": "top",
  "subscribed": false,
  "closed": false
}</code></pre>

      <h2>Common Errors</h2>
      <table>
        <thead>
          <tr>
            <th>Error</th>
            <th>Possible Cause</th>
            <th>Solution</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>401 Unauthorized</td>
            <td>Invalid API key or token.</td>
            <td>Verify your API key and token are correct.</td>
          </tr>
          <tr>
            <td>400 Bad Request</td>
            <td>Missing required parameters.</td>
            <td>Ensure <b>idBoard</b> and <b>name</b> are provided.</td>
          </tr>
          <tr>
            <td>404 Not Found</td>
            <td>Board ID does not exist or is invalid.</td>
            <td>Check the <b>idBoard</b> value.</td>
          </tr>
        </tbody>
      </table>

      <div class="footer-nav">
        <a href="/Trello-API-Automating-Task-Management-with-Postman/Content/Endpoints/Add%20Card.htm">Previous: Add Card</a>
        <a href="/Trello-API-Automating-Task-Management-with-Postman/Content/Endpoints/Create%20Board.htm">Next: Create Board</a>
      </div>
    </main>

    <!-- Updated Footer -->
    <footer class="site-footer" style="background-color: #f4f4f4; padding: 30px 20px; border-top: 2px solid #ddd; text-align: center; font-size: 0.95rem; color: #333;">
        <div style="margin-bottom: 20px;">
            <p style="margin: 5px 0; font-weight: bold;">Explore My Projects:</p>
            <a href="https://github.com/GFiorino" target="_blank" style="display: inline-block; margin: 5px 10px; padding: 10px 15px; color: #fff; background-color: #0056b3; text-decoration: none; border-radius: 5px; font-size: 0.9rem; font-weight: bold; transition: background-color 0.3s ease;">
                GitHub Portfolio
            </a>
            <a href="https://gfiorino.github.io/Technical-Writing-Portfolio/" target="_blank" style="display: inline-block; margin: 5px 10px; padding: 10px 15px; color: #fff; background-color: #28a745; text-decoration: none; border-radius: 5px; font-size: 0.9rem; font-weight: bold; transition: background-color 0.3s ease;">
                Live Portfolio
            </a>
        </div>
        <p style="margin: 5px 0;">&copy; 2024 Trello API: Automating Task Management with Postman. All rights reserved.</p>
    </footer>
  </body>
</html>
