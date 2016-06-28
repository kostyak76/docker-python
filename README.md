# Python Docker Image

This fork exists as an example of how we can change docker image build for projects to be released and hosted with [Heroku](http://heroku.com) and the
[heroku-docker](https://github.com/heroku/heroku-docker) CLI plugin.

### Differences from its forked counterpart

There is only the one difference and it is - python interpreter version.
I was needed in **python interpreter version 2.7.10** for one of my old long term project.

### Example of use

1. Clone repository
```
$ git clone [address]
```
2. Build docker image
```
$ docker build -t <name_of_your_custom_image>
```
3. The new image should appears in your images list, check that
```
$ docker images
```
4. Image is ready to be a parent for your project. Open auto generated ‘Dockerfile’ and replace image mane in ‘FROM’ command into following line
```
FROM <name_of_you_custom_image>
```
That is it.
After you built target project ‘heroku container:release’ works as expected.
I my case python will be of version 2.7.10 not 2.7.11.

> *Image is not available on Dockerhub*. You are going to build it locally
