# JSHint checkstyle file reporter

Writes checkstyle output to a file. This can be used to report JSHint results to **Jenkins**.

## Usage

### Standard JSHint cli

```bash
# optional: specify a different filename, default: checkstyle.xml
export JSHINT_CHECKSTYLE_FILE="jshint.xml"
# run jshint
jshint --reporter node_modules/jshint-checkstyle-reporter *.js subfolder/*.js sub/subfolder.js
```

As of 08/20/2014 JSHint's --reporter checkstyle reporter always logs everything as level error resulting in <error ... /> for every xml entry. I made this tool for that purpose, it translates the fiven issue code to the actual severity level resulting in proper logging.

### Like so:
```XML
<error line="227" column="44" severity="error" message="Too many errors. (16% scanned)." source="jshint.E043" />
<warning line="42" column="14" severity="warning" message="Missing semicolon." source="jshint.W033" />
```

The message codes are up to date as of 08/20/2014