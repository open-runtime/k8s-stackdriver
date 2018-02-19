# Copyright 2017 Google Inc.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

# The build rule builds a Docker image that logs all Docker contains logs to
# Google Compute Platform using the Cloud Logging API.

# Procedure for change:
# 1. Bump the tag number.
# 2. Push to the private repo and test using newer version
# 3. Issue PR.
# 4. Assuming permissions to do so, when PR is approved
#    make the gcr.io version of the image: make build push
# 5. Issue PR with config files changes

.PHONY:	build push

PREFIX=gcr.io/google-containers
TAG = 0.1

build:
	docker build --pull -t $(PREFIX)/fluentd-gcp-scaler:$(TAG) .


push:
	gcloud docker -- push $(PREFIX)/fluentd-gcp-scaler:$(TAG)