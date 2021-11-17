# Validations in Aras
<div class='editDate'>Created/Updated: 2021-10-14</div>

## Introduction
The validation concept in Aras is invented to validate that an Item in Aras of specific type has the information it should have.
As an example you might want to warn or stop a Part of type assembly from being released if it has no Bill Of Material (BOM). Or validate that a type of Part has any document which specifies it. Whatever you want to validate, with the framework/solution you could implement any business logic. With this solution the user will get information immediately, compared to other solutions where the user gets error messages when trying e.g. to release a Part.

This video will do a demonstration. The video also includes some development parts, i.e. showing how you can develop and deploy solutions. The demo is done on an Aras Innovator R11 installation, but it works just as fine in R12.
Source code is in: <https://github.com/hilleconsultit/hc_aras_plm_ext>

<div style="position:relative;height:0;padding-bottom:75.0%">
    <iframe src="https://www.youtube.com/embed/WJLfYEj_thI" width="480" height="360" frameborder="0" allow="autoplay; encrypted-media" style="position:absolute;width:100%;height:100%;left:0" allowfullscreen=""></iframe>
</div>