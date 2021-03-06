=========
CHANGELOG
=========

unreleased
==========
* feature: Added Sqlalchemy parameterized query capture. `PR34 <https://github.com/aws/aws-xray-sdk-python/pull/34>`_.

1.0
===
* Changed development status to `5 - Production/Stable` and removed beta tag.
* feature: Added S3 API parameters to the default whitelist.
* feature: Added new recorder APIs to add annotations/metadata.
* feature: The recorder now adds more runtime and version information to sampled segments.
* feature: Django, Flask and Aiohttp middleware now inject trace header to response headers.
* feature: Added a new API to configure maximum captured stack trace.
* feature: Modularized subsegments streaming logic and now it can be overriden with custom implementation.
* bugfix(**Breaking**): Subsegment `set_user` API is removed since this attribute is not supported by X-Ray back-end.
* bugfix: Fixed an issue where arbitrary fields in trace header being dropped when calling downstream.
* bugfix: Fixed a compatibility issue between botocore and httplib patcher. `ISSUE48 <https://github.com/aws/aws-xray-sdk-python/issues/48>`_.
* bugfix: Fixed a typo in sqlalchemy decorators. `PR50 <https://github.com/aws/aws-xray-sdk-python/pull/50>`_.
* Updated `README` with more usage examples. 

0.97
====
* feature: Support aiohttp client tracing for aiohttp 3.x. `PR42 <https://github.com/aws/aws-xray-sdk-python/pull/42>`_.
* feature: Use the official middleware pattern for Aiohttp ext. `PR29 <https://github.com/aws/aws-xray-sdk-python/pull/29>`_.
* bugfix: Aiohttp middleware serialized URL values incorrectly. `PR37 <https://github.com/aws/aws-xray-sdk-python/pull/37>`_
* bugfix: Don't overwrite plugins list on each `.configure` call. `PR38 <https://github.com/aws/aws-xray-sdk-python/pull/38>`_
* bugfix: Do not swallow `return_value` when context is missing and `LOG_ERROR` is set. `PR44 <https://github.com/aws/aws-xray-sdk-python/pull/44>`_
* bugfix: Loose entity name validation. `ISSUE36 <https://github.com/aws/aws-xray-sdk-python/issues/36>`_
* bugfix: Fix PyPI project page being rendered incorrectly. `ISSUE30 <https://github.com/aws/aws-xray-sdk-python/issues/30>`_

0.96
====
* feature: Add support for SQLAlchemy and Flask-SQLAlcemy. `PR14 <https://github.com/aws/aws-xray-sdk-python/pull/14>`_.
* feature: Add support for PynamoDB calls to DynamoDB. `PR13 <https://github.com/aws/aws-xray-sdk-python/pull/13>`_.
* feature: Add support for httplib calls. `PR19 <https://github.com/aws/aws-xray-sdk-python/pull/19>`_.
* feature: Make streaming threshold configurable through public interface. `ISSUE21 <https://github.com/aws/aws-xray-sdk-python/issues/21>`_.
* bugfix:  Drop invalid annotation keys and log a warning. `PR22 <https://github.com/aws/aws-xray-sdk-python/pull/22>`_.
* bugfix:  Respect `with` statement on cursor objects in dbapi2 patcher. `PR17 <https://github.com/aws/aws-xray-sdk-python/pull/17>`_.
* bugfix:  Don't throw error from built in subsegment capture when `LOG_ERROR` is set. `ISSUE4 <https://github.com/aws/aws-xray-sdk-python/issues/4>`_.

0.95
====
* **Breaking**: AWS API parameter whitelist json file is moved to path `aws_xray_sdk/ext/resources/aws_para_whitelist.json` in `PR6 <https://github.com/aws/aws-xray-sdk-python/pull/6>`_.
* Added aiobotocore/aioboto3 support and async function capture. `PR6 <https://github.com/aws/aws-xray-sdk-python/pull/6>`_
* Added logic to removing segment/subsegment name invalid characters. `PR9 <https://github.com/aws/aws-xray-sdk-python/pull/9>`_
* Temporarily disabled tests run on Django2.0. `PR10 <https://github.com/aws/aws-xray-sdk-python/pull/10>`_
* Code cleanup. `PR11 <https://github.com/aws/aws-xray-sdk-python/pull/11>`_

0.94
====
* Added aiohttp support. `PR3 <https://github.com/aws/aws-xray-sdk-python/pull/3>`_

0.93
====
* The X-Ray SDK for Python is now an open source project. You can follow the project and submit issues and pull requests on GitHub: https://github.com/aws/aws-xray-sdk-python

0.92.2
======
* bugfix: Fixed an issue that caused the X-Ray recorder to omit the origin when recording segments with a service plugin. This caused the service's type to not appear on the service map in the X-Ray console.

0.92.1
======
* bugfix: Fixed an issue that caused all calls to Amazon DynamoDB tables to be grouped under a single node in the service map. With this update, each table gets a separate node.

0.92
====

* feature: Add Flask support
* feature: Add dynamic naming on segment name

0.91.1
======

* bugfix: The SDK has been released as a universal wheel
