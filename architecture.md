# Architecture manifest
This manifest is written to maintain a consistent architecture across all projects in the company.
If the project architecture changes, it must be noted in README.md (in the Architecture field).
All projects must adhere to this topology.
The only exception is the utils directory when used with the Shadcn library. 

## Architecture for root Vue and React project
```
public/                               // Only contains files for CEO optimization, favicons, and other service files
  assets/                             // Folder for favicon and PWA loadable icons
    favicon.ico
  robot.txt
  manifest.json

src/                                  // Root working directory
  app/                                // Only for project-specific files
    App.{tsx, vue}      
    main.{css, scss}
    i18n/                             // Folder for internalization 
      index.ts
      resouses/
        en.ts
        uk.ts
    router/
      index.ts

  components/                         // Folder for components
    shared/
      index.ts                        // File for reexport all shared components (optional)
      Navigation/
        Navigation.{tsx, vue}         // File with component code
        index.ts                      // File for component reexport only
    ui/                               // Folder for atomic components
      Button/
        Button.{tsx, vue}             // File with component code
        index.ts                      // File for component reexport only

  widgets/                            // Folder for finished logical block. Allowed to use only with components
    WidgetName/
      WidgetName.{tsx, vue}
      index.ts

  assets/
    fonts/
    images/
    icons/        

  styles/
    index.{css, scss}                 // Root file for reexport styles
    utils/                            // Folder for variables, fonts, mixins, and other styling files

  hooks/                              // Folder for hook. Hooks must start with `use...`

  utils/
    lib/                              // Folder for utils, which add some new logic, like `classnames`
    dist/                             // Folder for custom utils, like `calcTotalPrice.ts`

  pages/                              // Folder for pages
    index.ts                          // Service file for reexport only
    MainPage/                         // Service name for the root page              
      MainPage.{tsx, vue}             // File for page component
      index.ts                        // File for page component reexport only
```

## Architecture for root Vue and React project
The meta-framework dictates its underlying architecture if the project uses Next.js or Nuxt.js.
All other directories should follow the same topology when using pure React.js and Vue.js frameworks.

## In case of non-compliance with the recommended application architecture
In case of non-compliance with the recommended program architecture, your program will not pass standardized control and sanctions will be applied to you: a warning and a requirement to correct the project architecture by the requirements.
