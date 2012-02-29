Description
-----------
This module provides multilingual features to the Webform Module. Special
options in the webform and component configuration let you enable different
ways to manage translation of forms and questionnaires.

You can choose two different ways to manage localization that cover this
scenarios:

A) If you want to keep a single webform across all nodes in a translation set:
Use i18n_string integration to translate webform strings. This module expose
webform properties, components and emails strings through the i18n module. All
submissions results are related to the original node only.
(You have a "localization by string translation" fieldset in the form settings
to enable this)

B) If you want to keep a webform per node per language but synchronized:
The entire webform structure is replicated when a translated node is created
then you can customize it at will. You can add specific options or components
per language and choose to keep sync: webform properties, components properties,
roles and emails recipients. In this scenario make no sense of having results
attached to one node since each webform could have a different structure with
only a few components in sync.
(You have a "localization by sync" fieldset in the form settings to enable this)

Requirements
------------
Drupal 7.x
Webform Module
i18n Module

Installation
------------
1. Copy the entire webform localization directory the Drupal sites/all/modules
directory.

2. Login as an administrator. Enable the module in the "Administer" -> "Modules"

3. Create a webform node at node/add/webform or edit a existing webform.

3. Enable one of the localization features provided in the webform at "Form
settings". See examples below.


Example A: Manage localization for node/1 using string translation
------------------------------------------------------------------

1. Go to the webform admin section for that node at node/1/webform.

2. Go to the Webform Form settings at node/1/webform/configure.

3. In the "localization by string translation" fieldset enable "Expose webform
component strings suitable for translation." checkbox. That will expose defined
strings to the i18n_string module.

4. [OPTIONAL] In the "localization by string translation" fieldset enable "Keep
a single webform across a translation set." checkbox. This will render the
webform in the source language node, in all nodes within a translation set, so
activate this feature to create a single webform for appear in every translated
node.

5. If you are dealing with a already existing webform you have to do an
additional action for refreshing the string pool for all components.You can
ommit this step if you enable string translation before adding the components.

    - Go to Configuration -> Translate interface -> Strings
    (admin/config/regional/translate/i18n_string)

    - Enable "Webform localization" checkbox

    - Click "Refresh Strings"
    
6. The actual translation is made at
Configuration -> Translate interface -> Translate
(admin/config/regional/translate/translate)
Here you can filter the strings available for translation by "webform" text
group.