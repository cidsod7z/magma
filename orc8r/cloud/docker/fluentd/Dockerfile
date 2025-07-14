# Copyright 2023 The Magma Authors.

# This source code is licensed under the BSD-style license found in the
# LICENSE file in the root directory of this source tree.

# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

#FROM fluent/fluentd:v1.14.6-debian-1.0
#USER root
#RUN gem install excon:1.2.5 \ 
#    elasticsearch:7.13.0 \
#    fluent-plugin-elasticsearch:5.2.1 \
#    fluent-plugin-multi-format-parser:1.0.0 \
#    --no-document
#USER fluent


# Use the Fluentd base image
FROM fluent/fluentd:v1.14.6-debian-1.0

# Switch to root user to install required packages
USER root

# Install compatible multi_json gem for Ruby 2.7 and other gems
RUN gem install multi_json -v 1.15.0 \
    && gem install excon:1.2.5 \
    && gem install elasticsearch:7.13.0 \
    && gem install fluent-plugin-elasticsearch:5.2.1 \
    && gem install fluent-plugin-multi-format-parser:1.0.0 \
    --no-document

# Switch back to the fluent user (keeping the same user as you requested)
USER fluent
