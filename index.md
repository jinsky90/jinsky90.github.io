<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
  <meta http-equiv="Content-Style-Type" content="text/css">
  <title></title>
  <meta name="Generator" content="Cocoa HTML Writer">
  <meta name="CocoaVersion" content="1561.4">
  <style type="text/css">
    p.p1 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Menlo; color: #24292e; -webkit-text-stroke: #24292e; min-height: 14.0px}
    p.p2 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Menlo; color: #032f62; -webkit-text-stroke: #032f62}
    p.p3 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Menlo; color: #1b1f23; color: rgba(27, 31, 35, 0.3); -webkit-text-stroke: rgba(27, 31, 35, 0.3); min-height: 14.0px}
    p.p4 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Menlo; color: #24292e; -webkit-text-stroke: #24292e}
    span.s1 {font-kerning: none}
    span.s2 {font-kerning: none; color: #24292e; -webkit-text-stroke: 0px #24292e}
    span.s3 {font-kerning: none; color: #22863a; -webkit-text-stroke: 0px #22863a}
    span.s4 {font-kerning: none; color: #6f42c1; -webkit-text-stroke: 0px #6f42c1}
    span.s5 {font-kerning: none; color: #005cc5; -webkit-text-stroke: 0px #005cc5}
    span.s6 {font-kerning: none; color: #032f62; -webkit-text-stroke: 0px #032f62}
    table.t1 {border-collapse: collapse}
    td.td1 {width: 1869.5px; padding: 0.0px 10.0px 0.0px 10.0px}
    td.td2 {width: 50.0px; min-width: 50.0px; padding: 0.0px 10.0px 0.0px 10.0px}
  </style>
</head>
<body>
<table cellspacing="0" cellpadding="0" class="t1">
  <tbody>
    <tr>
      <td colspan="2" valign="top" class="td1">
        <p class="p1"><span class="s1"></span><br></p>
        <p class="p2"><span class="s2">&lt;</span><span class="s3">ul</span><span class="s2"> </span><span class="s4">class</span><span class="s2">=</span><span class="s1">"posts"</span><span class="s2">&gt;</span></p>
      </td>
    </tr>
    <tr>
      <td valign="top" class="td2">
        <p class="p3"><span class="s1"></span><br></p>
      </td>
      <td valign="top" class="td1">
        <p class="p4"><span class="s1"><span class="Apple-converted-space">    </span>{% for post in site.posts %}</span></p>
      </td>
    </tr>
    <tr>
      <td valign="top" class="td2">
        <p class="p3"><span class="s1"></span><br></p>
      </td>
      <td valign="top" class="td1">
        <p class="p4"><span class="s1"><span class="Apple-converted-space">      </span>&lt;</span><span class="s3">li</span><span class="s1">&gt;&lt;</span><span class="s3">span</span><span class="s1">&gt;{{ post.date | date_to_string }}&lt;/</span><span class="s3">span</span><span class="s1">&gt; </span><span class="s5">&amp;raquo;</span><span class="s1"> &lt;</span><span class="s3">a</span><span class="s1"> </span><span class="s4">href</span><span class="s1">=</span><span class="s6">"{{ post.url }}"</span><span class="s1">&gt;{{ post.title }}&lt;/</span><span class="s3">a</span><span class="s1">&gt;&lt;/</span><span class="s3">li</span><span class="s1">&gt;</span></p>
      </td>
    </tr>
    <tr>
      <td valign="top" class="td2">
        <p class="p3"><span class="s1"></span><br></p>
      </td>
      <td valign="top" class="td1">
        <p class="p4"><span class="s1"><span class="Apple-converted-space">    </span>{% endfor %}</span></p>
      </td>
    </tr>
    <tr>
      <td valign="top" class="td2">
        <p class="p3"><span class="s1"></span><br></p>
      </td>
      <td valign="top" class="td1">
        <p class="p4"><span class="s1"><span class="Apple-converted-space">  </span>&lt;/</span><span class="s3">ul</span><span class="s1">&gt;</span></p>
      </td>
    </tr>
  </tbody>
</table>
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>
</body>
</html>
