# ------------------------------------------------------------------------
#
# Copyright 2020 WSO2, Inc. (http://wso2.com)
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License
#
# ------------------------------------------------------------------------

# set base Docker image to WSO2 API Manager Docker image with latest WSO2 Updates
FROM wso2/wso2am:4.0.0
LABEL maintainer="WSO2 Docker Maintainers <dev@wso2.org>"

# build arguments for external artifacts
ARG MYSQL_CONNECTOR_VERSION=8.0.17

# add MySQL JDBC connector to server home as a third party library
ADD --chown=wso2carbon:wso2 ./lib/postgresql-42.2.19.jar ${WSO2_SERVER_HOME}/repository/components/dropins/
ADD --chown=wso2carbon:wso2 ./lib/event-publisher-1.0-SNAPSHOT.jar ${WSO2_SERVER_HOME}/repository/components/lib/
COPY client-truststore.jks  /home/wso2carbon/wso2am-4.0.0/repository/resources/security/
COPY wso2carbon.jks  /home/wso2carbon/wso2am-4.0.0/repository/resources/security/