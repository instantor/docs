---
description: >-
  Each report will contain report status, which you will find under
  "processStatus".
---

# Report status definitions

<table>
  <thead>
    <tr>
      <th style="text-align:left">Status</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">ok</td>
      <td style="text-align:left">
        <p>Indicates that the process has finished successfully.
          <br />When list of accounts and transactions are empty there are 3 possible
          explanations:</p>
        <ul>
          <li>There are no transactions in requested date interval (3, 6, or 12 months).</li>
          <li>There are no current, or savings accounts linked to customer&apos;s online
            netbanking account.</li>
          <li>Accounts and transactions are omitted in product configuration.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">process_error</td>
      <td style="text-align:left">An error occurred during data collection process, or data processing.
        Most common cause is communication failure with a bank.</td>
    </tr>
    <tr>
      <td style="text-align:left">invalid_login</td>
      <td style="text-align:left">The system could not process the bank using the credentials provided by
        the customer.</td>
    </tr>
    <tr>
      <td style="text-align:left">abandoned</td>
      <td style="text-align:left">Widget was reloaded, or &quot;Choose another bank&quot; button was clicked.</td>
    </tr>
    <tr>
      <td style="text-align:left">blocked</td>
      <td style="text-align:left">Data collection process was blocked because there is a previous process
        which is still in progress.</td>
    </tr>
  </tbody>
</table>