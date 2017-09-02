---
layout: post
title: "handle nvl in postgres"
comments: true
---
<pre style="margin: 0px 0px 1em; padding: 5px; border: 0px; font-size: 13px; width: auto; max-height: 600px; overflow: auto; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; word-wrap: normal; color: #242729; background-color: #eff0f1;">CREATE OR REPLACE FUNCTION nvl(expr1 text, expr2 text)
  RETURNS text AS
$BODY$
  SELECT coalesce($1, $2);
$BODY$
  LANGUAGE sql;</pre>
