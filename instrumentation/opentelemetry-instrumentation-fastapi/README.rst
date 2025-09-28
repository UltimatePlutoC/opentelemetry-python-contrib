OpenTelemetry FastAPI Instrumentation
=======================================

|pypi|

.. |pypi| image:: https://badge.fury.io/py/opentelemetry-instrumentation-fastapi.svg
   :target: https://pypi.org/project/opentelemetry-instrumentation-fastapi/


This library provides automatic and manual instrumentation of FastAPI web frameworks,
instrumenting http requests served by applications utilizing the framework.

auto-instrumentation using the opentelemetry-instrumentation package is also supported.

Installation
------------

::

    pip install opentelemetry-instrumentation-fastapi

References

* `OpenTelemetry Project <https://opentelemetry.io/>`_
* `OpenTelemetry Python Examples <https://github.com/open-telemetry/opentelemetry-python/tree/main/docs/examples>`_
 
 Configuration & Usage Notes
 --------------------------
 
 **Environment Variables**
 
 OpenTelemetry Python supports standard environment variables for configuration, including:
 
 - ``OTEL_EXPORTER_OTLP_ENDPOINT``
 - ``OTEL_EXPORTER_OTLP_PROTOCOL``
 - ``OTEL_SERVICE_NAME``
 - ``OTEL_TRACES_EXPORTER``, ``OTEL_METRICS_EXPORTER``
 
 These can be set to configure exporters, service name, and other options. See the `OpenTelemetry Python documentation <https://opentelemetry-python.readthedocs.io/en/latest/getting-started.html#environment-variables>`_ for a full list.
 
 **Trace Propagation**
 
 Trace context propagation works automatically for HTTP requests. The instrumentation uses W3C Trace Context and Baggage headers for distributed tracing. No manual intervention is required for standard HTTP requests.
 
 **WebSocket Support**
 
 Automatic trace propagation for WebSocket connections is limited. You may need to manually create and propagate spans for WebSocket handlers in FastAPI applications.
 
 **Logging Integration**
 
 To integrate logs as events in traces, use the ``opentelemetry-instrumentation-logging`` package and configure your logger with OpenTelemetry's logging handler. This allows logs to be attached to traces as events. See the `OpenTelemetry Python logging documentation <https://opentelemetry-python.readthedocs.io/en/latest/instrumentation/logging/logging.html>`_.
 
 **Related Packages**
 
 - `opentelemetry-instrumentation <https://pypi.org/project/opentelemetry-instrumentation/>`_
 - `opentelemetry-instrumentation-fastapi <https://pypi.org/project/opentelemetry-instrumentation-fastapi/>`_
