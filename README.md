src: https://docs.aws.amazon.com/codebuild/latest/userguide/getting-started-overview.html#getting-started

Apache Maven uses the instructions in the file `pom.xml` to convert the `MessageUtil.java` and `TestMessageUtil.java` files into a file named `messageUtil-1.0.jar` and then run the specified tests.

A buildspec is a collection of build commands and related settings, in YAML format, that CodeBuild uses to run a build. Without a build spec, CodeBuild cannot successfully convert your build input into build output or locate the build output artifact in the build environment to upload to your output bucket.

zip all the files from the source directory:
```
zip -r MessageUtil.zip . -x "*.git/*"
```

`MessageUtil.zip` is uploaded to an AWS S3 bucket.

After the build is complete, AWS CodeBuild uploads the build output artifact (eg `messageUtil-1.0.jar`) to another AWS S3 bucket.
