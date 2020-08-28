# swagger-client
Functionality to create and manage Lab projects, services, datasets, models, and experiments.

This Python package is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: 3.0.0
- Package version: 1.0.0
- Build package: io.swagger.codegen.languages.PythonClientCodegen

## Requirements.

Python 2.7 and 3.4+

## Installation & Usage
### pip install

If the python package is hosted on Github, you can install directly from Github

```sh
pip install git+https://github.com//.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com//.git`)

Then import the package:
```python
import lab_api.swagger_client 
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import lab_api.swagger_client
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python
from __future__ import print_function
import time
import lab_api.swagger_client
from lab_api.swagger_client.rest import ApiException
from pprint import pprint

# create an instance of the API class
api_instance = lab_api.swagger_client.AdministrationApi(lab_api.swagger_client.ApiClient(configuration))
id = 'id_example' # str |  (optional)
authorization = 'authorization_example' # str | Authorization Token (optional)

try:
    # Checks whether a workspace container for the passed id already exists. If not, a new one is created & started.
    api_response = api_instance.check_workspace(id=id, authorization=authorization)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling AdministrationApi->check_workspace: %s\n" % e)

```

## Documentation for API Endpoints

All URIs are relative to *https://localhost*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AdministrationApi* | [**check_workspace**](docs/AdministrationApi.md#check_workspace) | **GET** /api/admin/workspace/check | Checks whether a workspace container for the passed id already exists. If not, a new one is created &amp; started.
*AdministrationApi* | [**get_events**](docs/AdministrationApi.md#get_events) | **GET** /api/admin/events | Returns events filtered by a specified event type (admin-only).
*AdministrationApi* | [**get_lab_info**](docs/AdministrationApi.md#get_lab_info) | **GET** /api/admin/info | Returns information about this Lab instance.
*AdministrationApi* | [**get_statistics**](docs/AdministrationApi.md#get_statistics) | **GET** /api/admin/statistics | Returns statistics about this Lab instance (admin-only).
*AdministrationApi* | [**reset_all_workspaces**](docs/AdministrationApi.md#reset_all_workspaces) | **PUT** /api/admin/workspace/reset-all | Resets all workspaces. Use with caution (admin-only).
*AdministrationApi* | [**reset_workspace**](docs/AdministrationApi.md#reset_workspace) | **GET** /api/admin/workspace/reset | Resets a workspace. Removes the container (keeps all persisted data) and starts a new one.
*AdministrationApi* | [**shutdown_disk_exceeding_containers**](docs/AdministrationApi.md#shutdown_disk_exceeding_containers) | **PUT** /api/admin/workspace/shutdown-disk-exceeding | Remove all workspaces that exceed the disk storage limit (docker-local mode only).
*AdministrationApi* | [**shutdown_unused_workspaces**](docs/AdministrationApi.md#shutdown_unused_workspaces) | **PUT** /api/admin/workspace/shutdown-unused | Shutdown all unused workspaces - 15 days without activity (admin-only).
*AuthorizationApi* | [**add_user_to_project**](docs/AuthorizationApi.md#add_user_to_project) | **GET** /api/auth/users/{user}/projects/{project} | Add a user to a project. Return new token.
*AuthorizationApi* | [**create_api_token**](docs/AuthorizationApi.md#create_api_token) | **GET** /api/auth/users/{user}/token | Get a long-term API token for given user.
*AuthorizationApi* | [**create_user**](docs/AuthorizationApi.md#create_user) | **POST** /api/auth/users | Create user profile.
*AuthorizationApi* | [**deactivate_users**](docs/AuthorizationApi.md#deactivate_users) | **POST** /api/auth/users/deactivate | Deactivate a list of users. This will overwrite all deactivated users (admin only).
*AuthorizationApi* | [**delete_user**](docs/AuthorizationApi.md#delete_user) | **DELETE** /api/auth/users/{user} | Delete a user (admin only).
*AuthorizationApi* | [**get_me**](docs/AuthorizationApi.md#get_me) | **GET** /api/auth/users/me | Get the user profile of the current user.
*AuthorizationApi* | [**get_user**](docs/AuthorizationApi.md#get_user) | **GET** /api/auth/users/{user} | Get the profile a user has access to.
*AuthorizationApi* | [**get_users**](docs/AuthorizationApi.md#get_users) | **GET** /api/auth/users | Get all profiles stored in the database (admin only).
*AuthorizationApi* | [**login_user**](docs/AuthorizationApi.md#login_user) | **GET** /api/auth/login | Login with basic auth and get short-term application token (JWT).
*AuthorizationApi* | [**logout_user**](docs/AuthorizationApi.md#logout_user) | **GET** /api/auth/logout | Log the user out by setting the auth cookie to a time in the past
*AuthorizationApi* | [**refresh_token**](docs/AuthorizationApi.md#refresh_token) | **GET** /api/auth/refresh | Get a new short-term application token (JWT).
*AuthorizationApi* | [**remove_user_from_project**](docs/AuthorizationApi.md#remove_user_from_project) | **DELETE** /api/auth/users/{user}/projects/{project} | Remove a user from a project. Return new token.
*AuthorizationApi* | [**update_permissions**](docs/AuthorizationApi.md#update_permissions) | **POST** /api/auth/users/{user}/permissions | Update permissions of a user (admin only). Return new token.
*AuthorizationApi* | [**update_user_password**](docs/AuthorizationApi.md#update_user_password) | **GET** /api/auth/users/{user}/password | Update user password. Return new token.
*ProjectsApi* | [**create_project**](docs/ProjectsApi.md#create_project) | **POST** /api/projects | Create a new project.
*ProjectsApi* | [**create_project_token**](docs/ProjectsApi.md#create_project_token) | **GET** /api/projects/{project}/token | Get project token for the specified project.
*ProjectsApi* | [**delete_experiment**](docs/ProjectsApi.md#delete_experiment) | **DELETE** /api/projects/{project}/experiments | Deletes an experiment from a specified project.
*ProjectsApi* | [**delete_file**](docs/ProjectsApi.md#delete_file) | **DELETE** /api/projects/{project}/files | Deletes a file from a specified project.
*ProjectsApi* | [**delete_job**](docs/ProjectsApi.md#delete_job) | **DELETE** /api/projects/{project}/jobs/{job} | Deletes a job from a project.
*ProjectsApi* | [**delete_project**](docs/ProjectsApi.md#delete_project) | **DELETE** /api/projects/{project} | Delete a project and all its associated networks, services &amp; data.
*ProjectsApi* | [**delete_scheduled_job**](docs/ProjectsApi.md#delete_scheduled_job) | **DELETE** /api/projects/{project}/jobs/scheduled/{job} | Remove a scheduled job.
*ProjectsApi* | [**delete_service**](docs/ProjectsApi.md#delete_service) | **DELETE** /api/projects/{project}/services/{service} | Delete a specific project service by name or type.
*ProjectsApi* | [**deploy_job**](docs/ProjectsApi.md#deploy_job) | **POST** /api/projects/{project}/jobs | Deploy a job for a specified project based on a provided image.
*ProjectsApi* | [**deploy_model**](docs/ProjectsApi.md#deploy_model) | **POST** /api/projects/{project}/files/models/deploy | Deploy a model as a service for a specified project.
*ProjectsApi* | [**deploy_service**](docs/ProjectsApi.md#deploy_service) | **POST** /api/projects/{project}/services | Deploy a service for a specified project based on a provided image.
*ProjectsApi* | [**download_file**](docs/ProjectsApi.md#download_file) | **GET** /api/projects/{project}/files/download | Download file from remote storage of selected project.
*ProjectsApi* | [**get_experiments**](docs/ProjectsApi.md#get_experiments) | **GET** /api/projects/{project}/experiments | Get all experiments of a project with details.
*ProjectsApi* | [**get_file_info**](docs/ProjectsApi.md#get_file_info) | **GET** /api/projects/{project}/files/info | Get info about the specified file.
*ProjectsApi* | [**get_files**](docs/ProjectsApi.md#get_files) | **GET** /api/projects/{project}/files | Get all files of a project with details and general statistics filtered by data type and/or prefix.
*ProjectsApi* | [**get_job**](docs/ProjectsApi.md#get_job) | **GET** /api/projects/{project}/jobs/{job} | Get a specific project job by name or type.
*ProjectsApi* | [**get_job_logs**](docs/ProjectsApi.md#get_job_logs) | **GET** /api/projects/{project}/jobs/{job}/logs | Get the logs for a job.
*ProjectsApi* | [**get_jobs**](docs/ProjectsApi.md#get_jobs) | **GET** /api/projects/{project}/jobs | Get all jobs of a project with details and general statistics.
*ProjectsApi* | [**get_project**](docs/ProjectsApi.md#get_project) | **GET** /api/projects/{project} | Get details for the specified project.
*ProjectsApi* | [**get_projects**](docs/ProjectsApi.md#get_projects) | **GET** /api/projects | Get all available projects with details.
*ProjectsApi* | [**get_scheduled_jobs**](docs/ProjectsApi.md#get_scheduled_jobs) | **GET** /api/projects/{project}/jobs/scheduled | Get all scheduled jobs of a project.
*ProjectsApi* | [**get_service**](docs/ProjectsApi.md#get_service) | **GET** /api/projects/{project}/services/{service} | Get a specific project service by name or type.
*ProjectsApi* | [**get_service_logs**](docs/ProjectsApi.md#get_service_logs) | **GET** /api/projects/{project}/services/{service}/logs | Get the logs for a service.
*ProjectsApi* | [**get_services**](docs/ProjectsApi.md#get_services) | **GET** /api/projects/{project}/services | Get all services of a project with details and general statistics.
*ProjectsApi* | [**is_project_available**](docs/ProjectsApi.md#is_project_available) | **GET** /api/projects/{project}/available | Checks if a project name is available for project creation .
*ProjectsApi* | [**sync_experiment**](docs/ProjectsApi.md#sync_experiment) | **POST** /api/projects/{project}/experiments | Sync an experiment to the experiments DB of a project.
*ProjectsApi* | [**upload_file**](docs/ProjectsApi.md#upload_file) | **POST** /api/projects/{project}/files/upload | Upload file to remote storage of selected project and returns key.


## Documentation For Models

 - [ExperimentResources](docs/ExperimentResources.md)
 - [GitInfo](docs/GitInfo.md)
 - [HostInfo](docs/HostInfo.md)
 - [LabEvent](docs/LabEvent.md)
 - [LabExperiment](docs/LabExperiment.md)
 - [LabFile](docs/LabFile.md)
 - [LabFileCollection](docs/LabFileCollection.md)
 - [LabFileResponse](docs/LabFileResponse.md)
 - [LabInfo](docs/LabInfo.md)
 - [LabInfoResponse](docs/LabInfoResponse.md)
 - [LabJob](docs/LabJob.md)
 - [LabJobResponse](docs/LabJobResponse.md)
 - [LabProject](docs/LabProject.md)
 - [LabProjectConfig](docs/LabProjectConfig.md)
 - [LabProjectResponse](docs/LabProjectResponse.md)
 - [LabProjectsStatistics](docs/LabProjectsStatistics.md)
 - [LabScheduledJob](docs/LabScheduledJob.md)
 - [LabService](docs/LabService.md)
 - [LabServiceResponse](docs/LabServiceResponse.md)
 - [LabStatisticsResponse](docs/LabStatisticsResponse.md)
 - [LabUser](docs/LabUser.md)
 - [LabUserResponse](docs/LabUserResponse.md)
 - [ListOfLabEventsResponse](docs/ListOfLabEventsResponse.md)
 - [ListOfLabExperimentsResponse](docs/ListOfLabExperimentsResponse.md)
 - [ListOfLabFilesResponse](docs/ListOfLabFilesResponse.md)
 - [ListOfLabJobsResponse](docs/ListOfLabJobsResponse.md)
 - [ListOfLabProjectsResponse](docs/ListOfLabProjectsResponse.md)
 - [ListOfLabScheduledJobsResponse](docs/ListOfLabScheduledJobsResponse.md)
 - [ListOfLabServicesResponse](docs/ListOfLabServicesResponse.md)
 - [ListOfLabUsers](docs/ListOfLabUsers.md)
 - [ListOfLabUsersResponse](docs/ListOfLabUsersResponse.md)
 - [ListOfStringsResponse](docs/ListOfStringsResponse.md)
 - [StatusMessageFormat](docs/StatusMessageFormat.md)
 - [StringResponse](docs/StringResponse.md)
 - [UnifiedErrorMessage](docs/UnifiedErrorMessage.md)
 - [UnifiedFormatMetadata](docs/UnifiedFormatMetadata.md)
 - [ValueListFormatMetadata](docs/ValueListFormatMetadata.md)


## Documentation For Authorization

 All endpoints do not require authorization.


## Author


