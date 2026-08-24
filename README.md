## Rosetta-Docs

- Languages:
  - [Java](https://github.com/Rosetta-Docs/Schema-Language-Java)
  - [Lua](https://github.com/Rosetta-Docs/Schema-Language-Lua)

- Modules:
  - [Project Zomboid](https://github.com/Rosetta-Docs/Schema-ProjectZomboid)
## Example
```json
{
  "$schema": "https://schema.rosetta-docs.com/1.2",
  "version": "1.2"
}
```

### Legacy
```json
{
  "$schema": "https://schema.rosetta-docs.com/1.1",
}
```

## Self-Hosting

**Files**: Host them by pasting each module into the same directory. 

**.htaccess**: This template allows for calling schema files with the same name as directories without their extensions. Modify as needed.
```
DirectorySlash Off

<IfModule mod_rewrite.c>

RewriteEngine On

RewriteCond %{DOCUMENT_ROOT}/$1.schema.json -f
RewriteRule ^([^/]+)$ $1.schema.json [L]

RewriteCond %{REQUEST_FILENAME}.schema.json -f
RewriteRule ^(.*)$ $1.schema.json [L]

</IfModule>

<FilesMatch "\.(json|schema)$">
    Header set Content-Type "application/json; charset=UTF-8"
    Header set Access-Control-Allow-Origin "*"
</FilesMatch>
```
