### Deploy [fast.ai](https://www.fast.ai) models on [Render](https://render.com)

This repo can be used as a starting point to deploy
[fast.ai](https://github.com/fastai/fastai) models on Render.

The guide for production deployment to Render is at https://course.fast.ai/deployment_render.html.

Prepare your starter app:
   * Fork this repository.
   * Sign up for a Render account.
   * Modify you repository. Render integrates with your GitHub repo
     and automatically builds and deploys changes every time you push a change.

[Deploy](https://course.fast.ai/deployment_render.html#deploy) it:
   1. Create a new **Web Service** on [Render Dashboard](https://dashboard.render.com/)
      and use the repo you created above.
      You will need to grant Render permission to access your repo in this step.
   2. On the deployment screen, pick a name for your service and use **Docker**
      for the Environment. The URL will be created using this service name. The service
      name can be changed if necessary, but the URL initially created can’t be edited.
   3. Click **Save Web Service**. That’s it! Your service will begin building and should be
      live in a few minutes at the URL displayed in your Render dashboard.
      You can follow its progress in the deploy logs.

The sample app described here is up at https://fastai-v3.onrender.com. Test it out with bear images!

You can test your changes locally by installing Docker and using the following command:
```shell script
docker build -t fastai-v3 . && docker run --rm -it -p 5000:5000 fastai-v3
```

Please use [Render's fast.ai forum thread](https://forums.fast.ai/t/deployment-platform-render/33953)
for questions and support.
