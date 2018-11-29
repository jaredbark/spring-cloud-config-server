Spring Cloud Config Server
===============================

Run RabbitMQ on Docker

    docker run -it -d -p 5672:5672 -p 15672:15672 -e RABBITMQ_DEFAULT_USER=test -e RABBITMQ_DEFAULT_PASS=test rabbitmq:3.7.2-management-alpine


Bug on Spring Cloud Bus

    Env:
        spring-boot-starter-parent/2.1.0.RELEASE
        spring-cloud version/Greenwich.M1

    Error details:
        Dispatcher has no subscribers for channel 'application-1.springCloudBusOutput' error occurred when /bus/refresh called.

    Error log:
        ERROR 236840 --- [nio-8881-exec-1] o.a.c.c.C.[.[.[/].[dispatcherServlet]    : Servlet.service() for servlet [dispatcherServlet] in context with path [] threw exception [Request processing failed; nested exception is org.springframework.messaging.MessageDeliveryException: Dispatcher has no subscribers for channel 'config-client-1.springCloudBusOutput'.; nested exception is org.springframework.integration.MessageDispatchingException: Dispatcher has no subscribers, failedMessage=GenericMessage [payload=byte[206], headers={contentType=application/json, id=a10ff724-76ca-b29a-9a7f-7c717ed66252, timestamp=1542077508374}], failedMessage=GenericMessage [payload=byte[206], headers={contentType=application/json, id=a10ff724-76ca-b29a-9a7f-7c717ed66252, timestamp=1542077508374}]] with root cause
        
    Bug report URL: https://github.com/spring-cloud/spring-cloud-bus/issues/137
    
    Solution:
        Changed the version of spring-boot-starter-parent(1.5.14.RELEASE) and spring-could(Edgware.SR3)