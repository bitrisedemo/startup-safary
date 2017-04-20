# Startup Safary Demo

---

## Infos

website: [bitrise.io](https://www.bitrise.io)

devcenter: [devcenter.bitrise.io](http://devcenter.bitrise.io)

discuss: [discuss.bitrise.io](https://discuss.bitrise.io)

---

## Workshop

1. [Sign Up](https://www.bitrise.io/users/sign_up) or [Sign In](https://www.bitrise.io/users/sign_in) to Bitrise.io
2. [Add your app](https://www.bitrise.io/apps/add) to Bitrise
  - if you do not have a project to automate, __fork__ our:

ios sample: `https://github.com/bitrisedemo/startup-safary.git`

android sample: `https://github.com/bitrise-samples/sample-apps-android-sdk22.git`

3. Add a `Send a Slack message` step to your primary workflow

  - [join](https://bitrise-demo.herokuapp.com/) to the public bitrise-demo Slack team
  - add a `Send a Slack message` step to the end of your primary workflow
  - __Slack Webhook URL:__ `https://hooks.slack.com/services/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`
  - __Target Slack channel, group or username:__ `builds`
  - fill the remaining inputs

4. Run a new build to ensure, the new step works well
5. Wire in the `deploy` workflow

__in case of ios project__

- navigate to your `Workflow` \ `Code Signing & files`
- retrieve your code sign files by using `Code Signing Doctor`
- upload your code sign files
- navigate to your `Workflow` \ `Triggers`
- wire in your `deploy` workflow
- run a new build with the `deploy` workflow 

__in case of android project__

- navigate to your `Workflow` \ `Code Signing & files`
- select file type: `Android Keystore`
- fill: `Keystore password`, `Keystore alias`, `Private key password`
- Save metadata
- navigate to your `Workflow` \ `Workflow editor`
- add `Sign APK` step to your workflow after `Gradle Runner` step
- run a new build

__in case of xamarin project__

- do both of the ios and android tasks

---

## Notes

Retrieve Incoming Slack WebHook URL:

1. navigate to `https://<YOUR_TEAM_NAME>.slack.com/apps`

or

  - sign in to your slack team
  - open up the navigation popup by clicking on <YOUR_TEAM_NAME> at the top right corner
  - select `Apps & integrations`

2. search for `Incoming WebHooks` integration
3. `Add Configuration`
4. Set `Post to Channel` field
5. `Add Incoming WebHooks integration`
6. Find your URL in `Setup Instructions` section / `Webhook URL`


