---
title: Config Flow
sidebar_label: Config Flow
---



<head>
  <title> Config Flow</title>
  <meta
    name="description"
    content="your meta content goes here"
  />
</head>



<img src="/img/config/schemaConfig.jpeg" alt="Architecture" />




<!-- This diagram presents a workflow for configuring and deploying a bot application  through a series of interconnected steps involving an admin panel, configuration specifications, and deployment strategies, including the use of feature flags.


## Process Flow

### 1. **Spec for config**
   - Begins with a configuration specification that outlines potential settings for the application.
 

### 2. **Render as Form**
   - The spec is translated into a form within the admin panel.
   - This allows for a user-friendly interface for administrators to input configuration data.

### 3. **Admin Form for Config**
   - This is the admin interface where the configuration data is entered.
   - The form is likely dynamic, adapting to the spec provided in the first step.

### 4. **Filled Form**
   - Represents the admin's input, constituting the selected configuration values for deployment.

### 5. **Deploy**
   - The process of implementing the configurations into the running application or service.

### 6. **Overrides**
   - Any exceptions to the standard configuration are applied here.
   - Overrides enable customization without altering the primary configuration.

### 7. **Pushed to Flagsmith**
   - The configurations, along with any overrides, are pushed to Flagsmith, a feature flag and remote configuration service.

### 8. **User Override**
   - Flagsmith allows configurations to be further customized on a per-user basis.

### 9. **override.config.json**
   - A JSON file that captures the specific configurations that will be used in deployment.
   - Includes details for application-specific settings like modules and molecules.

### 10. **App**
   - The application retrieves and applies settings from `override.config.json`.
   - The diagram indicates a possible need for a secondary override call if necessary.

### 11. **Deployment**
   - The final deployment phase, with the possibility of creating or updating resources and managing configurations across different environments, like previous and production, with overrides as needed.

## Conclusion

This workflow provides a structured and flexible method for managing application configurations, from specification to deployment, with the ability to handle overrides and customizations at both a global and a user level. -->




This diagram presents a workflow for configuring and deploying a bot application  through a series of interconnected steps involving an admin panel, configuration specifications, and deployment strategies, including the use of feature flags

## Molecule Components (MC)

- **Molecule**: These are the primary components of the system, each associated with a `molecule-config.json` file containing specific configuration settings.

- **flag.json**: A configuration file that contains feature flag settings, enabling or disabling features dynamically.

- **style_config.json**: This file stores styling configurations for the molecules.

## Global Configurations

- **App Config (Global)**: Represents the global settings applicable across the application.

- **Defaults**: Defines the default styles and properties for MC components, including whether they can be rendered (`"isAvailable": true`).

## Overrides

- **override.config.json**: Contains override configurations for the application fetched by making an api request to the deployment server, allowing for customization of molecules.

- **flag.json**: Works in conjunction with `override.config.json` to provide feature flag-based overrides.




## Admin Panel Workflow

- **Config**: A json config that can be used for rendering the form.
- **Render as Form**: The spec is rendered into a form within the admin panel allowing admin to configure the bot just by filling the form..


## Deployment Process

- **Deploy Action**: The filled form is deployed, updating the system's configurations.

- **Application (App)**: The application reads the `override.config.json` and applies the configurations. It may also make a secondary call to Flagsmith for user-level overrides.

The described flow ensures that the system's components can be easily managed and customized, providing a flexible and dynamic deployment process.
