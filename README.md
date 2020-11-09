# Secure301

The secure301 stack is a simple solution to an annoying problem - it allows you to have HTTPS redirects with a 301 message. To achieve this the stack utilizes the API Gateway. 

When deploying the stack you have to only manually make a SSL Certificate using the AWS Certificate Manager service, provide all the details in the deployment phase, and you'll get a working redirect. 

We chose to use API Gateway for this because using CloudFront in conjunction with S3 is very slow to work with. It take CloudFront 20 min to deploy the resources across all the regions, where as API Gateway is also deliver over CloudFront, but the deployment is instant. Since CloudFront in this case is managed by AWS itself.

The stack was designed to handle one redirectsion per deployment to keep the solution simple and straight forward.

# DISCLAIMER!

This stack is available to anyone at no cost, but on an as-is basis. 0x4447, LLC. is not responsible for damages or costs of any kind that may occur when you use the stack. You take full responsibility when you use it.

# How to deploy

<a target="_blank" href="https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=zer0x4447-Secure301&templateURL=https://s3.amazonaws.com/0x4447-drive-cloudformation/secure301.json">
<img align="left" style="float: left; margin: 0 10px 0 0;" src="https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png"></a>

All you need to do to deploy this stack is click the button to the left and follow the instructions that CloudFormation provides in your AWS Dashboard. Alternatively you can download the CF file from [here](https://s3.amazonaws.com/0x4447-drive-cloudformation/secure301.json).

# What will deploy?

- 1x API Gateway
- 1x API Gateway Domain

# Manual work

- Prior to deploying the stack you have to create a SSL Cert for the domain you want to redirect from. Using the Certificate Manager service. 
- Once deployed you have to take the geenral API  Gateway domian and update your DNS record.

# Pricing

- [API Gateway](https://aws.amazon.com/api-gateway/pricing/)

# How to generate the CloudFormation file

This repo was build using the [Grapes Frameworks](https://www.npmjs.com/package/@0x4447/grapes). First you need to install the framework:

```
sudo npm install -g @0x4447/grapes
```

Then, go inside this repo and run this command:

```
grapes -s .
```

This will create a `CloudFormation.json` file in the root dir of the repo which you can upload to AWS.

# The End

If you enjoyed this project, please consider giving it a 🌟. And check out our [0x4447 GitHub account](https://github.com/0x4447), where you'll find additional resources you might find useful or interesting.

## Sponsor 🎊

This project is brought to you by 0x4447 LLC, a software company specializing in building custom solutions on top of AWS. Follow this link to learn more: https://0x4447.com. Alternatively, send an email to [hello@0x4447.email](mailto:hello@0x4447.email?Subject=Hello%20From%20Repo&Body=Hi%2C%0A%0AMy%20name%20is%20NAME%2C%20and%20I%27d%20like%20to%20get%20in%20touch%20with%20someone%20at%200x4447.%0A%0AI%27d%20like%20to%20discuss%20the%20following%20topics%3A%0A%0A-%20LIST_OF_TOPICS_TO_DISCUSS%0A%0ASome%20useful%20information%3A%0A%0A-%20My%20full%20name%20is%3A%20FIRST_NAME%20LAST_NAME%0A-%20My%20time%20zone%20is%3A%20TIME_ZONE%0A-%20My%20working%20hours%20are%20from%3A%20TIME%20till%20TIME%0A-%20My%20company%20name%20is%3A%20COMPANY%20NAME%0A-%20My%20company%20website%20is%3A%20https%3A%2F%2F%0A%0ABest%20regards.).
