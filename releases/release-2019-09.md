**Attention:** If you skipped one or more releases, please also check the release-notes of the skipped ones.

# Repositories

This release consists of the following new versions of the `livingdocs-server` and the `livingdocs-editor`:

Package | Version
--- | ---
`@livingdocs/server` | `release-2019-09`
`@livingdocs/editor` | `release-2019-09`

## Livingdocs Server
How to require the server in your package.json:
```json
"dependencies": {
  "@livingdocs/server": "release-2019-09",
}
```

- Link to the release branch:
  https://github.com/livingdocsIO/livingdocs-server/tree/release-2019-09

### Livingdocs Server Patches
- [v85.3.8](https://github.com/livingdocsIO/livingdocs-server/releases/tag/v85.3.8): fix(request-logger): extend with user id through verified token
- [v85.3.7](https://github.com/livingdocsIO/livingdocs-server/releases/tag/v85.3.7): fix: Upgrade to @livingdocs/framework@^12.6.3

To fix some image service helpers
- [v85.3.6](https://github.com/livingdocsIO/livingdocs-server/releases/tag/v85.3.6): fix(add-pagination-config): add pagination config for document-lists
- [v85.3.5](https://github.com/livingdocsIO/livingdocs-server/releases/tag/v85.3.5): fix(include): Support the `options` parameter in the new sync & async include render function
- [v85.3.4](https://github.com/livingdocsIO/livingdocs-server/releases/tag/v85.3.4): fix(token): add issuer to token if available
- [v85.3.3](https://github.com/livingdocsIO/livingdocs-server/releases/tag/v85.3.3): chore: Migrate to elasticsearch 6 as bluewin is using that by default already in the september release
- [v85.3.2](https://github.com/livingdocsIO/livingdocs-server/releases/tag/v85.3.2): test for release management
- [v85.3.1](https://github.com/livingdocsIO/livingdocs-server/releases/tag/v85.3.1): update framework



## Livingdocs Editor
How to require the editor in your package.json:
```json
"dependencies": {
  "@livingdocs/editor": "release-2019-09",
}
```

- Link to the release branch:
  https://github.com/livingdocsIO/livingdocs-editor/tree/release-2019-09

### Livingdocs Editor Patches
- [v41.9.19](https://github.com/livingdocsIO/livingdocs-editor/releases/tag/v41.9.19): fix: track call, extended info
- [v41.9.18](https://github.com/livingdocsIO/livingdocs-editor/releases/tag/v41.9.18): fix(collaboration): Fix the user names that are shown when another user edits a document
- [v41.9.17](https://github.com/livingdocsIO/livingdocs-editor/releases/tag/v41.9.17): fix(user-proxy): ensure inexistent users have a preview
- [v41.9.16](https://github.com/livingdocsIO/livingdocs-editor/releases/tag/v41.9.16): fix(cropping): editing metadata image check scoped on distinct metafield
- [v41.9.15](https://github.com/livingdocsIO/livingdocs-editor/releases/tag/v41.9.15): fix: Upgrade to @livingdocs/framework@^12.6.3

To fix some image service helpers
- [v41.9.14](https://github.com/livingdocsIO/livingdocs-editor/releases/tag/v41.9.14): fix(compare-toggle): reset diffService selection

Revisions must be reset before compare started again
- [v41.9.13](https://github.com/livingdocsIO/livingdocs-editor/releases/tag/v41.9.13): fix: Migrate to the newer dependency injection syntax
- [v41.9.12](https://github.com/livingdocsIO/livingdocs-editor/releases/tag/v41.9.12): fix: finishing proofreading forces a new revision
- [v41.9.8](https://github.com/livingdocsIO/livingdocs-editor/releases/tag/v41.9.8): search: Fix last publication date on search result
- [v41.9.7](https://github.com/livingdocsIO/livingdocs-editor/releases/tag/v41.9.7): assets: Set default cache time of assets to 1 year again.
- [v41.9.6](https://github.com/livingdocsIO/livingdocs-editor/releases/tag/v41.9.6): component-library: use correct binding variable ref for design modal
- [v41.9.5](https://github.com/livingdocsIO/livingdocs-editor/releases/tag/v41.9.5): design: import groups only where available
- [v41.9.4](https://github.com/livingdocsIO/livingdocs-editor/releases/tag/v41.9.4): Fix webpack config lookup



# Highlights

## Categories :gift:

The categories feature allows to organise routing information and category related metadata such as ad campaigns, analytics, etc.
We provide a Monaco Editor instance in the Project Setup to edit the categories information as a JSON. In addition there are new metadata plugins to enable the categories on content-types as well as a one-click setup that sets up all metadata for pages and articles in one go.

For use in the frontend projects we provide new public API endpoints:
* :heavy_plus_sign: `/routing/resolve` to resolve a given path to a document id
* :heavy_plus_sign: `/categories` to get all categories
* :heavy_plus_sign: `/categories/:id` to get a specific category
Detailed documentation on the new public API endpoints is in the public API documentation `<your-editor-host>/public-api`.

## Reindex Documents via Operation Screen :gift:

Reindexing will often be used when one wants to have updated metadatadata and design for deliveries.
A server administrator can now reindex documents via the `Operations` panel (Server Administration -> Operations) in the editor.
The reindexing mechanism is the same as via the `livingdocs-server` cli.

![elasticsearch-operations](https://user-images.githubusercontent.com/431376/62135777-1750c380-b2e3-11e9-8ec5-b5d23d2c7102.gif)

References:
  * [editor PR #2895](https://github.com/livingdocsIO/livingdocs-editor/pull/2895)

## Teaser Preview :gift:

The Teaser Preview adds an additional read-only view to the publication section of the Livingdocs Editor. It is by default disabled and can only be enabled and configured in a content type config. Examples and more details how to set up a teaser preview, can be found in the [documentation](https://github.com/livingdocsIO/livingdocs/pull/258)

![teaser_preview](https://user-images.githubusercontent.com/546185/63969271-ced32400-caa1-11e9-9428-8b5248ff77e9.gif)

References:
  * [documentation](https://github.com/livingdocsIO/livingdocs/pull/258)
  * [editor PR #2908](https://github.com/livingdocsIO/livingdocs-editor/pull/2908)

## doc-include Enhancements :gift:

doc-include have been enhanced. 
- :heavy_plus_sign: Pass dependencies (css/js) to a doc-include
- :heavy_plus_sign: New `onIncludeRendered` hook

You can find the updated doc-include in the documentation. 
There is also a guide in our documentation on how to set up a Twitter include which uses the new options of doc-includes.

References:
  * [documentation](https://github.com/livingdocsIO/livingdocs/pull/256)
  * [editor PR #2892](https://github.com/livingdocsIO/livingdocs-editor/pull/2892)
  * [framework PR #412](https://github.com/livingdocsIO/livingdocs-framework/pull/412)


## https and api proxy support

The editor has experienced some small but useful improvements

- :heavy_plus_sign: Support ssl certificates for localhost and therefore https/http2
- :heavy_plus_sign: Introduce a proxy for API requests to prevent CORS requests
- :heavy_plus_sign: Serving assets using a cdn url

You can find a more detailled description in the editor PR.

References:
  * [editor PR #2903](https://github.com/livingdocsIO/livingdocs-editor/pull/2903)


# Breaking Changes :fire:

## Migrate the database

```sh
# run grunt migrate to update to the newest database scheme
# migration - 120-add-asset-collections.js
#   create asset collection table
# migration - 121-add-assets-to-indexes.js
#   add assets collection to indexes
# migration - 122-add-user-to-indexes.js
#   add user to indexes
livingdocs-server migrate up
```

## Drop Browser Support

### Changes

- :heavy_minus_sign: Drop browser support for `Safari` older than `v11.1`
- :heavy_minus_sign: Drop browser support for `Microsoft Edge` older than `v18`

References:
  * [editor PR #2825](https://github.com/livingdocsIO/livingdocs-editor/pull/2825)


## Editor Menu: New Config Options

It's now necessary to configure a docment search filter for a Menu. The search filter will be applied when you try to link a document to a menu entry.

### Needed Actions :fire:

If you want to keep the previous behavior, you'll have to add this filter to the Livingdocs Editor config.

**Example**

```js
// all.js
filters: {
  menuList: {
    displayFilters: [],
    defaultQueries: [
      {type: 'documentType', value: 'page'},
      {type: 'documentState', value: 'published'},
      {type: 'sortBy', value: 'relevance'}
    ],
    emptySearchQueries: [
      {type: 'documentType', value: 'page'},
      {type: 'documentState', value: 'published'},
      {type: 'sortBy', value: '-updated_at'}
    ]
  }
}
```

References:
  * [editor PR #2871](https://github.com/livingdocsIO/livingdocs-editor/pull/2871)

## Design Versions

### Changes

The channel properties `available_versions` and `disabled_versions` are no longer checked on 
- document create
- document update
- document publish

References:
  * [editor PR #2410](https://github.com/livingdocsIO/livingdocs-editor/pull/2410)

## Auto update component with `doc-html` directive :fire:

### Changes
The html of a component with a `doc-html` directive will be applied and rendered automatically to a document in the Editor.
The Previous behaviour needed a confirmation to apply html content to a document.

References:
  * [editor PR #2917](https://github.com/livingdocsIO/livingdocs-editor/pull/2917)

## Includes Feature :fire:

Includes API `resolveInclude` + `resolveRawInclude` returns now an object instead of a HTML string.

**Example**

```js
// Before
//   -> returns a HTML string
const includesApi = server.features.api('li-includes')
includesApi.resolveInclude({
  serviceName: 'old-resolve'
}, function (err, html) {
  expect(html).to.be.a.('string')
})
```

```js
// After
//   -> returns an object
const includesApi = server.features.api('li-includes')
includesApi.resolveInclude({
  serviceName: 'new-resolve'
}, function (err, include) {
  expect(include.html).to.be.a.('string')
})
```



# Prototypes

## IMatrics for NLP (Natural Language Processing) analysis

We integrated IMatrics as a prototype:
- Integrated IMatrics in the Livingdocs Editor for NLP analysis of text.
- Allow users to configure IMatrics with a project through the channel config (plugin). 
- Allow users to run analysis on text as well as showing a PoC of related articles.

Here you can watch a [demo video](https://drive.google.com/file/d/17G86pS1ro_iG3otW9LPWb8YFdP1FEbuE/view)

* Related Pull Requests
  * [editor PR ##2861](https://github.com/livingdocsIO/livingdocs-editor/pull/2861)



# Other Changes

* Improvements
  * Dashboard Filter: Allow `notContentType` filters to be a value or an array [livingdocs-editor #2867](https://github.com/livingdocsIO/livingdocs-editor/pull/2867) :gift:
  * Proofreading: Improve load delay and make throttle time configurable [livingdocs-editor #2857](https://github.com/livingdocsIO/livingdocs-editor/pull/2857) :gift:
  * History: Prefix username with colored dots [livingdocs-editor #2890](https://github.com/livingdocsIO/livingdocs-editor/pull/2890) :gift:
  * Asset Management: Add source and read-only section to [livingdocs-editor #2907](https://github.com/livingdocsIO/livingdocs-editor/pull/2907) :gift:
  * Embeds: Allow Editing Iframe Embeds [livingdocs-editor #2921](https://github.com/livingdocsIO/livingdocs-editor/pull/2921) :gift:
  * Document Copy: Allow transformations within the same design [livingdocs-server #2512](https://github.com/livingdocsIO/livingdocs-server/pull/2512) :gift:
* Bugfixes
  * User Management: Prevent group membership assignment in user merging from overwriting [livingdocs-server #2482](https://github.com/livingdocsIO/livingdocs-server/pull/2482) :beetle:
  * Search: Fix `path` query in `documentApi.findOne` [livingdocs-server #2517](https://github.com/livingdocsIO/livingdocs-server/pull/2517) :beetle:
  * Images: Use image size as max value for crop [livingdocs-editor #2836](https://github.com/livingdocsIO/livingdocs-editor/pull/2836) :beetle:
  * Error Handling: Handle invalid content-types on Dashboards [livingdocs-editor #2842](https://github.com/livingdocsIO/livingdocs-editor/pull/2842) :beetle:
  * Differ: Fix relative path of css files in differ [livingdocs-editor #2850](https://github.com/livingdocsIO/livingdocs-editor/pull/2850) :beetle:
  * Editor: Always hide the toolbar on archived documents [livingdocs-editor #2864](https://github.com/livingdocsIO/livingdocs-editor/pull/2864) :beetle:
  * Publish Panel: Show tasks in publish panel on the sidebar [livingdocs-editor #2879](https://github.com/livingdocsIO/livingdocs-editor/pull/2879) :beetle:
  * Access Management: Correctly set access for multiple groups (ABAC) [livingdocs-editor #2885](https://github.com/livingdocsIO/livingdocs-editor/pull/2885) :beetle:
  * liPairSelection: correctly resolve a previous selection [livingdocs-editor #2910](https://github.com/livingdocsIO/livingdocs-editor/pull/2910) :beetle:
  * Proofeading Dashboard: ctrl-click opens a new tab [livingdocs-editor #2929](https://github.com/livingdocsIO/livingdocs-editor/pull/2929) :beetle:

  ---
  **Icon Legend**
  * Breaking changes: :fire:
  * Feature: :gift:
  * Bugfix: :beetle:
  * Chore: :wrench: