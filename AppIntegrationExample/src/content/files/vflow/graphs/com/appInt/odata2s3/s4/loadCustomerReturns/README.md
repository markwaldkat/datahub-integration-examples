# S4 CustRet. to S3

## Description

This graph extracts S/4 customer returns data and stores then in CSV format into Amazon S3. 

The graph is composed of the following components:
- OData Query Consumer: Reads customer returns data from the Odata endpoint exposed by S/4HANA.
- Flowagent File Producer: Writes the data in CSV format into Amazon S3.
- 3-1 Multiplexer & Terminal: Shows results of the data ingestion.

## Prerequisites

- For this graph to run you will need the following:
    - Configured connection to the S/4 HANA customer returns OData endpoint with ID `APPINT_S4_CUSTRET`
    - Configured connection to Amazon S3 with ID `APPINT_S3`
        - Remark: you can also use corresponding object store solutions from Microsoft Azure or Google Cloud Platform.

## Configure and Run the Graph

1. Adapt the OData query in the OData Query Consumer as required. The default configuration looks like this:<br>
`A_CustomerReturn?$orderby=CreationDate`
2. Adapt the target location in S3 for the generated file. Default location is:
   `/sdl/landing_zone/appInt/s4/CustomerReturns.csv`
3. Save and run the graph. 
4. Use the Terminal operator to view the status of the Pipeline during execution. Press `Enter` on the Terminal console to complete the graph.

<br>
<div class="footer">
   &copy; 2019 SAP SE or an SAP affiliate company. All rights reserved.
</div>
