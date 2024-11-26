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


