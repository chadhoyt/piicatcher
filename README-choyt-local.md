# Local Setup Steps

## PII Catcher Setup (Docker version)

References: <https://github.com/tokern/piicatcher> & <https://tokern.io/docs/piicatcher/installation>

    git clone https://github.com/tokern/piicatcher.git
    cd piicatcher
    alias piicatcher='docker run -v ${HOME}/.config/tokern:/config -u $(id -u ${USER}):$(id -g ${USER}) -it --add-host=host.docker.internal:host-gateway tokern/piicatcher:latest'

## Scan Usage Examples

Run these against nonprod sources that are current, like EDW-Stage and sunup-prod-performance.  Use "piicatcher --help" for instruction (docs and repo readme seem either newer or outdated for docker image).

piicatcher db --connection-type postgres --user $PIICATCHER_DB_USER=chad --password $PIICATCHER_DB_PWD --host $PIICATCHER_EDW_HOST --port 5432 --database enterprise_dw --scan-type shallow --exclude-schema public > edw-pii-results-shallow.txt
piicatcher db --connection-type postgres --user $PIICATCHER_DB_USER=chad --password $PIICATCHER_DB_PWD --host $PIICATCHER_BSF_HOST --port 5432 --database bsf --scan-type shallow --exclude-schema public > bsf-pii-results-shallow.txt
