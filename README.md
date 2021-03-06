# Matlab Docker


Full Matlab with GUI and a minimal Matlab. 

Adheres to Mathworks' licensing. 

Must supply valid Mathworks License to start containers.

Prebuilt containers available [here](https://hub.docker.com/r/raphaelguzman/matlab).

See `docker-compose.yml` for instructions on how to properly start it with `docker-compose up`.


## Env Vars for Starting

* MATLAB_LICENSE="#\ BEGIN---........---END" `Converted Mathworks license to string. To convert use: echo \"$(sed ':a;N;$!ba;s|\t|\\t|g' license.lic | sed 's| |\\ |g' | sed 's|"|\\"|g' | sed ':a;N;$!ba;s|\n|\\n|g')\"`

* MATLAB_HOSTID=xx:xx:xx:xx:xx:xx `MAC Address supplied to Mathworks as HostID associated with license`

* MATLAB_USER=muser               `System/ComputerLogin user associated with license. Default is muser`

* MATLAB_UID=1000                 `Any UID of your docker host`

* MATLAB_GID=1000                 `Any GID of your docker host`


## Env Vars for Building

* MATLAB_VERSION=R2018b           `Matlab Version to be build. Must supply COMPLETE matlab_RXXXXX_glnxa64.zip for install in an installers dir.`

* MATLAB_FILE_KEY=xxxxx-xxxxx-xxxxx-xxxxx `Mathworks provided file key along with Mathworks license.` 

* PY_VERSION=3.6                  `>= 3.0. Necessary to complete install of Jupyter Notebook with MATLAB kernel (GUI).`

* MATLAB_INSTALLED_ROOT=/home/muser/.MATLAB `Directory where MATLAB root path is located.`


## Travis CI Integration

For a reference of how this container may be used in Continuous Integration with Travis, see my repo for [compareVersions.m](https://github.com/guzman-raphael/compareVersions).