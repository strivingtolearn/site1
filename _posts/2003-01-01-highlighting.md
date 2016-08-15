---
layout: post
---

### Ruby

{% highlight ruby %}
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end
{% endhighlight %}

### Bash

{% highlight bash %}
#!/bin/bash
# Comment
trap something ERR
for i in {1..10}; do
  echo "Hello, world"
done
sed -i '/something/d' file
grep "^neat$" /path/to/file
{% endhighlight %}

### Sh (shell)

{% highlight sh %}
#!/bin/sh
# Comment
trap something ERR
for i in {1..10}; do
  echo "Hello, world"
done
sed -i '/something/d' file
grep "^neat$" /path/to/file
{% endhighlight %}

### KSH

{% highlight ksh %}
#!/bin/ksh
# Comment
trap something ERR
for i in {1..10}; do
  echo "Hello, world"
done
sed -i '/something/d' file
grep "^neat$" /path/to/file
{% endhighlight %}

### CSH (not supported by Rouge)

{% highlight csh %}
#!/bin/csh
# Comment
trap something ERR
for i in {1..10}; do
  echo "Hello, world"
done
sed -i '/something/d' file
grep "^neat$" /path/to/file
{% endhighlight %}

### C

{% highlight c %}
#include <stdio.h>
#include <stdlib.h>

int main(void) {
  printf("Hello, world\n");
  return EXIT_SUCCESS;
}
{% endhighlight %}

### C++

{% highlight cpp %}
#include <iostream>

int main() {
  std::cout << "Hello, World.";
  return 0;
}

{% endhighlight %}

### HTML

{% highlight html %}
<!DOCTYPE html>
  <head>
    <title>Title</title>
    <style>body {width: 500px;}</style>
    <script type="application/javascript">
      function $init() {return true;}
    </script>
  </head>
  <body>
    <p class="test" id='title'>Hello, world</p>
    <!-- here goes the rest of the page -->
  </body>
</html>
{% endhighlight %}

### CSS

{% highlight css %}
/* default styling based on github.com/necolas/normalize.css */

article,
summary {
        display: block;
}

html {
        background-color: #fff;
        color: #333;
        font-family: "Roboto", sans-serif;
}

p:before {
        -webkit-box-sizing: border-box;
}

blockquote,
q {
        color: #777;
        /*font-size: 1.5em;*/
        /*font-style: italic;*/
        quotes: none;
        -webkit-hyphens: none;
}

.vi    { color: #008080 }
.il    { color: #099 }

@media only screen and (max-device-width: 640px) {
        body {
                margin: .5em;
                padding: 0;
        }
}

{% endhighlight %}

### Perl

{% highlight perl %}
#!/usr/bin/perl -w

eval 'exec /usr/bin/perl -w -S $0 ${1+"$@"}'
    if 0; # not running under some shell
use strict;

my @ps0 = split(/\%\{(.*?)\%\}/, $ps0);
  if (@ARGV) {
    foreach (@ARGV) {
      return {error=>"invalid parameter $_"} unless /^(\w+)\=(.*?)$/;
      my ($key,$val) = ($1,$2);
      $val =~ s/\%(.)/exists $formatliteral{$1} ? $formatliteral{$1} : ''/ge;
      $opt{$key} = $val;
    }
  }
{% endhighlight %}

### Make

{% highlight make %}
MAIN_MAKEFILE=1
include config.mak

vpath %.c    $(SRC_PATH)
vpath %.cpp  $(SRC_PATH)
PROGS-$(CONFIG_FFMPEG)   += ffmpeg
PROGS      := $(PROGS-yes:%=%$(PROGSSUF)$(EXESUF))
DATA_FILES := $(wildcard $(SRC_PATH)/presets/*.ffpreset) $(SRC_PATH)/doc/ffprobe.xsd
.config: $(wildcard $(FFLIBS:%=$(SRC_PATH)/lib%/all*.c))
        @-tput bold 2>/dev/null
SUBDIR_VARS := CLEANFILES EXAMPLES FFLIBS HOSTPROGS TESTPROGS TOOLS      \
               HEADERS ARCH_HEADERS BUILT_HEADERS SKIPHEADERS
$(foreach P,$(PROGS-yes),$(eval $(call DOPROG,$(P))))
.PHONY: all all-yes alltools check *clean config install*

{% endhighlight %}

### Diff

{% highlight diff %}
diff --git a/_posts/2013-01-01-highlighting.md b/_posts/2013-01-01-highlighting.md
index 1ee0f62..7e50ac4 100644
--- a/_posts/2013-01-01-highlighting.md
+++ b/_posts/2013-01-01-highlighting.md
@@ -5 +5 @@ layout: post
-## Ruby
+### Ruby
@@ -113,0 +114,36 @@ int main() {
+/* default styling based on github.com/necolas/normalize.css */
+
+article,

{% endhighlight %}

### Python (barely supported by Rouge)

{% highlight python %}
#!/usr/bin/python

import optparse
import subprocess
optparse.OptionParser.format_epilog = lambda self, formatter: self.epilog
# Open an output file if requested.
if options.filename is not None:
  sys.stdout = open(options.filename, 'w')
    for line in data:
      line   = line.strip('\n')
try: outtrack
except NameError:
except IOError as e:
  sys.exit(e)
{% endhighlight %}

### PHP

{% highlight php %}
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" xml:lang="en">
<?php
  date_default_timezone_set("UTC");

  // Initialize sql object
  $sql = NULL;
  // Initial forms for disabling, removing, or viewing old hosts
  if (!isset($_POST["submit"])) {
    get_host("disable");
    get_host("remove");
    get_old_hosts();
  }
  function bye() {
    echo "<p><a href=\"$_SERVER[REQUEST_URI]\">Start over</a></p>";
    echo "</body></html>";
    exit();
  }

{% endhighlight %}

### SQL (barely supported by Rouge)

{% highlight sql %}
select name, ip, environment
	FROM hosts
	ORDER BY environment, name;
select name, updated_at, timediff(now(),created_at)
  from hosts
  where updated_at <= date_sub(now(), interval 24 hour);
select distinct fact_values.value
  from fact_names
  join fact_values
    on fact_values.fact_name_id=fact_names.id
  where fact_names.name="roles"
  order by value;
SELECT a, b FROM c JOIN (d,e) ON c.id = d.id AND d.id = e.fid;
SELECT a, b FROM c JOIN (d CROSS JOIN e) ON c.id = d.id AND d.id = e.fid;
\d pg_attribute
{% endhighlight %}

### MySQL (not supported by Rouge)

{% highlight mysql %}
select name, ip, environment
	FROM hosts
	ORDER BY environment, name;
select name, updated_at, timediff(now(),created_at)
  from hosts
  where updated_at <= date_sub(now(), interval 24 hour);
select distinct fact_values.value
  from fact_names
  join fact_values
    on fact_values.fact_name_id=fact_names.id
  where fact_names.name="roles"
  order by value;
SELECT a, b FROM c JOIN (d,e) ON c.id = d.id AND d.id = e.fid;
SELECT a, b FROM c JOIN (d CROSS JOIN e) ON c.id = d.id AND d.id = e.fid;
\d pg_attribute
{% endhighlight %}

### PostgreSQL (not supported by Rouge)

{% highlight postgresql %}
select name, ip, environment
	FROM hosts
	ORDER BY environment, name;
select name, updated_at, timediff(now(),created_at)
  from hosts
  where updated_at <= date_sub(now(), interval 24 hour);
select distinct fact_values.value
  from fact_names
  join fact_values
    on fact_values.fact_name_id=fact_names.id
  where fact_names.name="roles"
  order by value;
SELECT a, b FROM c JOIN (d,e) ON c.id = d.id AND d.id = e.fid;
SELECT a, b FROM c JOIN (d CROSS JOIN e) ON c.id = d.id AND d.id = e.fid;
\d pg_attribute
{% endhighlight %}

### Text 1

{% highlight text %}
set nocompatible
set backspace=2
set ruler
set background=dark
syntax on
let loaded_matchparen=1
map <F6> <Esc>:set spell spelllang=en_us<CR>
map <F7> <Esc>:set nospell<CR>
{% endhighlight %}

### Text 2

{% highlight text %}
$ head /etc/hosts
#
127.0.0.1	localhost.localdomain		localhost
#192.168.13.10	localhost.localdomain
{% endhighlight %}

### ViM (barely supported by Rouge)

{% highlight vim %}
set nocompatible
set backspace=2
set ruler
set background=dark
syntax on
let loaded_matchparen=1
map <F6> <Esc>:set spell spelllang=en_us<CR>
map <F7> <Esc>:set nospell<CR>
{% endhighlight %}

### Awk (not supported by Rouge)

{% highlight awk %}
awk 'BEGIN{print "Hello World"}'
echo "" | awk 'BEGIN{print "Hello World"}'
echo "Hello World" | awk '{print $0}'
{% endhighlight %}

### Console (not supported by Rouge)

{% highlight console %}
$ cat /etc/vim/vimrc
set nocompatible
set backspace=2
set ruler
set background=dark
syntax on
let loaded_matchparen=1
map <F6> <Esc>:set spell spelllang=en_us<CR>
map <F7> <Esc>:set nospell<CR>
{% endhighlight %}
