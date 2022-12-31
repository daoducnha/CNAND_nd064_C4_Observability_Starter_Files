**Note:** For the screenshots, you can store all of your answer images in the `answer-img` directory.

## Verify the monitoring installation

*TODO:* run `kubectl` command to show the running pods and services for all components. Take a screenshot of the output and include it here to verify the installation
![Alt text](https://github.com/daoducnha/CNAND_nd064_C4_Observability_Starter_Files/blob/master/screen_shot/all-pods.png?raw=true "kubectl get pod")
![Alt text](https://github.com/daoducnha/CNAND_nd064_C4_Observability_Starter_Files/blob/master/screen_shot/all-services.png?raw=true "kubectl get services")

## Setup the Jaeger and Prometheus source
*TODO:* Expose Grafana to the internet and then setup Prometheus as a data source. Provide a screenshot of the home page after logging into Grafana.
![Alt text](https://github.com/daoducnha/CNAND_nd064_C4_Observability_Starter_Files/blob/master/screen_shot/dashboard1.png?raw=true "dashboard")
![Alt text](https://github.com/daoducnha/CNAND_nd064_C4_Observability_Starter_Files/blob/master/screen_shot/dashboard2.png?raw=true "data source")

## Create a Basic Dashboard
*TODO:* Create a dashboard in Grafana that shows Prometheus as a source. Take a screenshot and include it here.
![Alt text](https://github.com/daoducnha/CNAND_nd064_C4_Observability_Starter_Files/blob/master/screen_shot/dashboard3.png?raw=true "dashboard Prometheus")

## Describe SLO/SLI
*TODO:* Describe, in your own words, what the SLIs are, based on an SLO of *monthly uptime* and *request response time*.
- Service-Level Objective (SLO): is a measurable goal set by the SRE team to ensure a standard level of performance during a specified period of time.
- Service-Level Indicator (SLI): is a specific metric used to measure the performance of a service.
- So based on an SLI of *monthly uptime* and *request response time* we can determine SLO measurable goal of application to ensure performance 
- Example: assumption SLO: 99.5% monthly uptime and request response time should less than 1 second so with avg of SLI indicate the level of performance your service actually, and show you whether you achieved your SLO

## Creating SLI metrics.
*TODO:* It is important to know why we want to measure certain metrics for our customer. Describe in detail 5 metrics to measure these SLIs. 
SLI mestris:
    - Service uptime
    - Latency
    - Failure Rate
    - CPU Usage
    - Memory Usage

## Create a Dashboard to measure our SLIs
*TODO:* Create a dashboard to measure the uptime of the frontend and backend services We will also want to measure to measure 40x and 50x errors. Create a dashboard that show these values over a 24 hour period and take a screenshot.
![Alt text](https://github.com/daoducnha/CNAND_nd064_C4_Observability_Starter_Files/blob/master/screen_shot/dashboard1.png?raw=true "up_time")
![Alt text](https://github.com/daoducnha/CNAND_nd064_C4_Observability_Starter_Files/blob/master/screen_shot/dashboard1.png?raw=true "error")
## Tracing our Flask App
*TODO:*  We will create a Jaeger span to measure the processes on the backend. Once you fill in the span, provide a screenshot of it here. Also provide a (screenshot) sample Python file containing a trace and span code used to perform Jaeger traces on the backend service.

## Jaeger in Dashboards
*TODO:* Now that the trace is running, let's add the metric to our current Grafana dashboard. Once this is completed, provide a screenshot of it here.

## Report Error
*TODO:* Using the template below, write a trouble ticket for the developers, to explain the errors that you are seeing (400, 500, latency) and to let them know the file that is causing the issue also include a screenshot of the tracer span to demonstrate how we can user a tracer to locate errors easily.

TROUBLE TICKET

Name:

Date:

Subject:

Affected Area:

Severity:

Description:


## Creating SLIs and SLOs
*TODO:* We want to create an SLO guaranteeing that our application has a 99.95% uptime per month. Name four SLIs that you would use to measure the success of this SLO.
SLOs:
 - Application uptime is 99.95% uptime per month
 - < 99% request succes 
 - Response latance should be less than 0.1s
 - Server resource should not more than 70% utillization permonth
## Building KPIs for our plan
*TODO*: Now that we have our SLIs and SLOs, create a list of 2-3 KPIs to accurately measure these metrics as well as a description of why those KPIs were chosen. We will make a dashboard for this, but first write them down here.

## Final Dashboard
*TODO*: Create a Dashboard containing graphs that capture all the metrics of your KPIs and adequately representing your SLIs and SLOs. Include a screenshot of the dashboard here, and write a text description of what graphs are represented in the dashboard.  
