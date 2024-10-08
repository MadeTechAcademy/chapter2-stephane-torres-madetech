# Question sheet

Commit your answers to these questions in your copy

## Part 1
Answer these after a day or two to see how much you remember

1. What principle(s) can we apply to improve the size of images?<br />

    Using different/better base images and tags, making sure we are only building using what we actually need, 
    minimising bloat.
    We can inspect the size of an image (in bytes) by running 

    ```
      docker inspect -f "{{ .Size }}" <image name>
    ```
    May need to pull the image locally to be able to do this  
    Docker Hub is a massive image respository, searchable and filterable to help find images that may be useful

    OR 

    ```
     docker images
    ```
    To list all of docker images built locally with their size.
   

2. What principle(s) can we apply to speed up rebuilds of images locally?<br />
    Using caching, order of commands, using more appropriate images as above.
    Ensuring a more efficient order to our commands along with caching means we can avoid rebuilding layers that might necessarily 
    change that often, example, installing dependencies close to the top of our image and copying test files that might change quite 
    a bit further down in the execution.
    Layers will be rebuilt even if they themselves haven't changed but any above them have.

    Creating and using custom base images can also help with speeding up, pulling out commonly used commands to build a different images
    into a custom image and then having that made locally can reduce the time locally.

3. What principles can we apply to speed up builds of an image in a pipeline?<br />
    Choosing the correct/more appropriate base images and only baking/building what we actually need

4. What are examples of artefacts, files or values we would not want to have baked into a shipped image used in production and why?
    Might not want to share your Dockerfile, shows what images we're using and potentially how our project might work. Any files with secrets present like API keys or PAT (tokens) We want to stop those who may have malicious intentions from being able to access what they shouldn't, keeping these people in the dark about how our projects might be made and potential vulnerabilities.

5. What principles can we apply to avoid this?<br />
    Using a .dockerignore file so that certain files/folders aren't copied/built<br /> 
    Using multistage builds to hide what was baked into previous images/stages 

6. Which exercise had the biggest impact on the image quality and why?<br />
    I think exercises 1, 5 and 6 probably have the most impact on image quality, making sure we're only using what we need in terms of packages/dependencies and systems, by using appropriate base images. Exercises 5 and 6 focus on what's being exposed and how we can minimise that as much as possible to keep our builds secure. 


## Part 2
Answer these after some reflection on your delivery

1. Which is the most important type of problem to fix first and why?<br/>
    - In general I think security is probably the most important to make sure nothing is being exposed that shouldn't and knowing how to keep what needs to be hidden away hidden, on our delivery all of our repos are public so we are not necessarily hiding how our project is structured, but the keys, names of resources, AWS account numbers etc remain hidden, but aren't exposed in our Dockerfiles.
    - After that we need to make sure it works, quickly and efficiently, so size and order are super important for this. 
2. What problem have you spotted on your delivery that either needs improving or has been solved by one of these approaches? (or another approach we haven’t discussed)<br/>
    - Image size and rebuild speed in development. Making sure an image only usese what it needs.
3. Give an example of a problem you spotted and the proposal you made for it to be fixed.
    - Introducing a .dockerignore file to so that Docker doesn't build unecessary files and folders present in our lambdas files, and not needing to restructure. Also changing some of the order or the file, adding in a copy step for our requirements before pip installing and copying the rest of the needed files over helps with local building of the image, taking advantage of Dockers local caching
4. Give an example of a problem you were involved in fixing and the impact that the fix brought. How was the impact measured?<br/>
    - In local development, just a slightly quicker image build by using caching, and a slightly smaller image size to push 
    ```
      REPOSITORY                                                                TAG       IMAGE ID       CREATED        SIZE
batch-image                                                               latest    9dee18155dcb   5 hours ago    198MB
<none>                                                                    <none>    3826b04cf7cd   5 hours ago    199MB
<none>                                                                    <none>    ddff9d97b05f   5 hours ago    199MB
<none>                                                                    <none>    5d83b25f1799   5 hours ago    198MB
<none>                                                                    <none>    4bcd4979fc07   5 hours ago    507MB
<none>                                                                    <none>    13f48de2c322   5 hours ago    507MB
<none>                                                                    <none>    e201194478ca   5 hours ago    198MB
************.dkr.ecr.eu-west-2.amazonaws.com/ndra-weekly-ods-update       latest    793366f0238d   2 days ago     513MB
    ```
  