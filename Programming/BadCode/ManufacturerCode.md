# The horrible manufacturer code
<div class='editDate'>Created: 2021-07-01</div>
<div class='editDate'>Updated: 2023-03-03</div>


This is probably the worst piece of code I encountered. And I was supposed to add support for a new template.

``` java
public class MatchingTemplatesTag extends TagSupport {
    private static final String ATTRIBUTE_ST_AVAILABILITY_VALUE_SELECT = "attribute[st_Availability].value";
    private static final long serialVersionUID = 1L;
    private HtmlWriter html;
    private Context ctx;
    public MatchingTemplatesTag() {
    }

    @Override
    public int doStartTag() throws JspException {
        JspWriter writer = pageContext.getOut();
        html = HtmlWriterFactory.newWriter(writer);
        try {

            HttpServletRequest req = (HttpServletRequest) pageContext.getRequest();
            String id = req.getParameter("objectId");
            ctx = Framework.getFrameContext(req.getSession());
            String contextUserName = ctx.getUser();
            BusinessObject boContent = new BusinessObject(id);
            BusinessObjectWithSelect bowsContent = boContent.select(ctx, new StringList(
                    Attributes.PRIMARY_MAUFACTURER_SELECT));

            DomainObject doECOObj = new DomainObject(id);
            // Changes started
            String getType = doECOObj.getType(ctx);
            String doType = "";
            if (getType.equals(com.acme.common.constants.Types.type_ECO)) {
                doType = "PAP";
            } else {
                if (getType.equals(com.acme.common.constants.Types.TYPE_ST_TAPECO)) {
                    doType = "TAP";
                } else {
                    if (getType.equals(com.acme.common.constants.Types.TYPE_ST_PCPECO)) {
                        doType = "PCP";
                    } else {
                        if (getType.equals(com.acme.common.constants.Types.TYPE_ST_PDPECO)) {
                            doType = "PDP";
                        }
                    }
                }
            }
...
// 150 rows of other code I ommitted before reaching the "good" piece
...    
            primManufTemplate = bowsTemplate.getSelectData(Attributes.PRIMARY_MAUFACTURER_SELECT);
            if (primManufTemplate.equals("Other") && primManufContent.equals("Other")
                    || primManufTemplate.equals("SE")
                    && (primManufContent.equals("SE") || primManufContent.equals("GB"))
                    || primManufTemplate.equals("GB")
                    && (primManufContent.equals("SE") || primManufContent.equals("GB"))
                    || !primManufTemplate.equals("Other") && !primManufTemplate.equals("SE")
                    && !primManufTemplate.equals("GB")
                    && !primManufContent.equals("Other") && !primManufContent.equals("SE")
                    && !primManufContent.equals("GB")) {
                if (!first) {
                    html.startElement(javax.swing.text.html.HTML.Tag.BR.toString());
                }
                html.startElement(javax.swing.text.html.HTML.Tag.INPUT.toString());
                html.addAttribute("type", "radio");
                html.addAttribute("name", "Template");
                if (first) {
                    html.addAttribute("checked", "checked");
                    first = false;
                }
                html.addAttribute("value", bowsTemplate.getObjectId());
                html.addText(bowsTemplate.getSelectData("name"));
                html.endElement(javax.swing.text.html.HTML.Tag.INPUT.toString());
            }

        } while (true);
        html.finish();
    } catch (Exception e) {
            e.printStackTrace();
        }
        return 0;
    }

```

Fourteen conditions in an if statement combined with ANDs, ORs and NOTs makes it quite impenetrable for my poor little brain to process.

There are so many bad things in this code, but this if statement is something else.

## How I solved the issue with the bad code.
I inserted the lines below before the real mess started.
``` java
             // PCP templates are handled in a special way
            if (getType.equals(com.acme.common.constants.Types.TYPE_ST_PCPECO)) {
                findMatchingTemplatesForPCP(boContent);
                // Exits to avoid unmaintainable code
                return 0;
            }
```
findMatchingTemplatesForPCP should have been named findAndAddMatchingTemplatesForPCP and the if statement should be written if (isPCP(domainType)) after renamed getType to domainType. The last comment about the "unmaintainable code" is good because it explains WHY the return was done in a middle of 200+ lines of a method.

