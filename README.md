<b> Azure Portal Template for Tailscale </b>

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Ftailscale-acknowledge%2Ftailscale-arm-template%2Fmaster%2Fmain.json/createUIDefinitionUri/https%3A%2F%2Fraw.githubusercontent.com%2Ftailscale-acknowledge%2Ftailscale-arm-template%2Fmaster%2FcreateUiDefinition.json)

These templates will deploy a single tailscale linux server to Azure using the Azure Portal. The template allows deployment to a new Resource Group or existing Resource Group. Please use a decimal to hex converter to convert Site ID (customer number). This needs to be inserted into the requested `tailscale Site ID` option. Hereby there will be created an IPv4-over-IPv6 NAT for 0.0.0.0/0.

<b>For example</b>

<table>
  <tr>
    <th>Site ID (DECIMAL)</th>
    <th>Site ID (HEX)</th>
    <th>Customer IPv6 subnet</th>
  </tr>
  <tr>
    <td>16</td>
    <td>0010</td>
    <td>fd7a:115c:a1e0:b1a:0:<b>0010</b>::/96</td>
  </tr>
  <tr>
    <td>201</td>
    <td>00C9</td>
    <td>fd7a:115c:a1e0:b1a:0:<b>00C9</b>::/96</td>
  </tr>
</table>

This would result in the following NAT;

<table>
  <tr>
    <th>Original IPv4</th>
    <th>Customer IPv6 subnet</th>
    <th>NATTED IPv6</th>
    <th>IPv6</th>
  </tr>
  <tr>
    <td>172.18.14.13/32</td>
    <td>fd7a:115c:a1e0:b1a:0:<b>0010</b>::/96</td>
    <td><b>[</b>fd7a:115c:a1e0:b1a:0:0010:172.18.14.13<b>]</b></td>
    <td>fd7a:115c:a1e0:b1a:0:0010:ac12:0e0d/128</td>
  </tr>
  <tr>
    <td>10.20.41.0/24</td>
    <td>fd7a:115c:a1e0:b1a:0:<b>00C9</b>::/96</td>
    <td>fd7a:115c:a1e0:b1a:0:00C9:10.20.41.0/120</td>
    <td>fd7a:115c:a1e0:b1a:0:00C9:0a14:2900/120</td>
  </tr>
</table>
