### Deploy [fast.ai](https://www.fast.ai) models on [Render](https://render.com)
Starter project to deploy a trained [fast.ai](https://github.com/fastai/fastai)
models to the web using Render.

![Web app](data/2019.10.02_web_app.jpg)

Guide for production deployment to Render is
[here](https://course.fast.ai/deployment_render.html).

This is the [original project](https://github.com/render-examples/fastai-v3).

Prepare your starter app:
   * Fork this repository.
   * Sign up for a Render account.

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

Modify you repository:
   * [Share link](https://www.wonderplugin.com/online-tools/google-drive-direct-link-generator/#getsharedurl)
     on `bears_trained_model.pkl` or other Pickle file in your Google Drive.
     Anyone with the link or anyone in the Internet can view it.
   * Create the **downloadable** (*not shareable*) direct link. Use direct link generator for
     [Google Drive](https://www.wonderplugin.com/online-tools/google-drive-direct-link-generator),
     [Dropbox or Onedrive](https://syncwithtech.blogspot.com/p/direct-download-link-generator.html).
   * Edit the file [server.py](app/server.py) inside the [`app`](app) directory and update the
     `model_file_url` variable with the URL copied above.
     Update `export_file_name` to `bears_trained_model.pkl`.
     Update `classes` if you have other classes.
   * Push a change into GitHub. Render integrates with your GitHub repo and automatically builds
     and deploys changes every time you push a change.
   * Wait several minutes (now it is 6 min) for the application to deploy.
   * Test out [this web-site](https://foobar167.onrender.com/) with bear images!

You can test your changes locally by installing Docker and using the following command:
```shell script
docker build -t fastai-v3 . && docker run --rm -it -p 5000:5000 fastai-v3
```

Please use [Render's fast.ai forum thread](https://forums.fast.ai/t/deployment-platform-render/33953)
for questions and support.
