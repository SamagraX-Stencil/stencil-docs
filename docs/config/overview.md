---
title: Overview
sidebar_label: Overview
---



<head>
  <title> Overview </title>
  <meta
    name="description"
    content="your meta content goes here"
  />
</head>


<!-- The Config-based approach streamlines the bot creation process, enabling easy creation or updates through a simple form in an admin panel.

Before explaining it in details let's go through the defination of `atom` and `molecule`

## Atom

An `atom` represents a foundational building block, an independent single component that can be combined with other atoms to form more complex structures, known as molecules. Examples of atoms include Input fields, Buttons, and Typography elements.

## Molecule

A `molecule` is a composite component constructed from various atoms. It represents a more complex UI element that serves a specific purpose within an application's interface. Examples of molecules include a Login Page and an OTP (One-Time Password) Page.


# Steps involved in the process:


### Step 1: Create a Molecule

Begin by creating a molecule in the [molecule repository](https://github.com/SamagraX-Stencil/ui-templates/tree/dev/molecules). Consider potential configurations while designing your molecule.
When designing a molecule, it's essential to first consider the various configurations and customizations that can be applied to enhance its functionality and aesthetic appeal. For instance, when creating a Login molecule, consider customization options such as different label texts, themes, and other properties that can be adjusted to meet the specific requirements of your application's design and functionality.


### Step 2: Define Molecule Configuration

Define the configuration options for your molecule that can be modified via the admin panel. For instance, for a `Navbar` molecule, you might include properties for `brandName`, different `logos`, and their placements.

### Step 3: Configure the Admin Panel

After creating your molecule, incorporate its configuration into the admin panel. This allows for the rendering of inputs for all expected properties, enabling easy customization.

### Step 4: Render the Configuration Form

Based on the defined configuration, render the form elements. This facilitates the dynamic customization of the molecule's properties through the admin panel.

### Step 5: Generate the Final Configuration

Finally, generate the ultimate configuration based on the form inputs. This represents the final step in customizing your bot, ready for deployment.

This approach ensures a flexible and user-friendly method for customizing bot functionalities according to specific requirements. -->


## Streamlining Bot Creation with a Config-Based Approach

The Config-based approach significantly simplifies the bot creation process by enabling easy creation and updates through a straightforward form within an admin panel.

Before delving into the details, let's first understand the definitions of `atom` and `molecule`.

## Atom

An `atom` is a basic building block, representing an independent component that can be used alone or combined with other atoms to form more complex structures, termed as molecules. Examples include Input fields, Buttons, and Typography elements, each serving as a fundamental part of user interface design.

## Molecule

A `molecule` is a compound component made up of various atoms. It represents a more intricate UI element designed to fulfill a specific function within an application's interface. For example, a Login Page or an OTP (One-Time Password) Page, each composed of multiple atoms to provide a comprehensive and functional unit.

## Process Overview

The process involves several steps:

### Step 1: Create a Molecule

Start by designing a molecule in the [molecule repository](https://github.com/SamagraX-Stencil/ui-templates/tree/dev/molecules). When doing so, consider the different configurations and customizations that could be applied to make the molecule versatile and visually appealing. For instance, a Login molecule might offer customization options like label texts variations, theme choices, and other adjustable properties to align with your application's design and functional needs.

### Step 2: Define Molecule Configuration

Specify the configuration options for your molecule that can be altered via the admin panel. For a `Navbar` molecule, for example, configuration properties might include `brandName`, various `logos`, and their placements, allowing for customization to fit the application's branding and design schema.

### Step 3: Configure the Admin Panel

Incorporate the newly created molecule and its configuration options into the admin panel. This step involves setting up the admin panel to display input fields for all the configurable properties of the molecule, thereby simplifying the customization process.

### Step 4: Render the Configuration Form

Utilize the defined configuration to render form elements within the admin panel. This allows for the dynamic alteration of the molecule's properties, enabling administrators to customize the molecule according to specific needs directly from the admin panel.

### Step 5: Generate the Final Configuration

The final step involves generating the ultimate configuration from the admin panel inputs. This configuration is what customizes the bot, making it ready for deployment with its newly defined functionalities and appearance.

Adopting this Config-based approach facilitates a flexible and efficient way to customize bots, ensuring they meet specific requirements with ease.
