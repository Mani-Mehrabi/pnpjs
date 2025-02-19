# @pnp/sp/forms

Forms in SharePoint are the Display, New, and Edit forms associated with a list.

## IFields

[![Invokable Banner](https://img.shields.io/badge/Invokable-informational.svg)](../concepts/invokable.md) [![Selective Imports Banner](https://img.shields.io/badge/Selective%20Imports-informational.svg)](../concepts/selective-imports.md)  

|Scenario|Import Statement|
|--|--|
|Selective 1|import { sp } from "@pnp/sp";<br />import { Webs, IWebs } from "@pnp/sp/webs"; <br />
import "@pnp/sp/forms";<br/>
import "@pnp/sp/lists";

### Get Form by Id

Gets a form from the collection by id (guid). Note that the library will handle a guid formatted with curly braces (i.e. '{03b05ff4-d95d-45ed-841d-3855f77a2483}') as well as without curly braces (i.e. '03b05ff4-d95d-45ed-841d-3855f77a2483'). The Id parameter is also case insensitive.

```TypeScript
import { sp } from "@pnp/sp";
import "@pnp/sp/forms";
import "@pnp/sp/lists";

// get the field by Id for web
const form = sp.web.lists.getByTitle("Documents").forms.getById("{c4486774-f1e2-4804-96f3-91edf3e22a19}")();
```
