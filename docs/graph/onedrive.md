# @pnp/graph/onedrive

The ability to manage drives and drive items in Onedrive is a capability introduced in version 1.2.4 of @pnp/graphfi(). Through the methods described
you can manage drives and drive items in Onedrive.

## IInvitations

[![Invokable Banner](https://img.shields.io/badge/Invokable-informational.svg)](../concepts/invokable.md) [![Selective Imports Banner](https://img.shields.io/badge/Selective%20Imports-informational.svg)](../concepts/selective-imports.md)  

| Scenario    | Import Statement                                                  |
| ----------- | ----------------------------------------------------------------- |
| Selective   | import { graphfi } from "@pnp/graph";<br />import "@pnp/graph/onedrive"; |
| Preset: All | import "@pnp/graph/presets/all";    |

## Get the default drive

Using the drive you can get the default drive from Onedrive

```TypeScript
import { graphfi } from "@pnp/graph";
import "@pnp/graph/onedrive";

const drives = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives();

const drives = await graphfi().me.drive();

```

## Get all of the drives

Using the drives() you can get the users available drives from Onedrive

```TypeScript
import { graphfi } from "@pnp/graph";
import "@pnp/graph/onedrive";

const drives = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives();

const drives = await graphfi().me.drives();

```

## Get drive by Id

Using the drives.getById() you can get one of the available drives in Outlook

```TypeScript
import { graphfi } from "@pnp/graph";
import "@pnp/graph/onedrive";

const drive = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives.getById('driveId');

const drive = await graphfi().me.drives.getById('driveId');

```

## Get the associated list of a drive

Using the list() you get the associated list

```TypeScript
import { graphfi } from "@pnp/graph";
import "@pnp/graph/onedrive";

const list = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives.getById('driveId').list();

const list = await graphfi().me.drives.getById('driveId').list();

```

## Get the recent files

Using the recent() you get the recent files

```TypeScript
import { graphfi } from "@pnp/graph";
import "@pnp/graph/onedrive";

const files = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives.getById('driveId').recent();

const files = await graphfi().me.drives.getById('driveId').recent();

```

## Get the files shared with me

Using the sharedWithMe() you get the files shared with the user

```TypeScript
import { graphfi } from "@pnp/graph";
import "@pnp/graph/onedrive";

const shared = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives.getById('driveId').sharedWithMe();

const shared = await graphfi().me.drives.getById('driveId').sharedWithMe();

```

## Get the Root folder

Using the root() you get the root folder

```TypeScript
import { graphfi } from "@pnp/graph";
import "@pnp/graph/onedrive";

const root = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives.getById('driveId').root();

const root = await graphfi().me.drives.getById('driveId').root();

```

## Get the Children

Using the children() you get the children

```TypeScript
import { graphfi } from "@pnp/graph";
import "@pnp/graph/onedrive";

const rootChildren = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives.getById('driveId').root.children();

const rootChildren = await graphfi().me.drives.getById('driveId').root.children();

const itemChildren = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives.getById('driveId').items.getById('itemId').children();

const itemChildren = await graphfi().me.drives.getById('driveId').root.items.getById('itemId').children();

```

## Add folder or item

Using the add you can add a folder or an item

```TypeScript
import { graphfi } from "@pnp/graph";
import "@pnp/graph/onedrive";
import { DriveItem as IDriveItem } from "@microsoft/microsoft-graph-types";

const addFolder = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives.getById('driveId').root.children.add('New Folder', <IDriveItem>{folder: {}});

const addFolder = await graphfi().me.drives.getById('driveId').root.children.add('New Folder', <IDriveItem>{folder: {}});

```

## Search items

Using the search() you can search for items, and optionally select properties

```TypeScript
import { graphfi } from "@pnp/graph";
import "@pnp/graph/onedrive";

const search = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives.getById('driveId')root.search('queryText')();

const search = await graphfi().me.drives.getById('driveId')root.search('queryText')();

```

## Get specific item in drive

Using the items.getById() you can get a specific item from the current drive

```TypeScript
import { graphfi } from "@pnp/graph";
import "@pnp/graph/onedrive";

const item = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives.getById('driveId').items.getById('itemId');

const item = await graphfi().me.drives.getById('driveId').items.getById('itemId');

```

## Get thumbnails

Using the thumbnails() you get the thumbnails

```TypeScript
import { graphfi } from "@pnp/graph";
import "@pnp/graph/onedrive";

const thumbs = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives.getById('driveId').items.getById('itemId').thumbnails();

const thumbs = await graphfi().me.drives.getById('driveId').items.getById('itemId').thumbnails();

```

## Delete drive item

Using the delete() you delete the current item

```TypeScript
import { graphfi } from "@pnp/graph";
import "@pnp/graph/onedrive";

const thumbs = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives.getById('driveId').items.getById('itemId').delete();

const thumbs = await graphfi().me.drives.getById('driveId').items.getById('itemId').delete();

```

## Update drive item

Using the update() you update the current item

```TypeScript
import { graphfi } from "@pnp/graph";
import "@pnp/graph/onedrive";

const update = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives.getById('driveId').items.getById('itemId').update({name: "New Name"});

const update = await graphfi().me.drives.getById('driveId').items.getById('itemId').update({name: "New Name"});

```

## Move drive item

Using the move() you move the current item, and optionally update it

```TypeScript
import { graphfi } from "@pnp/graph";
import "@pnp/graph/onedrive";

// Requires a parentReference to the new folder location
const move = await graphfi().users.getById('user@tenant.onmicrosoft.com').drives.getById('driveId').items.getById('itemId').move({ parentReference: { id: 'itemId'}}, {name: "New Name"});

const move = await graphfi().me.drives.getById('driveId').items.getById('itemId').move({ parentReference: { id: 'itemId'}}, {name: "New Name"});

```
