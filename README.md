# on-dispatch-trigger-workflow 

This repository is an example of triggering a GitHub Actions workflow via the [repository dispatch event](https://developer.github.com/v3/repos/#creating-a-repository-dispatch-event). 

The repository dispatch event will trigger a new workflow execution that creates or updates your repo's `dates.txt` with a new date.

## Usage

* Fork the repo to your account
* Ensure `curl` is installed. (https://curl.haxx.se/)
* Then, Open the command line interface application of your choice and make this `curl` request, replacing `$TOKEN` with a [personal access token](https://help.github.com/en/articles/creating-a-personal-access-token-for-the-command-line) and `:owner` and `:repo` with the appropriate values


```shell
curl -v -H "Accept: application/vnd.github.everest-preview+json" \
  -H "Authorization: token $TOKEN" \
  https://api.github.com/repos/:owner/:repo/dispatches \
  -d '{"event_type":"update-dates-file"}'
```
