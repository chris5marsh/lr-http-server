# lr-http-server

An HTTP server with livereload included. If a file inside the folder being served is changed, added or deleted, the browser will automatically reload.


## Installing

    npm install -g lr-http-server

## Usage

    lr-http-server [-p <port>] [-d <dir>] [-l livereloadport] [-w < watchPaths || false >] [-b] [-x <proxyPath=proxyURL>]

**port** (default *8080*): Port to listen on

**dir** (default *.*): Folder to serve

**livereloadport** (default *35729*): Port for the livereload server. If `false` the livereload is disabled.

**watchPaths**: Comma-separated list of glob patterns for the files to watch. *e.g.* `**/*.js,**/*.css,**/*.html,**/*.xml`

**b**: disable browser open

**proxyPath**: (default false): the path for the proxy to work on e.g. "/media"

**proxyUrl**: (default false): the URL for the proxy to redirect to e.g "https://example.com/media". Should be combined with the *proxyPath* e.g "/media=https://example.com/media"

## Examples

Default usage

    > lr-http-server

    HTTP server listening on port 8080
    Serving <path>
    Livereload listening on port 35729
    Watching files:
      '<path>/**/*.html'
      '<path>/**/*.js'
      '<path>/**/*.css'
      '<path>/**/*.xml'

All options

    > lr-http-server -p 80 -d src/ -l 30000 -w **/*.css,*.html -x "/media=https://example.com/media"

    HTTP server listening on port 80
    Serving <path>/src
    Proxying /media to https://example.com/media
    Livereload listening on port 30000
    Watching files:
      <path>/src/**/*.css
      <path>/src/*.html

