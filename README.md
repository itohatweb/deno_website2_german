# Diese Übersetzung ist aktuell noch in Arbeit

# deno_website2

[![Build Status](https://github.com/denoland/deno_website2/workflows/ci/badge.svg?branch=master&event=push)](https://github.com/denoland/deno_website2/actions)

Das ist der Code für https://deno.land/

Diese website besteht aus zwei teilen

1. Einem Cloudflare Worker
2. Einer Next.js app gehostet auf Vercel

Wir möchten saubere und semantische URLs für Module bereitstellen, die in Deno
verwendet werden. Zum Beispiel: https://deno.land/std/http/server.ts

Wenn wir diese Datei in Deno anfordern, möchten wir nur den Inhalt dieser
Datei erhalten. Jedoch, wenn wir diese URL im Browser besuchen, möchten wir 
eine schöne HTML-Datei mit Syntaxhervorhebung sehen.

Um dies zu erreichen, überprüft der Cloudflare Worker, den HTTP-Header, um
festzustellen, ob der Client eine HTML-Datei möchte oder nicht. Wenn eine
HTML-Datei verlangt wird, wird diese Anfrage einfach an Vercel weitergeleitet.
(Wir verwenden Vercel wegen ihrer GitHub Integration.)

## Geschichte

Dies ist eine Neuentwicklung der Deno Website, welche den Code von https://github.com/denoland/deno/tree/f96aaa802b245c8b3aeb5d57b031f8a55bb07de2/website und https://github.com/denoland/registry kombiniert und eine schnellere Bereitstellung ermöglicht.

Dies wurde in React / TailwindCSS / Vercel / CloudFlare Workers geschrieben, nicht in Deno. Idealerweise könnte dies irgendwann nach Deno portiert werden, aber wir brauchen dafür eine neue Website und das braucht zu viel Zeit. Wir hoffen, dass dieser Code mit einem minimalen Entwicklereinfluss nach Deno übertragen werden kann (insbesondere muss es möglich sein, auf FS-Ereignisse warten und den Webserver neu laden zu können).

## Bildlizenz

Diese Deno Bilder werden unter der MIT Lizenz verbreitet (gemeinfrei und kostenlos).

- [Eine Grafik für den v1-Blogbeitrag von @hashroc](https://deno.land/v1.jpg)
