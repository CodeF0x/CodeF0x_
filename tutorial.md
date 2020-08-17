This tutorial shows you how to setup this repository for yourself.

## Preparation

1. <a href="https://developer.spotify.com/dashboard/login">Create a application on Spotify</a> to use their API
2. Edit settings for your app on Spotify dev dashboard, specifically, add a dummy `redirect_uri`. For my integration I've used `http://localhost/`, but you can use any other uri as per your choice.
> Note: if you use a different uri, then please make sure you update the url in the code, too.
3. Take note of your newly registered apps `client id` and `client secret`
4. Generate an authentication code for your spotify account for using your newly created application by constructing this URL using your apps client id and your set redirect uri (make sure it's <a href="https://www.urlencoder.org/">url encoded</a>) as values for the respective query params:

`https://accounts.spotify.com/authorize?client_id=<YOUR-CLIENT-ID-HERE>&response_type=code&redirect_uri=http%3A%2F%2Flocalhost%2F&scope=user-top-read%20user-read-recently-played`

5. Copy the generated code after the `code` query from the resulting response url which should look like this: `http://localhost/?code=<COPY-EVERYTHING-HERE>`

> Note: if you used a different `redirect_uri`, the localhost part is replaced with the url you submitted

6. <a href="https://github.com/settings/tokens">Create a GitHub access token</a> with the `public_repo` scope and **save** it for later, as you can only view it after creation

## Projekt setup

1. Fork this repository (or download and re-upload it to match your account and repository)
2. Edit <a href="https://github.com/CodeF0x/CodeF0x/blob/1b14138dfb3c4d3afb2aa99bdb073c72da4ab7cc/.circleci/config.yml#L43">line 43</a> in the `.circleci/config.yml` file and adjust it to your own repository
> Important note: you can of course edit the commit message, but do **not** remove *[ci skip]*, otherwise you will cause an endless loop of ci jobs!
2. <a href="https://circleci.com/vcs-authorize/">Log into CircleCI with your GitHub account</a>
3. Click on "Add Projects" on the sidebar
4. Setup the project with the newly created fork (respectively the repository you uploaded)
> Note: CircleCI will most likely start a job now automatically. It will fail, but this is completely fine.
5. Go to Project Settings -> Environment Variables
6. Add the following environment variables:

* SPOTIFY_CLIENT_ID: your Spotify application client id
* SPOTIFY_CLIENT_SECRET: your Spotify application client secret
* SPOTIFY_CODE: the code generated for you when you visited the constructed url above in the last step of the *preparation* section
* GITHUB_TOKEN: your GitHub access token

You're now ready to go! The ci job will run now once every hour and update your personal readme file.

> Important note: when the next ci job fails, it's possible that your generated Spotify code expired. Simply create a new one (step 4 and 5 preparation section) and update the SPOTIFY_CODE environment variable in your CircleCI project. Then re-run the job.

## Other

This was made possible by <a href="https://github.com/chakrakan">chakrakan</a>, please pay him a visit!

Also, if you found any issue with this (typo, tutorial unclear / not working, etc.), please submit an issue or a merge request!