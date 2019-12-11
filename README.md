# webplugin-rewarded-example
An example of how a publisher can integrate the webplugin integration to their website using a rewarded approach.

![HowItLooks](https://user-images.githubusercontent.com/4293389/47730087-1ca4b300-dc6a-11e8-8fab-0ce940c60321.png)

## What this example does
- It will not allow the webplugin integration to autostart
- It will change the number of lives provided based on the survey revenue
- It will change the approximate LOI (if provided by the survey) shown to the user
- It will handle the case where a survey is not available

More information can be found [on the webplugin documentation](https://www.pollfish.com/docs/webplugin).

## See it working

The only thing you need to do to see this demo working is to just open or serve the index.html,
or you can just open a dev-server immediately after installing the `live-server` npm package.

First install it
```shell

npm install live-server
```

then just run it and voila, you should be able to visit http://localhost:8080 to see the demo
```shell
live-server
```

(live-server might open the development server in a different port if the port 8080 is already occupied).

## Re-initialising the webplugin after a success or disqualify

If you want your respondents to complete more than one survey, the best approach would be to use our [Offerwall Integration](https://www.pollfish.com/docs/offerwall) but if for any reason you don't want to enable it, you can use the example provided in the `multiple-rewards.html` to achieve a similar goal.

#### Warning

Since the `start` method is not meant to be called twice, in order to avoid side effects and race condition issues, it is recommended that you only run the `start` method after your user _closes_ the panel AND has already screenedOut or finished successfully once.
