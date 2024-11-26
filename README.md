# Shiny documentation
Documentation for setting up and adding people to the CCB shiny account

## First app of new user

1. Log in on shinyapps.io
2. Go to Members &rarr; Invite User
3. In R, install `rsconnect` - `install.packages("rsconnect")`
4. Add Shinyapps security token in `R`

   Shinyapps.io &rarr; account &rarr; token &rarr; show &rarr; copy &rarr; run in `R`
6. Deploy app: `rsconnect::deployApp('/path/to/shiny/dir')`

   If custom names are required (recommended) you can run it in the following way: `rsconnect::deployApp('path/to/shiny/dir', appName = "Your-App_Name")`

   Check out the help for more options `?rsconnect::deployApp`
8. Change settings of your app if needed

   Shinyapps.io &rarr; applications &rarr; all &rarr; {your_app} &rarr; settings


## Additional info
### Increase max bundle size of app (default is 1GB, max is 3GB)

`options(rsconnect.max.bundle.size=3145728000)`


### Add custom domains
This is not operational yet, need to get back to VIB Communications.

Shinyapps.io &rarr; Account &rarr; Domains &rarr; Add domain

Applications deployed on shinyapps.io are accessible by loading a URL of the form: https://<account-name>.shinyapps.io/<application-name>/. Organizations that would like to have greater control over the URLs that their applications are served on can subscribe to the Professional plan and host the application on domains that belong to them.

To enable this feature, which is only available with the Professional plan, you will need to follow these steps:

1. Decide on domain(s) or subdomain(s) that you would want to host your applications on. (Example: acmeshinyapps.com or apps.acme.com)
2. Ask your IT administrator to setup a CNAME from that domain/subdomain to your account domain. For example, if your account name is “acme” and the domain you would like to set up is apps.acme.com, then you must create a CNAME from apps.acme.com to acme.shinyapps.io. Steps to accomplish this can vary depending on domain registrar or DNS provider, so we recommend that you consult your provider’s documentation for exact instructions to complete this step.
3. Once the domain record has been created, log into the shinyapps.io dashboard and navigate to Account -> Domains. From here, you can add the domain or subdomain from above and then click Add Domain.
