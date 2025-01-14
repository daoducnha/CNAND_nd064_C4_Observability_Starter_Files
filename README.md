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
![Alt text](https://github.com/daoducnha/CNAND_nd064_C4_Observability_Starter_Files/blob/master/screen_shot/up_time.png?raw=true "up_time")
## Tracing our Flask App
*TODO:*  We will create a Jaeger span to measure the processes on the backend. Once you fill in the span, provide a screenshot of it here. Also provide a (screenshot) sample Python file containing a trace and span code used to perform Jaeger traces on the backend service.
![Alt text](https://github.com/daoducnha/CNAND_nd064_C4_Observability_Starter_Files/blob/master/screen_shot/code1.png?raw=true "code_1")
![Alt text](https://github.com/daoducnha/CNAND_nd064_C4_Observability_Starter_Files/blob/master/screen_shot/code2.png?raw=true "code_2")
## Jaeger in Dashboards
*TODO:* Now that the trace is running, let's add the metric to our current Grafana dashboard. Once this is completed, provide a screenshot of it here.
![Alt text](https://github.com/daoducnha/CNAND_nd064_C4_Observability_Starter_Files/blob/master/screen_shot/jaeger_1.png?raw=true "jaeger_1")

## Report Error
*TODO:* Using the template below, write a trouble ticket for the developers, to explain the errors that you are seeing (400, 500, latency) and to let them know the file that is causing the issue also include a screenshot of the tracer span to demonstrate how we can user a tracer to locate errors easily.

![Alt text](https://github.com/daoducnha/CNAND_nd064_C4_Observability_Starter_Files/blob/master/screen_shot/jaeger_2.png?raw=true "jaeger_2")
TROUBLE TICKET

Name: 500INTERNAL SERVER ERROR

Date: January 1 2023, 13:18:34.371

Subject: Occur internal server error with status code 500 at add_star endpoint

Affected Area:  File "/app/app.py", line 93, in add_star

Severity: Critical

Description: Cannot insert star because method "insert" not exist


## Creating SLIs and SLOs
*TODO:* We want to create an SLO guaranteeing that our application has a 99.95% uptime per month. Name four SLIs that you would use to measure the success of this SLO.
SLOs:
 - Application uptime is 99.95% uptime per month
 - Response latance should be less than 0.1s
 - Server resource should not more than 70% utillization permonth
 - More than 99% request succes 
## Building KPIs for our plan
*TODO*: Now that we have our SLIs and SLOs, create a list of 2-3 KPIs to accurately measure these metrics as well as a description of why those KPIs were chosen. We will make a dashboard for this, but first write them down here.
- Application uptime is 99.95% uptime per month
    - Ratio downtime/uptime total service < 0.05 %: it will provide total time up and down of sevices
    - Ratio downtime/uptime each service < 0.05 %: it will provide total time up and down of each sevice
- Response latance should be less than 0.1s:
    - Total response latance less than 0.1s: we can determine performance of application
    - Percen latency in each api less than 0.1s: We can determin wich end point has low/hight perfomance
- Server resource should not more than 70% utillization permonth:
    - CPU using each service < 70%: we can determine wich service need to optimie CPU usage
    - CPU total pod of service usage >70%: we can determine when need to add new replica for this service
- More than 99% request succes
    - More than 99% request in all sevice success: We can determine part occur error in this application and can optimize it
    - More than 99% request in each sevice success: We can determin wich service occour error and build plan to fix it
## Final Dashboard
*TODO*: Create a Dashboard containing graphs that capture all the metrics of your KPIs and adequately representing your SLIs and SLOs. Include a screenshot of the dashboard here, and write a text description of what graphs are represented in the dashboard.  
![Alt text](https://github.com/daoducnha/CNAND_nd064_C4_Observability_Starter_Files/blob/master/screen_shot/final_1.png?raw=true "final1")
![Alt text](https://github.com/daoducnha/CNAND_nd064_C4_Observability_Starter_Files/blob/master/screen_shot/final_2.png?raw=true "final2")

- Container CPU usage: CPU usage each pod
- Cluster Node CPU usage: CPU usage each cluster node
- Failure request: Count total requests have status code != 200
- Success request: Count total request have status code == 200
- Avg response time request: Calcuate avg latency of request
- Backend Uptime: time backend sevice running 
- Trial uptime: time trial service running
- Frontend uptime: time frontend service running
- All container Uptine: time all service in application running