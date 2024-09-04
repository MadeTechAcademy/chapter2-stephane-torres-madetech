# Question sheet

Commit your answers to these questions in your copy

## Part 1
Answer these after a day or two to see how much you remember

1. What principle(s) can we apply to improve the size of images?
    Using different/better base images and tags, making sure we are only building using what we actually need, 
    minimising bloat.
    We can inspect the size of an image (in bytes) by running docker inspect -f "{{ .Size }}" <image name>
    May need to pull the image locally to be able to do this  
    Docker Hub is a massive image respository, searchable and filterable to help find images that may be useful

2. What principle(s) can we apply to speed up rebuilds of images locally?
    Using caching, order of commands, using more appropriate images as above.
    Ensuring a more efficient order to our commands along with caching means we can avoid rebuilding layers that might necessarily 
    change that often, example, installing dependencies close to the top of our image and copying test files that might change quite 
    a bit further down in the execution.
    Layers will be rebuilt even if they themselves haven't changed but any above them have.

    Creating and using custom base images can also help with speeding up, pulling out commonly used commands to build a different images
    into a custom image and then having that made locally can reduce the time locally.

3. What principles can we apply to speed up builds of an image in a pipeline?

4. What are examples of artefacts, files or values we would not want to have baked into a shipped image used in production and why?
    Might not want to share your Dockerfile, any files with secrets present like API keys of PAT (tokens), stop those who may have malicious
    intentions from being able to access what they shouldn't, them in the dark about how our projects might be made and potential vulnerabilities.

5. What principles can we apply to avoid this?
    Using a .dockerignore file so that certain files/folders aren't copied and built 
    Using multistage builds to hide what was baked into previous images/steps

6. Which exercise had the biggest impact on the image quality and why?

## Part 2
Answer these after some reflection on your delivery

1. Which is the most important type of problem to fix first and why?
2. What problem have you spotted on your delivery that either needs improving or has been solved by one of these approaches? (or another approach we haven’t discussed)
3. Give an example of a problem you spotted and the proposal you made for it to be fixed
4. Give an example of a problem you were involved in fixing and the impact that the fix brought. How was the impact measured?

