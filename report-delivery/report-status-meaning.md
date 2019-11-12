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
        <p></p>
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
      <td style="text-align:left">
        <p>Possible reasons can include:</p>
        <ul>
          <li>iFrame was reloaded</li>
          <li>&quot;Choose another bank&quot; button was clicked</li>
          <li>The customer closed the tab</li>
          <li>Internet connection was lost</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">bank_error</td>
      <td style="text-align:left">An error occurred during data collection process. Most common cause is
        bank&apos;s service unavailable</td>
    </tr>
  </tbody>
</table>