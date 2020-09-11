This repository is meant to be used as a sandbox for freeform experimentation with Drupal theming. It is definitely not production ready :)

I have been using the Acquia Dev Desktop 2 (https://dev.acquia.com/downloads). To use the theme in this repository:

* You can use this theme within an existing local Drupal deployment, or you can create a new clean deployment
* Goto the Drupal directory in your file system (linked from the dev desktop, if applicable)
* Clone this repository in `<drupal_dir>/themes/custom/`
* Open the your Drupal site in your browser (dev desktop provides a clickable link, if applicable)
* Enable the custom theme using the Drupal admin UI
  * Click the Appearance tab
  * Scroll down to "Unintalled Themes" section
  * Click "Install and set as default"

When working with this theme in Drupal, I'd recommend doing the above and opening your root Drupal directory, so that you have access to Drupal's built in theme. Since this theme is based on the built in theme, _Classy_, it is helpful to be able to open _Classy_ templates in your IDE and/or copy them into this theme for easier customization.

## Setting up Drupal

Once installed into your local Drupal, your front page won't yet look right. Some blocks won't be rendered, or rendered in the wrong region. I also have a few custom blocks defined within Drupal to fill out some static content.

### Custom Blocks

#### JHU Library Logo Light

Just the JHU Sheridan Library light/white version of the logo in a custom block. This is placed in the `footer first` region

#### Footer contacts

This should eventually change to include static links to the library's social media pages. This is placed in the `footer second` region.

```
The Sheridan Libraries
Johns Hopkins University
40-516-8335 (Library Info Desk)

<em>place socials here</em>
```

#### Copy stmt

More static content for the footer, placed in the `footer fourth` region.

`(c) 2020 Johns Hopkins University`

#### Front page blurb

Static text for the front page.

```
The five Sheridan Libraries - the Milton S. Eisenhower Library, the Brody Learning Commons, the Albert D. Hutzler Reading Room, the George Peabody Library, and the John Work Garrett Library - provide the major research library resources for Johns Hopkins University.

Together the Libraries contain more than 4.2 million volumes and provide round-the-clock access to a rich collection of electronic resources, including more than 154,000 print and e-journals, and more than 1.6 million e-books.
```

### Custom Menus

Several custom menus are placed in the site.

#### Footer help menu

* Help & Support
* Librarians & Staff Directory
* Libraries & Hours

#### Footer legal

* Confidentiality
* Disclaimer
* Policy
* Privacy

#### Need more information?

* About the repositories
* Contact Us
* Ask a Librarian

#### Other libraries link menu

* Sheridan Libraries
* Welch Medical Library
* SAIS Library
* Friedheim Music Library

### Block Layout

#### Top Menu region

* Other libraries link menuo
* User account menu

#### Header region

* Site branding
* Search
* Breadcrumbs

#### Highlighted region

* Front page highlight links (only on `<front>`)

#### Content region

* Front page blurb (only on `<front>`)
* Main page content

#### Left sidebar

#### Right sidebar

* Need more information (custom menu, only on `<front>`)

#### Footer first

* JHU Library Logo Light (custom block)

#### Footer second

* Footer contacts (custom block)

#### Footer third

* Footer help menu (custom menu)

#### Footer fourth

* Copy stmt (custom block)
* Footer legal (custom menu)

### Custom content types

#### Highlighted Link

Highlighted link intended to be displayed prominently on the front page. Not fully functional at the moment, nor fully styled. Intention is to display this "link" with an image, title, and short description.

Fields:

* Highlighted link image : Medium sized image (~480 x 320)
* Description : short text description
* Highlight type : Taxonomy (front_page|collection|item)

Content:

I have two content instances of this content type, one for each highlight on the front page mockup: Library Collections, and JHU Scholarship

### Custom Views

#### Front page highlight links

New Grid view of `highlight-link`s displaying fields: image, title, body. As much as possible should be clickable. This part isn't working to take you to the intended destination...

Content type selected by `type == front_page`.
