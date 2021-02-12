---
layout: full-width
---

# 1.9 Release Information 

## OpenMage LTS 1.9.x release notes
### v19.4.10
3 security updates

CMS Editor code execution
Widget instances allows a hacker to inject an executable file on the server
Layout XML RCE Vulnerability

More Changes:
Adds support for "SameSite" cookie property
Fixed return type of Mage_Adminhtml_Block_System_Config_Form::_canShowField
Add start & stop commands to ddev setup in readme
Update static-code-analyses.yml
Reduced multiple dispatch events in login form.
Github Action Labeler Bot
Allow rewrite of Mage_Core_Model_File_Validator_Image
Allow debug in admin
Declare two variables
Allow min pass length to 5 during login
Removed 2 unneeded function calls. Local var is already there.
Fix class name and filename for case sensitive filesystems
Fix getId() on bool when primary billing address is null
Fixed adminhtml boxes.css fieldset-wide for note.
New event "adminhtml_sales_order_create_save_before" when editing an order.
 Fixes PHP7.4 deprecated nested ternary operators
TypeError: round(): Argument #1 ($num) must be of type int|float

