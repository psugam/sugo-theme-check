+++
title = 'Hello Post'
date = 2023-03-15T11:00:00-07:00
draft = false
tags = ['red','green','blue']
authors = ['Alice', 'Bob']
toc=true
slug='hello-wassup'
+++


# Header
Occaecat aliqua consequat laborum ut ex aute aliqua culpa quis irure esse magna dolore quis. Proident fugiat labore eu laboris officia Lorem enim. Ipsum occaecat cillum ut tempor id sint aliqua incididunt nisi incididunt reprehenderit. Voluptate ad minim sint est aute aliquip esse occaecat tempor officia qui sunt. Aute ex ipsum id ut in est velit est laborum incididunt. Aliqua qui id do esse sunt eiusmod id deserunt eu nostrud aute sit ipsum. Deserunt esse cillum Lorem non magna adipisicing mollit amet consequat.
## spd
## hello

{{< codeblock >}}
{{- /*
Renders a menu for the given menu ID.

@context {page} page The current page.
@context {string} menuID The menu ID.

@example: {{ partial "menu.html" (dict "menuID" "main" "page" .) }}
*/}}

{{- $page := .page }}
{{- $menuID := .menuID }}

{{- with index site.Menus $menuID }}
  <div id="darkmode-toggle-container">
    <button id="darkmode-toggle" aria-label="Toggle dark mode">
      <span id="darkmode-icon" style="pointer-events:none;display:flex;align-items:center;">
        <!-- Sun icon for light mode (with rays), moon icon for dark mode; JS will toggle visibility -->
        <svg id="icon-sun" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" style="display:inline;"><circle cx="12" cy="12" r="5"/><g stroke="currentColor" stroke-width="2"><line x1="12" y1="1" x2="12" y2="3"/><line x1="12" y1="21" x2="12" y2="23"/><line x1="4.22" y1="4.22" x2="5.64" y2="5.64"/><line x1="18.36" y1="18.36" x2="19.78" y2="19.78"/><line x1="1" y1="12" x2="3" y2="12"/><line x1="21" y1="12" x2="23" y2="12"/><line x1="4.22" y1="19.78" x2="5.64" y2="18.36"/><line x1="18.36" y1="5.64" x2="19.78" y2="4.22"/></g></svg>
        <svg id="icon-moon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" style="display:none;"><path d="M21 12.79A9 9 0 0111.21 3a7 7 0 100 14 9 9 0 009.79-4.21z"/></svg>
      </span>
    </button>
  </div>
  <nav class="navbar" style="display: flex; align-items: center; justify-content: center; gap: 1rem; position: relative;">
    <button id="menu-toggle" aria-label="Toggle menu">&#9776;</button>
    <ul id="main-menu" class="hide-menu" style="flex: 1 1 auto; gap: 0; justify-content: center; align-items: center; padding: 0; margin: 0; margin-bottom: 1rem;">
      {{- partial "inline/menu/walk.html" (dict "page" $page "menuEntries" .) }}
    </ul>
  </nav>
{{- end }}

{{- define "_partials/inline/menu/walk.html" }}
  {{- $page := .page }}
  {{- range .menuEntries }}
    {{- $attrs := dict "href" .URL }}
    {{- if $page.IsMenuCurrent .Menu . }}
      {{- $attrs = merge $attrs (dict "class" "active" "aria-current" "page") }}
    {{- else if $page.HasMenuCurrent .Menu .}}
      {{- $attrs = merge $attrs (dict "class" "ancestor" "aria-current" "true") }}
    {{- end }}
    {{- $name := .Name }}
    {{- with .Identifier }}
      {{- with T . }}
        {{- $name = . }}
      {{- end }}
    {{- end }}
    <li>
      <a
        {{- range $k, $v := $attrs }}
          {{- with $v }}
            {{- printf " %s=%q" $k $v | safeHTMLAttr }}
          {{- end }}
        {{- end -}}
      >{{ $name }}</a>
      {{- with .Children }}
        <ul>
          {{- partial "inline/menu/walk.html" (dict "page" $page "menuEntries" .) }}
        </ul>
      {{- end }}
    </li>
  {{- end }}
{{- end }}

{{< /codeblock >}}

![Bryce Canyon National Park](bryce-canyon.jpg)

Sit excepteur do velit veniam mollit in nostrud laboris incididunt ea. Amet eu cillum ut reprehenderit culpa aliquip labore laborum amet sit sit duis. Laborum id proident nostrud dolore laborum reprehenderit quis mollit nulla amet veniam officia id id. Aliquip in deserunt qui magna duis qui pariatur officia sunt deserunt.


Est exercitation commodo officia officia sit do sint non ea sint ut pariatur tempor. Commodo minim cupidatat esse occaecat enim. Amet qui reprehenderit id anim veniam tempor eiusmod dolor veniam. Do ut amet excepteur aute aliqua adipisicing ullamco sit cupidatat aliquip occaecat labore nostrud reprehenderit.
#### sugam
Nostrud Lorem ea enim Lorem sunt aliquip sint incididunt pariatur est nisi laborum cillum. Fugiat proident magna incididunt ipsum sunt exercitation id nulla. Esse non est dolore sint quis ipsum aliqua ex ex. Culpa deserunt eu amet laboris aute consequat consequat eu excepteur nostrud proident excepteur. Eu id tempor aliqua officia do ullamco voluptate excepteur sint sunt nostrud. Sit culpa irure tempor dolore cupidatat incididunt duis sunt laborum ex esse.
##### pokharel
Nostrud Lorem ea enim Lorem sunt aliquip sint incididunt pariatur est nisi laborum cillum. Fugiat proident magna incididunt ipsum sunt exercitation id nulla. Esse non est dolore sint quis ipsum aliqua ex ex. Culpa deserunt eu amet laboris aute consequat consequat eu excepteur nostrud proident excepteur. Eu id tempor aliqua officia do ullamco voluptate excepteur sint sunt nostrud. Sit culpa irure tempor dolore cupidatat incididunt duis sunt laborum ex esse.

## what 
Commodo excepteur reprehenderit magna proident. Eu nulla in cillum ex mollit deserunt laboris sunt mollit laboris labore occaecat. Aliqua ad dolor incididunt nulla veniam sunt non duis et minim non. Velit commodo voluptate deserunt aute proident.

#### how
Et exercitation dolore esse exercitation nostrud id. Qui do laborum ut deserunt quis id aute. Labore adipisicing cillum ad minim cupidatat eu cillum irure. Exercitation ea elit adipisicing elit excepteur ad id. Nostrud Lorem amet adipisicing ut nostrud excepteur aute est eu. Incididunt laborum ex magna magna adipisicing. Nisi aliquip incididunt amet consequat irure tempor elit esse.
##### when

Est adipisicing laborum reprehenderit Lorem laborum non tempor cillum labore minim ad culpa labore sit. Dolore dolore dolor est eu incididunt sint pariatur est id ex laboris. Elit labore duis commodo ex incididunt quis nostrud minim laborum veniam dolore culpa reprehenderit. Deserunt Lorem eu anim sunt aliqua ut nostrud.

Cillum laboris et dolor minim deserunt tempor qui amet occaecat. Pariatur nisi aliquip commodo commodo minim tempor. Incididunt minim Lorem fugiat nostrud sunt occaecat sit nulla. Dolore sit consectetur sit dolor ex magna. Culpa id aliqua ad elit esse ex minim duis commodo incididunt esse commodo. Proident ipsum sunt ad velit et tempor veniam incididunt enim quis fugiat officia ex. Veniam nisi adipisicing nulla ad sint labore.