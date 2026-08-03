# OpenClaw — File d'attente des outils


## Vague 676 — CLI Tools (Markdown, mots, env, chiffres, phrases)
- [x] markdown-heading-level-check : audite la structure des titres Markdown ATX/Setext (sauts de niveau, premier titre non-H1, doublons insensibles à la casse, >H6 et sans-espace signalés, fences ignorées, histogramme, gates --check/--require-h1/--min-headings/--max-level exit 2, JSON, stdin, 16 tests) ✓ 2026-08-03
- [x] text-word-length-stats : statistiques de longueur des mots (extraction Unicode, chiffres exclus, contractions, mean/median/mode/stdev, histogramme + barres, --min-len, gates --min-words/--max-mean/--min-mean/--max-length exit 2, JSON, stdin, 13 tests) ✓ 2026-08-03
- [x] env-comment-extract : extrait/audite les commentaires .env (full-line + inline, '#' hors quotes, doc-ratio, clés sans doc, --comments-only/--undocumented, gates --check/--require-documented/--min-doc-ratio/--max-undocumented exit 2, JSON, stdin, 15 tests) ✓ 2026-08-03
- [x] text-digit-strip-report : supprime/audite les chiffres du texte (runs reportés ligne:col, --strip/--placeholder, --count-only, gates --check/--require/--max-runs/--max-digits exit 2, JSON, stdin, 16 tests) ✓ 2026-08-03
- [x] text-sentence-split-count : compte les phrases (segmenteur à règles, abréviations Mr./e.g. et décimales 3.14 protégées, stats mots avg/min/max, --list/--count-only, gates --check/--min/--max/--require exit 2, JSON, stdin, 17 tests) ✓ 2026-08-03

## Vague 675 — CLI Tools (env, lignes, CSV, chiffres, booléens)
- [x] env-url-components : décompose/valide les valeurs URL d'un .env (scheme/host/port/path/query/fragment, allow-list --schemes, ports invalides, export/quotes tolérés, gates --check/--require-url exit 2, JSON, stdin, 11 tests) ✓ 2026-08-03
- [x] line-first-word-freq : fréquence du premier mot de chaque ligne (--lowercase/--strip-punct, tris count/alpha/first, --top, gates --require/--min-ratio exit 2, JSON, stdin, 10 tests) ✓ 2026-08-03
- [x] csv-null-marker-stats : stats des marqueurs null-like CSV (NULL/n-a/-/None/\N/vide, par colonne + inventaire, --markers !replace, --ignore-case, gates --check/--max-null-ratio exit 2, JSON, stdin, 9 tests) ✓ 2026-08-03
- [x] text-roman-numeral : convertit chiffres romains <-> entiers (1..3999, validation stricte soustractive regex, roundtrip 1-399 testé, args ou stdin, --check exit 2, JSON, 10 tests) ✓ 2026-08-03
- [x] env-bool-normalize : normalise les valeurs booléennes .env (on/Yes/1/... -> style canonique true-false/1-0/yes-no/on-off, --keys, commentaires inline/export préservés, --check/--dry-run exit 2, JSON, stdin, 11 tests) ✓ 2026-08-03

## Vague 674 — CLI Tools (CSV, Markdown, lignes, texte, env)
5|- [x] csv-quote-consistency : audite la cohérence du quoting des champs CSV par colonne (parser maison multi-lignes, style dominant ou forcé, dominante par colonne, erreurs syntaxe quote non fermée/trailing garbage, --column, gates --check/--max-issues exit 2, JSON, stdin, 12 tests) ✓ 2026-08-03
6|- [x] markdown-table-column-count : compte les colonnes par ligne des tables pipe Markdown (fences ignorées, pipes échappés, --summary, gates --check/--max-ragged/--require-table exit 2, JSON, stdin, 9 tests) ✓ 2026-08-03
7|- [x] line-blank-run-count : compte les runs de lignes vides consécutives (whitespace-blank ou --strict-blank, --min-run, gates --check/--max-run-length/--max-runs exit 2, JSON, stdin, 11 tests) ✓ 2026-08-03
8|- [x] text-word-wrap-check : vérifie que les lignes respectent une largeur max (mesure tab-aware, --width/--tab-stop, --ignore-trailing-space, gates --check/--max-violations exit 2, JSON, stdin, 9 tests) ✓ 2026-08-03
9|- [x] env-interpolation-check : audite les références ${VAR}/$VAR dans un .env (single-quotes sans interpolation, résolution séquentielle + os.environ, undefined/self/cycles, --list-refs, gates --check/--require-refs exit 2, JSON, stdin, 14 tests) ✓ 2026-08-03
10|
11|## Vague 673 — CLI Tools (texte, JSON, INI, CSV, env, Markdown)
12|5|- [x] text-dup-word-adjacent : détecte les mots doublés consécutifs ('the the', position ligne:col du premier mot, runs xN, adjacence whitespace stricte par défaut + --ignore-punctuation, --case-sensitive, gates --check/--max exit 2, JSON, stdin, 17 tests) ✓ 2026-08-03
13|6|- [x] json-key-order-check : vérifie l'ordre des clés des objets JSON (alphabétique par défaut, ou ordre canonique via --reference doc, chemins jq-style, index de divergence, exit 2, JSON, stdin, 13 tests) ✓ 2026-08-03
14|7|- [x] ini-duplicate-section-detect : détecte les sections INI définies plusieurs fois (lignes de chaque occurrence, commentaires ; et # ignorés, warnings headers malformés/noms vides, gates --check exit 2, JSON, stdin, 14 tests) ✓ 2026-08-03
15|8|- [x] csv-cell-padding-audit : audite les cellules CSV avec espaces/tabs en tête ou queue (row/col, side leading/trailing xN, preview nettoyé, délimiteur auto , ; TAB |, quoted préservé, gates --check/--max exit 2, JSON, stdin, 16 tests) ✓ 2026-08-03
16|9|- [x] env-values-numeric-range : valide les valeurs numériques .env contre des plages (inline '# range:MIN-MAX' ou --range KEY=MIN-MAX répétable, devis désquotées, raisons out-of-range/non-numeric, gates --check exit 2, JSON, stdin, 17 tests) ✓ 2026-08-03
17|10|- [x] markdown-list-marker-consistency : vérifie la cohérence du marqueur de listes à puces (-/*/+ ; dominant inféré ou --marker forcé, égalités départagées par première apparition, fences ignorées, listes ordonnées/tâches ok, gates --check exit 2, JSON, stdin, 14 tests) ✓ 2026-08-03
18|11|
19|12|## Vague 672 — CLI Tools (texte, lignes, env, URLs, CSV)
20|13|- [x] text-dedupe-lines-stable : déduplique les lignes en gardant la première occurrence (ordre stable, --ignore-case/--strip, --keep-blank-duplicates, --count, --in-place, gates --check/--require-dupes/--max-dupes exit 2, JSON, 20 tests) ✓ 2026-08-03
21|14|- [x] line-trailing-ws-check : détecte/supprime les espaces/tabulations en fin de ligne (CRLF-aware, --tabs-only/--spaces-only/--min-run/--blank-is-clean, --show marqueurs visibles, --strip/-o/--in-place, gates --check/--max-findings/--require-findings exit 2, JSON, 21 tests) ✓ 2026-08-03
22|15|- [x] env-value-unquote : retire les quotes décoratives des valeurs .env (conservateur par défaut, --all, export/commentaires préservés, '#' dans les quotes non-commentaire, -o/--in-place, gates --check/--require-changes/--max-changes exit 2, JSON, 21 tests) ✓ 2026-08-03
23|16|- [x] text-url-extract : extrait les URLs de tout schéma (ponctuation/parens équilibrées, unique first-seen, --positions/--count/--hosts-only, --schemes, tris, gates --check/--require/--max-count/--max-unique/--require-host exit 2, JSON, 22 tests) ✓ 2026-08-03
24|17|- [x] csv-cell-count-audit : audite les lignes CSV ragged (largeur header/--expect N, sniff délimiteur + fallback, BOM, quotes/newlines, --skip-blank/--sample, gates --check/--max-bad/--require-bad exit 2, JSON, 22 tests) ✓ 2026-08-03
25|18|
26|19|## Vague 671 — CLI Tools (texte, CSV, env, indentation)
27|20|- [x] text-tab-to-spaces : convertit tabulations <-> espaces (tab stops respectés, --to-tabs, CRLF préservé, gates --check/--max-tabs/--require-conversion exit 2, JSON, 19 tests) ✓ 2026-08-03
28|21|
29|22|## Vague 670 — CLI Tools (CSV, env, texte, JSON, préfixes)
30|23|- [x] csv-trailing-space-inline : détecte/corrige les espaces dans les valeurs CSV (quoting préservé, BOM, sniff délimiteur, --strip/--in-place/--diff, gates --check/--require-fields/--max-fields exit 2, JSON, 12 tests) ✓ 2026-08-03
31|24|- [x] env-split-key-value : sépare un .env en fichiers keys/values auditables (export toléré, --placeholder, --quote shlex, --mask REGEX, --keys-only/--values-only, gates --check exit 2, JSON, 11 tests) ✓ 2026-08-03
32|25|- [x] text-reverse-words : inverse l'ordre des mots par ligne (--keep-whitespace, --reverse-chars, --numbers-only, --in-place, gate --check exit 2, JSON, 11 tests) ✓ 2026-08-03
33|26|- [x] json-string-length : longueur de chaque chaîne JSON (chemins jq, --min/--max, tri, --values, --stats, gates --check/--require exit 2, JSON, 11 tests) ✓ 2026-08-03
34|27|- [x] line-strip-prefix : retire un préfixe littéral ou regex de chaque ligne (--strict drop, --report-nonmatching, --in-place/-o, gates --check/--require-matched exit 2, JSON, 12 tests) ✓ 2026-08-03
35|28|
36|29|## Vague 669 — CLI Tools (env, CSV, nombres)
37|30|- [x] env-set-defaults : injecte des valeurs par défaut pour les clés absentes d'un .env (additif, -d KEY=VALUE/--defaults-file, export/--quote, gates --check/--require-existing/--require-added/--max-added exit 2, JSON, 12 tests) ✓ 2026-08-03
38|31|- [x] env-prefix-add : préfixe les clés d'un .env (idempotent, export/commentaires préservés, collisions détectées, --separator, --strict, gates --check/--require-rename/--max-renames exit 2, JSON, 14 tests) ✓ 2026-08-03
39|32|- [x] csv-row-shuffle-seed : mélange reproductible des lignes d'un CSV (seed string, header conservé, délimiteur sniffé, BOM, --no-header, --list-permutation, gates --check/--require-changed/--max-rows exit 2, JSON, 12 tests) ✓ 2026-08-03
40|33|- [x] csv-move-column : déplace une colonne CSV (nom ou #index, --first/--last/--index/--before/--after, --no-header, gates --check/--require-changed exit 2, JSON, 15 tests) ✓ 2026-08-03
41|34|- [x] text-extract-numerics : extrait les nombres d'un texte (décimaux EU/US, séparateurs de milliers, --signed/--integers/--scientific, --positions ligne:col, --stats, gates --check/--require/--max-count exit 2, JSON, 16 tests) ✓ 2026-08-03
42|35|
43|36|## Vague 668 — CLI Tools (env, lignes, JSONL, fichiers, CSV)
44|37|- [x] env-group-prefixes : groupe les clés .env par préfixe (avant le premier underscore, export toléré, --keys-only, --sort name/count, gates --require-group/--require-prefix/--max-groups/--check exit 2, JSON, 9 tests) ✓ 2026-08-03
45|38|- [x] text-line-stats-json : émet un objet JSON par ligne (n, longueur, mots, blank, --with-content, --hash md5/sha1/sha256, --pretty, gates --min-lines/--max-len/--require-non-empty exit 2, JSONL, 8 tests) ✓ 2026-08-03
46|39|- [x] jsonl-to-csv-flat : aplatit JSONL en CSV (union des clés first-seen/--sort-columns, nesting dotted a.b.c, null->"", bool->true/false, --columns, gates --check/--require-column/--min-rows exit 2, JSON, 10 tests) ✓ 2026-08-03
47|40|- [x] file-list-sizes : liste les fichiers d'un dossier avec tailles (tri size/name, -r récursif, --dirs, --human/--binary, --bytes-only, --top/--total, gates --require-files/--max-files exit 2, JSON, 8 tests) ✓ 2026-08-03
48|41|- [x] csv-filter-not-eq : supprime les lignes CSV où une colonne vaut une valeur (--keep-eq inverse, nom/index, --ignore-case, BOM+sniff, gates --require-dropped/--require-remaining/--check exit 2, JSON, 8 tests) ✓ 2026-08-03
49|42|
50|43|## Vague 667 — CLI Tools (JSON, Markdown, CSV, voyelles, tirages)
51|44|- [x] json-empty-stats : rapport des valeurs vides d'un JSON (null/""/[]/{}, chemins jq-style --paths, tri count/path, multi-fichiers, gates --check/--max-empty exit 2, JSON, 10 tests) ✓ 2026-08-03
52|45|- [x] markdown-list-done-move : descend les items cochés des task lists (bullets/numérotés, marques custom --done-marks/--open-marks, fences préservées, ordre relatif conservé, --in-place/--diff/--count, --check exit 2, JSON, 11 tests) ✓ 2026-08-03
53|46|- [x] csv-rename-column : renomme des colonnes CSV par nom ou #index (sniff délimiteur, BOM, collisions/interdits rejetés, --list, --check/--check-absent exit 2, -o, JSON, 13 tests) ✓ 2026-08-03
54|47|- [x] text-vowel-strip : supprime ou rapporte les voyelles (--extended accents, -y, --report/--count-only, gates --check/--min/--max-vowels exit 2, --in-place, JSON, 12 tests) ✓ 2026-08-03
55|48|- [x] line-random-pick : tire N lignes aléatoires (--seed reproductible, --replace, --unique, --numbered, gates --require-lines/--require-distinct exit 2, JSON, 13 tests) ✓ 2026-08-03
56|49|
57|50|## Vague 666 — CLI Tools (fréquences casse, jointure CSV, JSONL, MAC, box, marqueurs)
58|51|- [x] text-word-frequency-case : fréquences de mots avec variantes de casse (casefold grouped, dominant form, filtres min-length/min-count/top, sorts count/variants/alpha, gates check/require-variants/max-variants exit 2, JSON, 9 tests) ✓ 2026-08-03
59|52|- [x] csv-join-key : jointure de deux CSV sur colonne clé (inner/left/right/full, colonnes nom ou #index, --right-on, suffixe collisions, délimiteur sniffé, BOM, gates require-matched/max-unmatched exit 2, JSON, stdin, 10 tests) ✓ 2026-08-03
60|53|- [x] jsonl-split-lines : découpe un flux JSONL en chunks équilibrés (--parts N ou --size N, pattern -o {n}/{total}, markers stdout, validation --validate/--strict, gates require-parts/min-lines/max-line-errors exit 2, JSON, 10 tests) ✓ 2026-08-03
61|54|- [x] env-sample-mac : génère un .env de fixtures MAC-48 (unicast LAA par défaut, --seed reproductible sha256, OUIs vendor apple/cisco/dell/intel/vmware, --oui custom, unicité garantie, --export/--lowercase, gates check/require-count exit 2, JSON, 12 tests) ✓ 2026-08-03
62|55|- [x] text-box-draw : dessine un cadre autour d'un texte (styles ascii/single/double/rounded/heavy, --width wrap, --padding, align left/center/right, --title dans la bordure, gates max-width/min-lines exit 2, JSON, 11 tests) ✓ 2026-08-03
63|56|- [x] markdown-marker-inject : injecte du contenu généré entre sentinelles <!-- NAME --> (création top/bottom si absent, fences ```/~~~ ignorées, --content/--content-file/stdin, --in-place, gates check/require-markers/max-replacements exit 2, JSON, 10 tests) ✓ 2026-08-03
64|57|
65|58|## Vague 665 — CLI Tools (hostnames, caractères, JSON, Markdown, mots)
66|59|- [x] log-extract-hostnames : extrait les hostnames des logs (FQDN RFC 1123, IPv4 --include-ips, shorts --include-short, --suffix, --count/--sort, gates check/require/max-unique/require-domain exit 2, JSON, stdin, 12 tests) ✓ 2026-08-03
67|60|- [x] text-count-characters : compte les caractères par catégorie Unicode (letters/digits/spaces/punct/symbols/controls, ratios, ASCII/non-ASCII, histogramme --top, gates require-min/max-ratio + require-ascii + max-non-ascii exit 2, JSON, 9 tests) ✓ 2026-08-03
68|61|- [x] json-remove-key : supprime récursivement des clés d'un JSON (objets+arrays imbriqués, --key/--keys-from, --count/--list, gates check/require-removal exit 2, JSON rapport, 11 tests) ✓ 2026-08-03
69|62|- [x] markdown-strip-formatting : convertit Markdown en texte pur (gras/italique/code/barré/liens/images/titres/quotes/listes, fences préservées, --diff/--in-place/--count, gate check exit 2, JSON, 10 tests) ✓ 2026-08-03
70|63|- [x] text-word-extract-unique : extrait les mots uniques d'un texte (Unicode, contractions FR/EN, stopwords, filtres length/count, tris, diversité lexicale, gates check/require-min/max-unique exit 2, JSON, 11 tests) ✓ 2026-08-03
71|64|
72|65|## Vague 664 — CLI Tools (UUIDs, Markdown, CSV)
73|66|- [x] log-extract-uuids : extrait et audite les UUIDs des logs (canoniques + compactes --with-compact, normalisation lowercase, versions/variantes, --count/--unique/--stats, gates --check/--require/--max-unique exit 2, JSON, stdin, 11 tests) ✓ 2026-08-03
74|67|- [x] markdown-url-decode : décode les URLs percent-encodées en Markdown (liens inline, ref-defs, URLs nues, fences/code inline protégés, --list/--in-place, gates --check/--require-encoded/--max-encoded exit 2, JSON, 13 tests) ✓ 2026-08-03
75|68|- [x] csv-numeric-filter : filtre un CSV par conditions numériques (--where 'col OP val', between, AND/--or, EU numbers, --no-header, --invert/--count/--strict, gates --require-rows/--max-rows exit 2, JSON, 17 tests) ✓ 2026-08-03
76|69|
77|70|## Vague 663 — CLI Tools (IPv6, shell, netmasks, réseaux, BOM)
78|71|- [x] ipv6-hextet-count : compte les hextets peuplés vs compressés d'adresses IPv6 (expansion/validation ipaddress, gates --min/--max-populated, --require/--forbid-compression exit 2, JSON, stdin, 14 tests) ✓ 2026-08-03
79|72|- [x] shell-redirection-audit : audite les redirections shell (stdout/stderr/both truncate/append, clobber, fd-dup, here-doc/here-string, quotes+commentaires ignorés, kinds, --count, gates --check/--forbid-kind/--max-count exit 2, JSON, 17 tests) ✓ 2026-08-03
80|73|- [x] ip-netmask-convert : convertit netmasks pointillés ⇄ préfixes CIDR (masques non-contigus rejetés, wildcard/host_bits/usable, --to prefix|dotted, gates --min/--max-prefix exit 2, JSON, 16 tests) ✓ 2026-08-03
81|74|- [x] ip-network-border : calcule adresses réseau/broadcast de préfixes IPv4 (host forms normalisés, first/last host, --field, gates --require-network-form/--min/--max-addresses exit 2, JSON, 15 tests) ✓ 2026-08-03
82|75|- [x] csv-add-bom : ajoute/retire/vérifie le BOM UTF-8 des CSV (idempotent, -o copie, --check/--remove/--require-change exit 2, JSON, 12 tests) ✓ 2026-08-03
83|76|
84|77|## Vague 662 — CLI Tools (logs, crochets, niveaux)
85|78|- [x] log-extract-paths : extrait chemins Unix/Windows/URLs/relatifs des logs (kinds, count, min-count, gates check/require exit 2, JSON, stdin, 13 tests) ✓ 2026-08-03
86|79|- [x] paren-balance : vérifie équilibre () [] {} <> (mismatch/unclosed/unexpected, positions ligne:col, --lang py/js/c strings+commentaires ignorés, --max-issues, JSON, 13 tests) ✓ 2026-08-03
87|80|- [x] log-level-count : compte les niveaux TRACE..FATAL (aliases normalisés, kv/bracket/plain, --ratio/--only, gates require-error/forbid-error/max-errors/max-warn-ratio exit 2, JSON, 16 tests) ✓ 2026-08-03
88|81|
89|82|## Vague 661 — CLI Tools (timestamps, env, logs, Markdown, champs)
90|83|- [x] text-extract-timestamps : extrait les timestamps ISO 8601/syslog/Apache/HH:MM:SS/epoch (filtres --kind, --unique, --count, --kind-stats, gates --check/--require exit 2, JSON, stdin) ✓ 2026-08-03
91|84|- [x] json-to-env-vars : aplatit un JSON en lignes KEY=value (index/join/count pour arrays, --prefix, --export, --quote, --sort, --require, --check exit 2, JSON) ✓ 2026-08-03
92|85|- [x] log-extract-ips : extrait et compte les IPv4 des logs (validation octets, invalides optionnels, --min-count, --unique, gates --check/--require/--max-count exit 2, JSON) ✓ 2026-08-03
93|86|- [x] markdown-bold-usage : audit des marqueurs gras (** vs __, positions, fences et code inline ignorés, --require-style, --check, --max-underscore exit 2, JSON) ✓ 2026-08-03
94|87|- [x] line-swap-fields : échange deux champs par ligne (1-based, délimiteur custom, parse_intermixed_args, --strict exit 2, --report, JSON) ✓ 2026-08-03
95|88|
96|89|## Vague 660 — CLI Tools (entités HTML, MIME, ports, codes pays, unicode)
97|90|- [x] html-entity-encode : encode/décode les entités HTML (named/decimal/hex, --all, --ascii-only, --keep, --list positions, gates require-encoded/decoded/changes/entities exit 2, JSON, stdin, in-place, 28 tests) ✓ 2026-08-03
98|91|
99|92|## Vague 659 — CLI Tools (hosts, timestamps, chmod, Makefiles, anagrammes)
100|93|- [x] hosts-file-lint : lint /etc/hosts (invalid-ip, malformed-hostname, duplicate-entry/hostname avec shadowing, non-canonical-loopback, trailing-whitespace, missing-localhost v4/v6, --allow-duplicate-hostname, --ignore-missing-localhost, gates --check/--forbid/--max-findings exit 2, JSON, stdin, 17 tests) ✓ 2026-08-03
101|94|- [x] timestamp-to-date : convertit timestamps Unix ⇄ dates ISO 8601 (auto-détection précision s/ms/us/ns par magnitude, --unit forcé, --tz UTC/+HH:MM/IANA, styles iso/utc/date/full, batch args+stdin, gates --strict/--require-conversions exit 2, JSON, 15 tests) ✓ 2026-08-03
102|95|- [x] chmod-symbolic : évalue les expressions symboliques chmod (u+rwx,go-w,a=x, bits s/t/X, mode de base --from, chaîne rwx, --explain en clair, gate --expect exit 2, JSON, 22 tests) ✓ 2026-08-03
103|96|- [x] makefile-target-list : liste et audite les cibles d'un Makefile (kinds, .PHONY, commentaires ##, taille des recettes, gates CI exit 2, JSON, 19 tests) ✓ 2026-08-03
104|97|- [x] text-anagram-check : détecte les anagrammes (paires, groupes de classes, signatures triées, Unicode/casse normalisés, exit 2 pour les scripts, 16 tests) ✓ 2026-08-03
105|98|
106|99|
107|100|## Vague 658 — CLI Tools (env, Dockerfile, YAML, symlinks)
108|101|- [x] ini-key-sort : trie les clés de chaque section INI (ordre sections préservé, commentaires attachés aux clés, stdin) ✓ 2026-08-03
109|102|- [x] env-diff-check : compare les clés de .env contre une référence (.env.example), missing/extra/coverage, placeholders, valeurs jamais affichées par défaut, --allow-missing/--require-extras exit 2, JSON, stdin, 9 tests ✓ 2026-08-03
110|103|- [x] dockerfile-arg-default : audit ARG vs ${VAR} dans Dockerfiles (ARG inutilisés, usages non déclarés, ARG sans défaut, continuations \\, ENV-aware, gates --check/--max-unused-args/--require-declared/--require-defaults exit 2, JSON, 10 tests) ✓ 2026-08-03
111|104|- [x] yaml-key-list : liste les chemins de clés YAML jq-style (scanner stdlib par indentation, indices [n] pour séquences, --top-level/--max-depth/--leaves/--count, gates require/forbid/min/max-keys exit 2, JSON, stdin, 10 tests) ✓ 2026-08-03
112|105|- [x] symlink-target-check : audite les symlinks d'une arborescence (broken/loops ELOOP/escapes hors racine/absolus, tags, followlinks=False, gates --check/--max-broken/--forbid-absolute/--forbid-escapes exit 2, JSON, -q, 10 tests) ✓ 2026-08-03
113|106|
114|107|
115|108|## Vague 657 — CLI Tools (bases, logs, Docker, durées, gitignore, stack traces)
116|109|- [x] radix-convert : convertit des entiers entre bases 2..36 (auto 0x/0o/0b, pad, upper, batch stdin/fichier, --strict exit 2, JSON, 11 tests) ✓ 2026-08-03
117|110|- [x] stack-trace-summarize : groupe et classe les stack traces répétées d'un log (normalisation lignes/hex/ids, --top, --top-frames, gates --require-traces/--max-unique exit 2, JSON, 7 tests) ✓ 2026-08-03
118|111|- [x] dockerfile-lint-scan : lint statique de Dockerfile (latest, root, curl|sh, sudo, pip/apt non pinnés, 12 règles, --list-rules, --check/--max-findings exit 2, JSON, 11 tests) ✓ 2026-08-03
119|112|- [x] duration-round-normalize : normalise et arrondit des durées humaines (90min→1h30m, ISO 8601, round-to s/m/h/d up/down/nearest, formats compact/long/iso/seconds, --strict exit 2, JSON, 17 tests) ✓ 2026-08-03
120|113|- [x] log-level-report : compte les niveaux de logs d'un flux (syslog/logfmt/bracket/bare, aliases, barres ASCII, samples, erreurs ratio, gates --require-clean/--max-errors/--max-error-ratio/--require-min-level exit 2, JSON, 12 tests) ✓ 2026-08-03
121|114|- [x] gitignore-lint-check : lint .gitignore (duplicates, trailing-space, bare-star, negation-shadowed, CRLF, 8 règles, multi-fichiers, --check/--max-findings exit 2, JSON, 12 tests) ✓ 2026-08-03
122|115|
123|116|
124|117|## Vague 656 — CLI Tools (CSV, env, JSON, Markdown, lignes)
125|118|- [x] csv-sniff-dialect : détecte le dialecte CSV (délimiteur par score fréquence/consistance + sniffer stdlib fallback, quotechar/escape/doublequote/skipinitialspace, header, confidence, snippet csv.reader, gates --expect-* --min-confidence --check exit 2, JSON, 9 tests) ✓ 2026-08-03
126|119|- [x] env-shell-quote : quote les valeurs .env pour un source shell sûr (POSIX shlex/fish, valeurs sûres inchangées, export/commentaires/ordre préservés, --check/--require-changes/--max-changes exit 2, --list, JSON, 16 tests) ✓ 2026-08-03
127|120|- [x] json-stream-pretty : pretty-print JSON ou JSONL auto-détecté (indent/compact/sort-keys/ensure-ascii, JSONL forcé, lignes invalides tolérées ou --strict, --check/--require-change exit 2, JSON stderr, 14 tests) ✓ 2026-08-03
128|121|- [x] markdown-blank-run-report : rapporte/collapse les runs de lignes vides Markdown (LINE:LENGTH, fences ```/~~~ protégées, --fix --collapse-to, gates --check/--max-run/--max-runs/--max-blank-lines/--require-runs exit 2, JSON, 12 tests) ✓ 2026-08-03
129|122|- [x] line-repeat-count : compte les occurrences de chaque ligne sur tout l'input (uniq -c sans tri, ordres input/alpha/count/count-desc, filtres --duplicates-only/--unique-only/--min/--max-count, --ignore-case/--strip/--skip-empty, gates --check/--min-unique/--max-unique/--require-duplicates exit 2, JSON, 16 tests) ✓ 2026-08-03
130|123|
131|124|## Vague 655 — CLI Tools (Markdown, CSV, env, texte)
132|125|- [x] csv-stats-json : statistiques par colonne CSV en JSON (count/min/max/sum/mean/median/stdev/Q1/Q3, délimiteur auto, --columns, --sample, --round, gates --require-numeric/--require-min-rows exit 2, 8 tests) ✓ 2026-08-03
133|126|- [x] env-merge-files : fusionne N fichiers .env (first/last-wins, --export, --sort, commentaires préservés, doublons trackés, gates --fail-on-duplicate/--require-non-empty exit 2, JSON, 8 tests) ✓ 2026-08-03
134|127|- [x] line-number-lines : préfixe chaque ligne avec son numéro (start/step/width/sep, skip-blank, multi-fichiers + restart, --in-place, gates --max-lines/--require-lines exit 2, JSON, 7 tests) ✓ 2026-08-03
135|128|- [x] text-indent-normalize : convertit indentation espaces⇆tabs (--to-tabs/--to-spaces, --width, reste conservé, LF/CRLF préservées, --in-place, gates --check/--require-clean exit 2, JSON, 9 tests) ✓ 2026-08-03
136|129|- [x] markdown-toc-anchor-list : liste titres→anchors GitHub (ATX+setext, fences ignorées, slug dup suffix, --format tsv/json/toc, --min/--max-level, gates --require-headings/--strict-duplicates exit 2, JSON, 14 tests) ✓ 2026-08-03
137|130|
138|131|## Vague 654 — CLI Tools (JSONL, Markdown, env, lignes)
139|132|- [x] json-minify-lines : minifie chaque ligne JSONL (clés triées, --keep-order, --ensure-ascii, --skip-blank, --in-place, gates --check/--require-minified exit 2, JSON, 7 tests) ✓ 2026-08-03
140|133|- [x] jsonl-compact : normalise un flux JSONL (compact, tri clés, CRLF, --strip-blank, --in-place, gates --check/--require-canonical exit 2, JSON, 9 tests) ✓ 2026-08-03
141|134|- [x] markdown-list-renumber : renumérote les listes ordonnées Markdown (start/step, markers . ou ) préservés ou forcés, fences ignorées, --count dry-run, gates --check/--require-lists/--strict exit 2, JSON, 10 tests) ✓ 2026-08-03
142|135|- [x] env-expand-vars : expansion $VAR et ${VAR} dans .env (défauts :-, alt :+, requis :?, fallback env, --prefix, --mask, --no-env, gates --check exit 2, JSON, 13 tests) ✓ 2026-08-03
143|136|- [x] line-trim-whitespace : trim espaces début/fin de chaque ligne (LF/CRLF préservées, --leading/--trailing, --drop-empty, --in-place, gates --check/--require-clean exit 2, JSON, 8 tests) ✓ 2026-08-03
144|137|
145|138|## Vague 653 — CLI Tools (texte, Markdown, env, JSON, CSV)
146|139|- [x] text-soft-wrap-unwrap : joint les lignes soft-wrapped en paragraphes simples (listes/titres/fences/tables/code indenté préservés, --no-keep-structured, --in-place/-o, gates --check/--require-change/--max-joins exit 2, JSON stderr, stdin, 24 tests) ✓ 2026-08-03
147|140|- [x] markdown-image-path-validate : valide l'existence des images locales référencées en Markdown (remotes/data: skippés, fences ignorées, fragment/query strip + URL-decode, résolutions relatives, --allow-missing/--require-images/--max-missing exit 2, JSON rapports, 21 tests) ✓ 2026-08-03
148|141|- [x] env-line-dupe-check : détecte clés et lignes dupliquées dans un .env (export normalisé, --ignore-case, --keys-only/--lines-only, --max-key-dupes/--max-line-dupes/--require-duplicates exit 2, valeurs jamais exposées, JSON stderr, stdin, 18 tests) ✓ 2026-08-03
149|142|- [x] json-unicode-escape-normalize : normalize JSON entre Unicode littéral et échappements \uXXXX (--to-ascii/--to-unicode, fallback JSONL automatique, --indent 0 compact, --sort-keys, --in-place/-o, --check/--require-change exit 2, JSON stderr, 17 tests) ✓ 2026-08-03
150|143|- [x] csv-cell-quote-detect : rapporte le style de quoting par cellule (bare/quoted/escaped/malformed, scanner maison qui garde le tracking des octets, délimiteur sniffé, --list, --by-column, gates --max-malformed/--max-quoted-percent/--require-quoting exit 2, JSON, 17 tests) ✓ 2026-08-03
151|144|
152|145|## Vague 652 — CLI Tools (Markdown, texte, JSON, INI)
153|146|- [x] csv-quote-style-report : existant sur GitHub, dossier restauré depuis le remote (analyse du style de quoting CSV par cellule, délimiteur sniffé, 14 tests) ✓ 2026-08-03
154|147|- [x] markdown-heading-blank-line-check : lint les lignes vides autour des titres Markdown (ATX + setext, front matter YAML/TOML/JSON, fences ignorées, HR/--- non confondues, --require-blank-before/after N, --fix/--in-place/-o, gates --check/--min-headings/--max-violations/--require-violations exit 2, JSON stderr, stdin, 26 tests) ✓ 2026-08-03
155|148|- [x] text-trailing-spaces-report : rapport détaillé des espaces/tabulations trailing (kinds space/tab/mixed, max run + ligne, --list, --strip/--in-place/-o, multi-fichiers, CRLF préservées, gates --check/--max-dirty-lines/--max-trailing-chars/--require-dirty exit 2, JSON stderr, stdin, 23 tests) ✓ 2026-08-03
156|149|- [x] json-scalar-type-validate : valide les types scalaires JSON/JSONL contre un contrat PATH=TYPE (string/number/integer/float/boolean/null, chemins $ + a.b + [] + [N], --require/--forbid/--require-exists, --scalar-counts par chemin généralisé, gates --check/--max-violations/--require-violations exit 2, JSON stdout, stdin, 30 tests) ✓ 2026-08-03
157|150|- [x] ini-duplicate-key-check : détecte les clés dupliquées dans les sections INI (sections dupliquées, préambule global, séparateurs = et :, commentaires ;/#+inline, continuations indentées, --ignore-case/--values-too/--hide-values, gates --check/--max-duplicates/--require-duplicates exit 2, JSON stdout, stdin, 24 tests) ✓ 2026-08-03
158|151|
159|152|## Vague 651 — CLI Tools (Markdown, texte, lignes, JSON)
160|153|- [x] markdown-footnote-check : audite les footnotes Markdown (références [^id] sans définition, définitions inutilisées et doublons, fences/inline code ignorés, filtres --dangling-only/--unused-only, gates --check/--max-dangling/--max-unused/--require-footnotes exit 2, JSON stderr, stdin, 22 tests) ✓ 2026-08-03
161|154|- [x] text-number-normalize : normalise l'écriture des nombres dans un texte (séparateur décimal dot/comma, milliers space/comma/dot/apostrophe/underscore/none, --decimals N, signes préservés, parseur manuel tolérant 1,234/3,14/1.234.567/1.5e3, --in-place/-o, gates --check/--require-change/--max-changes exit 2, JSON stderr, stdin, 29 tests) ✓ 2026-08-03
162|155|- [x] line-number-strip : supprime ou ajoute les numéros de ligne en préfixe (styles colon/pipe/cat/paren/dot auto-détectés, --add avec --add-sep/--align/--start, --in-place/-o, gates --check/--require-numbered/--min-numbered exit 2, JSON stderr, stdin, 19 tests) ✓ 2026-08-03
163|156|- [x] json-types-report : rapport des types JSON par chemin jq-style ($, a.b, a[]) avec comptages et flags mixed (JSON/JSONL agrégés, --path/--mixed-only/--sort, gates --check/--require-type/--max-depth/--max-mixed exit 2, JSON stdout, stdin, 23 tests) ✓ 2026-08-03
164|157|
165|158|## Vague 650 — CLI Tools (CSV, Markdown, lignes, INI, texte)
166|159|- [x] csv-quoting-normalize : normalise le style de quoting CSV (minimal/all/non-numeric/none avec escaping, délimiteur sniffé, round-trip stdlib, --in-place/-o, gates --check/--require-change/--require-quoted/--require-unquoted exit 2, JSON stderr, stdin, 21 tests) ✓ 2026-08-03
167|160|- [x] markdown-inline-code-report : rapporte les spans de code inline Markdown (`code` et ``code``, line:col, tick count, fences/indented exclus, unclosed détectés, --list --unique --sort --multi-tick-only, gates --check/--require-any/--min-count/--max-count/--max-len/--require-unclosed exit 2, JSON stderr, stdin, 20 tests) ✓ 2026-08-03
168|161|- [x] line-collapse-blank : réduit les rafales de lignes vides à N max (cat -s configurable, mode --whitespace, CRLF préservées, --in-place/-o, gates --check/--require-change/--max-collapse exit 2, JSON stderr, stdin, 20 tests) ✓ 2026-08-03
169|162|- [x] ini-value-trim : trimme les espaces autour des valeurs INI (valeurs quotées intactes, commentaires inline préservés, séparateurs = et :, spacing key= conservé, --report, --in-place/-o, gates --check/--require-change/--require-dirty/--max-changes exit 2, JSON stderr, stdin, 17 tests) ✓ 2026-08-03
170|163|- [x] text-empty-line-count : compte les lignes vides et whitespace-only avec statistiques de runs (total/empty/ws-only/non-empty/longest run/ratio, multi-fichiers avec agrégats, --count-only, gates --check/--max/--min/--max-ratio/--max-run/--require-empty exit 2, JSON stderr, stdin, 16 tests) ✓ 2026-08-03
171|164|
172|165|## Vague 649 — CLI Tools (INI, CSV, Markdown, texte, lignes)
173|166|- [x] ini-value-dup-check : détecte les valeurs dupliquées entre clés/sections INI (commentaires inline stripping, --ignore-case/--trim, placeholders skippés, filtres --only-key/--ignore-key, --hide-values, gates --check/--max-dups/--max-occurrences/--require-dups exit 2, JSON, stdin, 23 tests) ✓ 2026-08-03
174|167|- [x] csv-row-field-count-check : valide que chaque ligne CSV a le bon nombre de champs (référence header ou --expect, délimiteur sniffé, quoted fields, histogramme, gates --max-bad/--min-ratio/--require-rows exit 2, JSON, -q, stdin, 19 tests) ✓ 2026-08-03
175|168|- [x] markdown-horizontal-rule-normalize : normalise les règles horizontales Markdown (---/***___, variantes espacées, fences/front matter/setext préservés, indent conservée, --style, --in-place/-o, gates --check/--require-change/--max-changes/--min-rules exit 2, JSON stderr, stdin, 22 tests) ✓ 2026-08-03
176|169|- [x] text-tab-to-space : existant sur GitHub, dossier restauré depuis le remote (déjà publié 2026-08-02, 8 tests) ✓ 2026-08-03
177|170|- [x] line-leading-zero-pad : padde les nombres des lignes avec des zéros (largeur fixe ou --auto-width, signe préservé, idempotent, --first, --pattern groupe num, CRLF préservées, gates --check/--require-change/--max-changes exit 2, JSON stderr, stdin, 23 tests) ✓ 2026-08-03
178|171|
179|172|## Vague 648 — CLI Tools (INI, CSV, sentence, Markdown, line)
180|173|- [x] ini-section-sort : trie alphabétiquement les sections d'un INI (section globale conservée en tête, corps de section préservé byte-for-byte, --ignore-case/--reverse, --check gate CI exit 2, --in-place/-o, JSON stderr, stdin, 19 tests) ✓ 2026-08-03
181|174|- [x] csv-header-case-normalize : normalise la casse des en-têtes CSV (snake/camel/pascal/kebab/lower/upper/title, splitting camel+snake+espaces, délimiteur auto, collisions détectées ou suffixées _2, --only/--check/--dry-run gates exit 2, JSON stderr, stdin, 23 tests) ✓ 2026-08-03
182|175|- [x] text-sentence-case-normalize : met une majuscule en tête de chaque phrase (protection abréviations Mr./e.g./etc. et décimales 3.14, --after-colon, --keep-caps pour acronymes, --check gate exit 2 CI, JSON stderr, stdin, 23 tests) ✓ 2026-08-03
183|176|- [x] markdown-italic-marker-normalize : convertit les italiques Markdown _text_ ↔ *text* (bold **/__ préservé, inline `_var_` et fences ```/~~~ protégés, échappés ignorés, --to underscore, --check gate exit 2 CI, JSON stderr, stdin, 19 tests) ✓ 2026-08-03
184|177|- [x] line-swap-case : inverse la casse de chaque lettre ligne par ligne (a⇄A idempotent, --lines 1,3,5-7 --invert, --word N 0-based, EOL LF/CRLF préservées, --require-change gate exit 2 CI, JSON stderr, stdin, 23 tests) ✓ 2026-08-03
185|178|
186|179|## Vague 647 — CLI Tools (INI, JSON, lignes, Markdown, texte)
187|180|- [x] ini-key-rename : renomme des clés INI globalement ou par section (règles [section:]old=new, fichier de règles, commentaires/quoting/ordre préservés, détection de collision, --in-place/-o, gates --check/--require-changed/--max-changes exit 2, JSON, stdin, 20 tests) ✓ 2026-08-03
188|181|- [x] json-sort-arrays-rec : trie récursivement les arrays d'un JSON/JSONL (scalaires mixtes null/bool/int/str sûrs, objets par --key avec absents en fin, --path a.b[2], --reverse, compact, gates --check/--require-changed/--min/--max-arrays exit 2, JSON, stdin, 22 tests) ✓ 2026-08-03
189|182|- [x] line-random-sample : échantillonne des lignes aléatoirement et reproductiblement (reservoir sampling --count N, Bernoulli --rate, --seed sha256-stable, ordre préservé ou --shuffle, gate --check sha256 exit 2 CI, --require-lines/--min/--max-sampled, JSON, stdin, 19 tests) ✓ 2026-08-03
190|183|- [x] markdown-list-depth-clamp : audite ou réduit l'imbrication des listes Markdown à une profondeur max (bullets + ordonnées, GCD step adaptatif 2/3 espaces, fences ignorées, markers préservés, --in-place/-o, gates --check/--require-changed/--max-changes exit 2, JSON, stdin, 19 tests) ✓ 2026-08-03
191|184|- [x] text-word-shift : décale cycliquement les mots de chaque ligne (gauche/droite, -n négatif inverse, --preserve-indent, identity no-op, gates --check/--require-changed/--min-words/--max-words exit 2, JSON, stdin, 18 tests) ✓ 2026-08-03
192|185|
193|186|
194|187|## Vague 646 — CLI Tools (JSON, lignes, Markdown, texte)
195|188|- [x] json-deep-flatten : aplatit un JSON imbriqué en paires chemin=valeur et reconstruit (jq-style a.b[2], conteneurs vides préservés, --unflatten, gates --check/--require-leaves/--max-leaves exit 2, JSON, stdin, 10 tests) ✓ 2026-08-03
196|189|- [x] line-reverse-lines : inverse l'ordre des lignes (tac portable, --chars graphemes combinants Unicode, --skip-blank, --in-place, gates --expect-lines/--max-lines/--check-reverse/--require-change exit 2, JSON, stdin, 12 tests) ✓ 2026-08-03
197|190|- [x] markdown-table-to-csv : convertit les tables Markdown en CSV (fences ignorées, \| déséchappé, stripping inline md, --table N/--combine, gates --require-tables/--max-tables/--expect-columns/--check-malformed exit 2, JSON, stdin, 10 tests) ✓ 2026-08-03
198|191|- [x] line-cut-fields : extrait/réordonne des champs par ligne (cut superset : ranges 1,3,5-7,-2,3-, --complement, --whitespace, --only-delimited, --unique, gates --expect-fields/--check-lines/--max-short/--require-delimiter exit 2, JSON, stdin, 16 tests) ✓ 2026-08-03
199|192|- [x] line-split-words : éclate les lignes en mots un par ligne (regex --split-on, --lower/--unique/--sort, filtres --min-len/--max-len/--keep-with, --number/prefixe/suffixe, --count-only, gates --expect-unique/--min-words/--max-words/--check-unique exit 2, JSON, stdin, 13 tests) ✓ 2026-08-03
200|193|
201|194|
202|195|## Vague 645 — CLI Tools (INI, texte, Markdown, JSON)
203|196|- [x] ini-quote-normalize : rapporte et normalise le style de quoting des valeurs INI (none/single/double, commentaires inline préservés, valeurs dangereuses gardées quotées, --in-place/-o, gates --check/--require-style/--max-changes exit 2, JSON, stdin, 19 tests) ✓ 2026-08-03
204|197|- [x] text-slash-escape : encode/décode les séquences backslash (\n \t \xHH \uXXXX \UXXXXXXXX, --keep-newlines, --escape-nonprint, --strict offsets, gates --check/--expect-changed/--expect-unchanged/--max-changes exit 2, JSON stderr, stdin, 25 tests) ✓ 2026-08-03
205|198|- [x] markdown-code-lang-report : rapporte les langages des fences Markdown (```/~~~, histogramme, untagged, unclosed avec lignes, --list, gates --allow/--forbid/--require-tagged/--max-untagged/--min-fences exit 2, JSON, stdin, 21 tests) ✓ 2026-08-03
206|199|- [x] json-minify-safe : minifie du JSON en validant d'abord (rien émis sur JSON invalide, mode --jsonl, --ascii/--sort-keys, --in-place sécurisé, stats bytes, gates --expect-savings/--min-savings/--max-output-bytes/--require-changed exit 2, JSON stderr, stdin, 20 tests) ✓ 2026-08-03
207|200|- [x] ini-list-keys : extrait le squelette d'un INI sans jamais exposer les valeurs (sections/clés avec lignes, globaux, doublons, modes --sections-only/--keys-only/--count, multi-fichiers, gates --require-section/--forbid-key/--max-keys/--min-sections/--check-empty/--strict exit 2, JSON, stdin, 24 tests) ✓ 2026-08-03
208|201|
209|202|
210|203|## Vague 644 — CLI Tools (Markdown, lignes, texte)
211|204|- [x] markdown-list-flatten : aplatit les listes Markdown imbriquées sur un seul niveau (bullets/ordered, --style, --strip-marker, fences préservées, gates --check/--max-depth exit 2, JSON, stdin, 14 tests) ✓ 2026-08-03
212|205|- [x] line-shuffle-sort : mélange aléatoire reproductible des lignes (--seed, --head échantillon, --unique, rapport stderr, gate --check ordre seedé exit 2, JSON, stdin, 10 tests) ✓ 2026-08-03
213|206|- [x] text-number-lines-file : préfixe chaque ligne de son numéro (nl portable, --start/--step/--width/--sep, --skip-blank, gates --check/--max-line exit 2, JSON stderr, stdin, 10 tests) ✓ 2026-08-03
214|207|
215|208|
216|209|
217|210|## Vague 643 — CLI Tools (INI, CSV, env, Markdown, texte)
218|211|- [x] ini-comment-align : aligne les commentaires trailing ;/# des fichiers INI sur une colonne commune (blocs séparés par sections/blancs/commentaires pleine ligne, --min-gap, --in-place/-o, gates --check/--require-dirty/--max-changes exit 2, JSON, stdin, 18 tests) ✓ 2026-08-03
219|212|- [x] csv-column-dedupe-rename : détecte et renomme les en-têtes CSV dupliqués (styles suffix/prefix/index-1, sniffing hors-quotes, quoting et whitespace des cellules préservés, --ignore-case, gates --check/--max-renames exit 2, JSON, stdin, 22 tests) ✓ 2026-08-03
220|213|- [x] env-order-sort : trie les clés d'un .env alphabétiquement (lignes structurelles commentaires/blancs/invalides figées, clés triées globalement autour, export toléré, --ignore-case, --desc, --in-place/-o, valeurs jamais exposées, gates --check/--max-moves exit 2, JSON, stdin, 20 tests) ✓ 2026-08-03
221|214|- [x] markdown-anchor-check : valide que les liens #fragment internes d'un Markdown pointent vers des titres existants (slugs GitHub ATX+setext, doublons suffixés -1, fences et inline code ignorés, line:col, --list-anchors, --allow-missing, gates --check/--max-dangling/--require-links exit 2, JSON, stdin, 21 tests) ✓ 2026-08-03
222|215|- [x] text-bom-detect : détecte et retire le BOM d'un fichier texte (UTF-8/16-LE/16-BE avec rapport, --strip, --add utf8, --in-place/-o, multi-fichiers, gates --check/--expect none|utf8|utf16-le|utf16-be exit 2, JSON, stdin, 19 tests) ✓ 2026-08-03
223|216|
224|217|
225|218|## Vague 642 — CLI Tools (Markdown, texte, env)
226|219|- [x] markdown-table-column-align : détecte et corrige la dérive des marqueurs d'alignement dans les tables Markdown (inférence type colonne, --expected NAME=ALIGN, --fix in-place, --check exit 2 CI, JSON, stdin, 7 tests) ✓ 2026-08-03
227|220|- [x] markdown-frontmatter-lint : valide les blocs front-matter YAML/TOML/JSON (--require KEY, --forbid KEY, --type KEY=TYPE, --regex KEY=PATTERN, --allow-absent, exit 2 CI, JSON, stdin, 12 tests) ✓ 2026-08-03
228|221|- [x] text-diacritics-strip : retire/remplace les diacritiques Unicode (NFKD, mapping compatibilité ß/æ/œ/ø/ð/þ, --keep-letters, --replace-compat, --check restes exit 2, --in-place, --report, JSON, stdin, 8 tests) ✓ 2026-08-03
229|222|- [x] env-diff-compare : compare deux .env (clés uniques chaque côté, valeurs changées, --mask-values pour logs, --ignore/--ignore-prefix, --check exit 2 CI, JSON, 7 tests) ✓ 2026-08-03
230|223|- [x] text-column-transpose : transpose lignes/colonnes de matrices texte (split whitespace ou --sep, --ragged-ok avec --fill, --out-sep, --require-input exit 2 CI, JSON, stdin, 7 tests) ✓ 2026-08-03
231|224|- [x] markdown-heading-ids : existant sur GitHub, dossier restauré depuis le remote (déjà publié 2026-08-02) ✓ 2026-08-03
232|225|
233|226|
234|227|## Vague 641 — CLI Tools (texte, env, Markdown, JSON)
235|228|- [x] text-whitespace-class : détecte et corrige les espacements Unicode exotiques (NBSP, ideographic, zero-width, line:col + codepoint + nom, --fix, gates --check/--max-exotic exit 2, JSON, stdin) ✓ 2026-08-03
236|229|- [x] env-multiline-check : audite les .env multilignes (valeurs quotées multi-lignes, quotes non fermées, continuations backslash, lignes orphelines, gates --check/--require-multiline/--max-issues exit 2, JSON, stdin) ✓ 2026-08-03
237|230|- [x] markdown-list-todo : audite les task lists Markdown (- [ ] / [x] / [~] / [>] / [-], fences ignorées, filtres --open-only/--done-only/--state, gates --check/--require-any/--max-open/--max-done exit 2, JSON, stdin) ✓ 2026-08-03
238|231|- [x] text-replace-many : applique N règles FIND=REPLACE (plain/regex avec backrefs, -i, fichier de règles, --in-place, --report, gates --require-change/--check-no-match exit 2, JSON, stdin) ✓ 2026-08-03
239|232|- [x] json-int-range : audite les magnitudes d'entiers JSON/JSONL (min/max par chemin jq, ranges uint32/int32/int53/int64/uint64, note bignum, gates --check/--require-range/--max-out-of-range exit 2, JSON) ✓ 2026-08-03
240|233|
241|234|
242|235|## Vague 640 — CLI Tools (Markdown, JSON, env, CSV)
243|236|- [x] markdown-image-alt-report : rapporte les images Markdown et audite leurs alt (fences/inline code ignorés, line:col, --fill placeholder, --missing-alt/--alts-only, gates --check/--max-missing/--require-any exit 2, JSON, stdin) ✓ 2026-08-03
244|237|- [x] json-float-precision-report : audite les floats d'un JSON/JSONL (chemin jq, digits décimaux/significatifs, notation scientifique, budget --max-significant, gates --check/--max-count/--require-any/--forbid-scientific exit 2, JSON) ✓ 2026-08-03
245|238|- [x] env-quote-normalize : rapporte et normalise le quoting des valeurs .env (none/single/double, escapes doubles quotes, commentaires/inline/export préservés, --style/--only-needed, --in-place/-o, gates --check/--require-style/--max-changes exit 2, JSON) ✓ 2026-08-03
246|239|- [x] csv-add-row-numbers : ajoute une colonne de numérotation à un CSV (nom/position first-last-N, --start/--step, --no-header, délimiteur sniffé, gates --check-empty/--expect-rows exit 2, JSON) ✓ 2026-08-03
247|240|- [x] markdown-def-list-check : rapporte et lint les listes de définitions Markdown (Terme / : définition, orphelins et définitions vides, fences ignorées, --terms-only/--orphans-only, gates --check/--require-any/--max-orphans/--max-empty exit 2, JSON) ✓ 2026-08-03
248|241|- [x] json-string-length-report : statistiques de longueur des strings par chemin jq d'un JSON/JSONL (min/max/mean/count, mesure chars ou bytes UTF-8, --show-longest, --sort path/max/mean/count, gates --min-len/--max-len/--require-path/--require-strings exit 2, JSON) ✓ 2026-08-03
249|242|
250|243|
251|244|## Vague 639 — CLI Tools (CSV, Markdown, env, JSON, texte)
252|245|- [x] csv-column-type-detect : infère le type de chaque colonne CSV (bool/int/float/date/datetime/email/url/uuid/string, délimiteur auto, distribution par type, gates --expect COL=TYPE/--check exit 2, JSON, stdin) ✓ 2026-08-03
253|246|- [x] markdown-list-indent-report : rapporte et lint l'indentation des listes Markdown (bullets + ordonnées, fences/inline code ignorés, depth par --step, sauts de niveau détectés, tabs expandés, gates --check/--max-depth exit 2, JSON, stdin) ✓ 2026-08-03
254|247|- [x] env-key-order-compare : compare l'ordre des clés de deux .env (clés manquantes chaque côté, clés déplacées, LCS + score de similarité, export toléré, valeurs jamais lues, gates --check/--ignore-missing exit 2, JSON, stdin) ✓ 2026-08-03
255|248|- [x] text-word-frequency-rank : classe les mots d'un texte par fréquence (rangs partagés en cas d'égalité, ordre alpha dans un rang, Unicode, --top/--min-count, gates --require/--expect-top/--max-unique exit 2, JSON, stdin) ✓ 2026-08-03
256|249|- [x] json-keys-case-report : classifie le style de casse de chaque clé JSON (camel/pascal/snake/kebab/upper_snake/flat/other, chemins jq, distribution, gates --check mixed/--require/--forbid exit 2, JSON, stdin) ✓ 2026-08-03
257|250|
258|251|
259|252|## Vague 638 — CLI Tools (CSV, Markdown, URL, JSON)
260|253|- [x] csv-empty-cell-report : rapporte les cellules vides d'un CSV (par colonne + total, --whitespace, --column ciblé, --row-details, délimiteur sniffé, gates --check/--max/--require-any/--require-column-nonempty exit 2, JSON, stdin) ✓ 2026-08-03
261|254|- [x] markdown-strikethrough-extract : extrait les segments barrés ~~texte~~ (fences, inline code et échappés ignorés, line:col, --unique/--count/--text-only/--strip, gates --check/--require-min/--max-count exit 2, JSON, stdin) ✓ 2026-08-03
262|255|- [x] url-subdomain-extract : extrait les sous-domaines d'URLs (TLDs composés co.uk/com.au gérés, --base, --depth, --with-url, --unique, IPv4/6 skippés, gates --check/--require-any/--require/--forbid exit 2, JSON, stdin) ✓ 2026-08-03
263|256|- [x] json-array-of-objects-report : stats des arrays d'objets JSON/JSONL (chemins jq, union/intersection de clés, coverage par clé, matrice de types, --uniform-only, --path, --sort length, gates --check/--require-array/--require-path/--min/--max-arrays exit 2, JSON) ✓ 2026-08-03
264|257|- [x] csv-line-ending-detect : détecte/convertit les fins de ligne LF/CRLF/CR (binaire-safe, mixed détaillé, final-newline manquant, --to + --in-place/-o, gates --style/--check/--require-final-newline exit 2, JSON, stdin) ✓ 2026-08-03
265|258|
266|259|
267|260|## Vague 637 — CLI Tools (CSV, Markdown, JSON, env, texte)
268|261|- [x] csv-column-move : déplace/réordonne les colonnes d'un CSV (--move COL:first|last|N|before:|after:, --order complet, délimiteur auto, gates --check/--require-changed/--require-unchanged exit 2, JSON, stdin) ✓ 2026-08-03
269|262|- [x] markdown-list-marker-normalize : uniformise les marqueurs de listes Markdown (bullets -/*/+, délimiteurs ordonnés . ou ), --renumber par niveau, fences préservées, --in-place, gates --check/--require-*/--max-changes exit 2, JSON) ✓ 2026-08-03
270|263|- [x] json-bigint-report : rapporte les entiers dépassant une borne sûre (défaut 2**53-1 JS safe, chemins jq, --limit, --count/--paths-only, --sort value, gates --check/--max/--require-any/--require-none exit 2, JSON) ✓ 2026-08-03
271|264|- [x] env-value-redact : masque les valeurs sensibles d'un .env (PASSWORD/SECRET/TOKEN/API_KEY..., quotes et commentaires préservés, placeholders tolérés, --style partial --keep, --allow, --in-place, gates --check/--require-redacted/--require-clean/--max-exposed exit 2, JSON) ✓ 2026-08-03
272|265|- [x] text-line-truncate : tronque les lignes à une largeur fixe (caractères Unicode, tab expansion, marqueur ... dans le budget, --side right/left/center, --no-marker, --in-place, gates --check/--max-truncated/--require-* exit 2, JSON, -q) ✓ 2026-08-03
273|266|
274|267|
275|268|## Vague 636 — CLI Tools (CSV, JSON, texte, Markdown, env)
276|269|- [x] csv-to-ndjson-config : convertit CSV en NDJSON selon schema declaratif JSON/TOML (selection/renommage columns, casts bool/int/float/null, decimal-comma, gates check/require-records/max-badrows exit 2, JSON, stdin, 18 tests) ✓ 2026-08-03
277|270|- [x] json-array-index-report : rapport par index pour chaque array JSON (types/count/min/max/avg par index, jq paths, --path, gates check/require-array/max-index/no-empty exit 2, JSON, stdin, 18 tests) ✓ 2026-08-03
278|271|- [x] text-slug-batch : genere des slugs URL-safe en lot (NFKD transliteration, separator custom, max-length, dedup suffixes, --pairs, gates check/require-change/unchanged/unique exit 2, JSON, stdin, 28 tests) ✓ 2026-08-03
279|272|- [x] markdown-todo-to-github-issue : extrait les - [ ] pending et genere des gh issue create (repo/label/assignee/milestone/title-prefix/body-template, gates check/require-pending/min-pending/require-done exit 2, JSON, stdin, 19 tests) ✓ 2026-08-03
280|273|- [x] env-var-expand-tester : teste l'expansion de variables dans des templates (syntaxe $VAR/${VAR}:-default/:=/:/?:+, .env, -D inline, show-resolved/unresolved, gates check/require-expanded/require-unresolved exit 2, JSON, stdin, 26 tests) ✓ 2026-08-03
281|274|
282|275|
283|276|## Vague 635 - CLI Tools (Markdown, JSON, env, texte, URL)
284|277|- [x] markdown-fence-indent-strip : retire une indentation commune des fences et de leur contenu (fences ``` et ~~~, nested lists 0-7 espaces, longest-common, info strings preservees, --in-place/-o, gates check/require-dirty/require-clean/max-shifted exit 2, JSON, 18 tests) OK 2026-08-03
285|278|- [x] json-key-sort-rec : trie recursivement les cles de tous les objets d'un JSON/JSONL (ordre alphabetique, --ignore-case, arrays preserves, --compact, --in-place, gates check/require-changed/require-unchanged exit 2, JSON, 16 tests) OK 2026-08-03
286|279|- [x] env-key-validate : valide les noms de cles d'un .env (schemes UPPER_SNAKE/camel/snake ou custom regex, doublons detectes, export tolere, --allow, gates check/require-valid/min/max-invalid/no-duplicates exit 2, JSON, 19 tests) OK 2026-08-03
287|280|- [x] text-tab2space : convertit tabs en espaces et reverse (tab-stops 4/8, --to-tabs compresse runs alignes, --leading-only, report ligne:shifted, --in-place/-o, gates check/require-clean/require-dirty/max-converted exit 2, JSON, 22 tests) OK 2026-08-03
288|281|- [x] url-query-sort : trie les parametres de query string des URLs (par cle puis valeur, parsing decode-safe, --key-subset, --ignore-case, fragments/ports preserves, gates check/require-sorted/max-urls exit 2, JSON, 19 tests) OK 2026-08-03
289|282|
290|283|
291|284|## Vague 634 — CLI Tools (INI, texte, CSV, Markdown)
292|285|- [x] ini-to-properties : convertit INI <-> Java .properties (round-trip, globs, --from-properties, --on-dupe rename/skip/error, --separator custom, gates check exit 2, JSON, 16 tests) ✓ 2026-08-03
293|286|- [x] text-alt-case : alterne la casse des lettres SpOnGe CaSe (modes lower/upper-first, --random+--seed déterministe, Unicode-aware, --skip-digits/--punct-counts, --continuous/--reset-per-line, gates check exit 2, JSON, 18 tests) ✓ 2026-08-03
294|287|- [x] csv-repeat-rows : duplique les lignes CSV N fois (colonne compteur --count-column nom/index ou --times global, délimiteur sniffé, --keep-count-column, --max-repeats clamp, --error-on-invalid, gates check-empty/error exit 2, JSON, 19 tests) ✓ 2026-08-03
295|288|- [x] ini-remove-section : supprime/garde des sections INI par nom ou glob (-s cache -s 'tmp-*', --keep inversé, préserve global/commentaires/blanks, collapses blank runs, gates check/allow-noop exit 2, JSON, 14 tests) ✓ 2026-08-03
296|289|- [x] markdown-hr-normalize : normalise les règles horizontales Markdown vers --- (ou ***, ___, spaced variants, fences et setext-underlines préservées, CRLF ok, gates check exit 2, JSON, 15 tests) ✓ 2026-08-03
297|290|
298|291|## Vague 633 — CLI Tools (texte, Unicode, CSV, JSON, lignes)
299|292|- [x] text-morse-codec : encode/decode du Morse international (symboles --dot/--dash custom, prosign SOS, --auto, --strict, gates --check round-trip/--require-encoded/--expect-encoded/--expect-unknown exit 2, JSON, 20 tests) ✓ 2026-08-03
300|293|- [x] text-homoglyph-detect : détecte les caractères confusables (cyrillic/greek/fullwidth/math-bold, line:col + codepoint + name, --blocks/--sanitize/--unique, gates check/require/min/max/expect-char/forbid-block exit 2, JSON, 16 tests) ✓ 2026-08-03
301|294|- [x] csv-row-select-regex : sélectionne les lignes CSV par regex sur champs (colonne nom/#index, AND multi-matchers, --any-column, --full-row, -i/-v, délimiteur sniffé, --count, gates check/min/max/expect-matches exit 2, JSON, 18 tests) ✓ 2026-08-03
302|295|- [x] json-null-strip : retire récursivement les valeurs null des documents JSON/JSONL (--also empty-string/array/object, --prune-empty, --keep-root, --compact, gates check/require-changed/unchanged/expect/min/max-stripped exit 2, JSON, 16 tests) ✓ 2026-08-03
303|296|- [x] line-duplicate-adjacent-remove : supprime les lignes dupliquées adjacentes (uniq streamé, -i/--trim, --count/--duplicates-only/--unique-only, CRLF préservées, --report-only, gates check/require/expect/min/max-duplicates/expect-lines exit 2, JSON, 19 tests) ✓ 2026-08-03
304|297|
305|298|## Vague 632 — CLI Tools (texte, hex, lignes, emoji)
306|299|- [x] text-acronym-maker : génère des acronymes depuis du texte (stopwords EN/FR, --title-case, gates --check/--require-min-length/--require-max-length exit 2, JSON) ✓ 2026-08-03
307|300|- [x] hex-codec : encode/decode hex (--upper, --separator, --group, --decode, --auto, gates --check/--require-encoded exit 2, JSON) ✓ 2026-08-03
308|301|- [x] text-word-reverse : inverse mots/lettres par ligne (3 modes, whitespace/ponctuation préservés optionnel, gates --check/--require-change/--require-unchanged exit 2, JSON) ✓ 2026-08-03
309|302|- [x] line-interleave : entrelace N fichiers en round-robin ou blocs (--drop-extras, --gap, --split-stdin, gates --check/--require-lines exit 2, JSON) ✓ 2026-08-03
310|303|- [x] text-emoji-strip : détecte/liste/compte/strip emoji (Catégories Unicode complètes, --replace, gates --check/--require-found/--max-emoji exit 2, JSON) ✓ 2026-08-03
311|304|
312|305|## Vague 631 — CLI Tools (texte, CSV, JSON, lignes, gitignore)
313|306|- [x] text-letter-frequency-csv : fréquence des caractères Unicode (casefold, --include-digits/space/punct, CSV+JSON, gates require/forbid-letter/min-max-unique exit 2, 12 tests) ✓ 2026-08-03
314|307|- [x] csv-column-pick-list : extrait les valeurs de colonnes CSV (nom ou #index, délimiteur sniffé, multi-colonnes --join, --unique/--sort/--ignore-case, --skip-empty, gates min/max/require/forbid-value exit 2, JSON, 13 tests) ✓ 2026-08-03
315|308|- [x] json-single-quote : convertit JSON vers notation Python single-quote (True/False/None) et inversement via ast.literal_eval (indent/compact/sort/trailing-comma, chemins dotted, gates require-key/check exit 2, 13 tests) ✓ 2026-08-03
316|309|- [x] line-suffix-strip : retire des suffixes littéraux/regex en fin de ligne (longest-first, EOL CRLF préservées, --drop-empty, --in-place/-o, --check exit 2, JSON, 11 tests) ✓ 2026-08-03
317|310|- [x] gitignore-audit : audit d'un .gitignore (duplicates, case-duplicates, trailing-space, double-star-only, redundant sous-dossiers, negation-trap, --strict, --fix-dups, gates no-duplicates/no-redundant/no-negation-traps/max-issues exit 2, JSON, 13 tests) ✓ 2026-08-03
318|311|
319|312|## Vague 630 — CLI Tools (JSON, texte, lignes, Markdown, INI)
320|313|- [x] json-pretty-compact : pretty-print/compacte des documents JSON et JSONL (validation, --indent, 12 tests) ✓ 2026-08-03
321|314|- [x] ini-to-env : convertit des fichiers INI en .env (sections préfixées, --flat/--prefix/--upper, Go) ✓ 2026-08-03
322|315|- [x] text-base64-codec : encode/decode Base64/Base64URL/Base32 (auto-détection, --wrap, --no-padding, check exit 2, JSON, 18 tests) ✓ 2026-08-03
323|316|- [x] text-slug-words : génère des slugs URL-friendly (translittération accents, stopwords, --unique suffixes, --check exit 2, JSON, 20 tests) ✓ 2026-08-03
324|317|- [x] line-length-histogram : distribution des longueurs de lignes (buckets, barres ASCII, stats, gate --max-length exit 2, JSON, 14 tests) ✓ 2026-08-03
325|318|- [x] markdown-strip-links : retire la syntaxe des liens Markdown en gardant le texte (inline/ref/images/autolinks, fences préservées, --in-place, --check exit 2, JSON, 20 tests) ✓ 2026-08-03
326|319|
327|320|## Vague 629 — CLI Tools (JSON, env, CSV, lignes, Markdown)
328|321|- [x] json-object-merge : fusion profonde de documents JSON (récursif, --arrays replace/concat, --compact, gates check/require-changed/require-key/min/max-keys exit 2, JSON, 20 tests) ✓ 2026-08-03
329|322|- [x] env-export-prefix : ajoute/retire le préfixe 'export' des lignes .env (commentaires/indent/quotes préservés, --add/--strip/--in-place, gates check/require-export/forbid-export/min-exported/max-plain exit 2, JSON, 16 tests) ✓ 2026-08-03
330|323|- [x] csv-quoted-fields-report : rapport des champs quotés d'un CSV (parse caractère par caractère, multi-ligne/échappements, délimiteur auto, par colonne + total, gates check/require-quoted/require-unquoted/min/max-quoted exit 2, JSON, 18 tests) ✓ 2026-08-03
331|324|- [x] line-number-add : préfixe chaque ligne de son numéro (--start/--width zero-pad/--separator, --skip-blank/--blank-placeholder, détection déjà-numéroté, gates check/expect-lines/min/max-lines exit 2, JSON, 16 tests) ✓ 2026-08-03
332|325|- [x] markdown-link-domain-report : rapport des domaines des liens Markdown (inline/ref/autolinks, fences+inline code ignorés, allow/forbid wildcards, gates check/require-domain/min/max-domains exit 2, JSON, 13 tests) ✓ 2026-08-03
333|326|
334|327|## Vague 628 — CLI Tools (Markdown, JSON, env, lignes, URL)
335|328|- [x] markdown-heading-level-shift : déplace les niveaux d'en-têtes ATX (# → ##..., promote/demote, clamp 1..6 avec comptage, fences ignorées, --by/--up/--down, --in-place/--output, gates check/require-changed/require-clamped/max-headings exit 2, JSON, 15 tests) ✓ 2026-08-03
336|329|- [x] json-string-concat : concatène les valeurs string d'un JSON/JSONL avec séparateur configurable (walk récursif, --key à toute profondeur, --path a.b[0], --scalars/--include-keys/--per-doc, gates require-non-empty/require-match/max-strings exit 2, JSON, 20 tests) ✓ 2026-08-03
337|330|- [x] env-url-extract : extrait et valide les URLs des valeurs .env (scheme/host/port/path, IPv6, warnings userinfo/host manquant/port par défaut redondant, --values/--schemes/--key, gates require-url/require-scheme/forbid-userinfo/max-warnings/check exit 2, JSON, 18 tests) ✓ 2026-08-03
338|331|- [x] line-rstrip-whitespace : rapporte/supprime les espaces/tabulations en fin de ligne (kinds space/tab/mixed, --strip/--in-place/-o, --kind filtre, EOL préservées, gates check/require-dirty/max-lines/max-chars exit 2, JSON, 17 tests) ✓ 2026-08-03
339|332|- [x] url-punycode-convert : convertit les IDN d'URLs vers/depuis punycode (encode/decode par label, userinfo/port/path/fragment préservés, IPv6 ignoré, --host-only, gates require-changed/require-unchanged/check exit 2, JSON, 18 tests) ✓ 2026-08-03
340|333|
341|334|## Vague 627 — CLI Tools (CSV, JSON, env, Markdown, texte)
342|335|- [x] csv-validate-records : valide des règles par champ sur chaque enregistrement CSV (int/float/email/url/bool/notempty/empty/len:N-M/regex/in:, colonne par nom ou #index, délimiteur sniffé, --check/--strict/--require-invalid/--min/max-violations gates exit 2, JSON, 19 tests) ✓ 2026-08-03
343|336|- [x] json-keys-type-map : cartographie le type de chaque clé JSON à travers les enregistrements (object/array/JSONL, chemins imbriqués + [], présence par clé racine, --path, gates --check/--require-key/--min-presence exit 2, JSON, 19 tests) ✓ 2026-08-03
344|337|- [x] env-required-check : vérifie un .env contre un contrat de clés requises (--require/--require-file depuis .env.example, --forbid, --no-empty/--allow-empty, --no-placeholder/--strict, --unexpected, JSON, 18 tests) ✓ 2026-08-03
345|338|- [x] markdown-bold-extract : extrait les segments gras **x**/__x__ (fences, inline code, échappés ignorés, line:col+style, non-fermés signalés, --unique/--count/--text-only, gates check/require-min/max-count/require-style/forbid-style/require-none exit 2, JSON, 21 tests) ✓ 2026-08-03
346|339|- [x] text-ngram-freq : fréquences de n-grammes de mots ou caractères (Unicode, --documents avec DF, multi-fichiers, --top/--min-count/--sort, sorties table/CSV/JSON, gates require/forbid-ngram/max-unique exit 2, 20 tests) ✓ 2026-08-03
347|340|
348|341|## Vague 626 — CLI Tools (texte, CSV, JSON, env, Markdown)
349|342|- [x] text-word-order-reverse : inverse l'ordre des mots de chaque ligne (séparateur regex custom, --keep-blanks round-trip exact, --reverse-lines, --skip-blank, --in-place, gates check/require-changed/min/max-changed exit 2, JSON, 17 tests) ✓ 2026-08-03
350|343|- [x] csv-distinct-per-column : compte les valeurs distinctes par colonne CSV (délimiteur sniffé, flags unique/constant, --ignore-case/--trim/--skip-empty, -c colonnes nom/index, --sort count/ratio, --top, gates min/max-distinct/require-unique/require-constant exit 2, JSON, 21 tests) ✓ 2026-08-03
351|344|- [x] json-numeric-sum-by-key : somme les valeurs numériques d'un JSON/JSONL regroupées par nom de clé (récursif, booléens exclus, --group-by dotted path sur docs/arrays racine, -k filtre, --sort/--ndigits, gates expect-sum/require-key/min/max-total/require-numeric exit 2, JSON, 19 tests) ✓ 2026-08-03
352|345|- [x] env-default-comment : génère un .env.example où chaque valeur devient un commentaire '# default: ...' (secrets TOKEN/SECRET/PASSWORD/KEY auto-redactés, --extra-sensitive, --keep-value, --required, --check-safe avec --no-redact exit 2, gates require-key/min-keys, JSON, 17 tests) ✓ 2026-08-03
353|346|- [x] markdown-list-item-count : compte les items de listes Markdown par section (ATX+Setext, preamble, ul/ol/task/done breakdown, fences ignorées, --section/--drop-empty/--types, gates require-lists/min/max-items/require-section exit 2, JSON, 18 tests) ✓ 2026-08-03
354|347|
355|348|## Vague 625 — CLI Tools (CSV, Markdown, lignes, env, INI)
356|349|- [x] csv-column-sort : trie les lignes d'un CSV par colonnes (nom/index, multi-clés stable, :n:numérique :d:descendant, délimiteur sniffé, --no-header, --check/--require-numeric/--require-unique/--min/max-rows exit 2, JSON, 26 tests) ✓ 2026-08-03
357|350|- [x] markdown-italic-text-extract : extrait les segments italiques (*x* et _x_) d'un Markdown (fences, inline code, gras, échappés ignorés, line:col+style, --unique/--count/--text-only, gates min/max-count/require-style/require-text/require-none exit 2, JSON, 23 tests) ✓ 2026-08-03
358|351|- [x] line-duplicate-remove : supprime les lignes dupliquées en préservant l'ordre (uniq ordonné, -i/--trim/--collapse, --skip-blank, --duplicates-only/--count, --in-place, gates check/require-duplicates/min/max-removed/unique/expect-lines exit 2, JSON, 22 tests) ✓ 2026-08-03
359|352|- [x] env-key-case-normalize : normalise la casse des clés .env (upper/lower/snake-upper/snake-lower, splitting camel/acronymes, valeurs/quotes/export/comments préservés, collisions détectées, --check/--dry-run/--in-place, gates require-changed/unchanged exit 2, JSON, 23 tests) ✓ 2026-08-03
360|353|- [x] ini-value-type-detect : détecte le type apparent des valeurs INI (bool/int/float/empty/list2+/path/string, quotes tolérées, par section, conflits de type inter-sections, gates expect-key/require/forbid-type/no-conflicts exit 2, JSON, 24 tests) ✓ 2026-08-03
361|354|
362|355|## Vague 624 — CLI Tools (JSON, lignes, Markdown)
363|356|- [x] json-array-items : extrait les items d'un array JSON racine (JSONL auto, --index avec offsets négatifs, --unwrap single-key, --pretty, gates min/max/require-array/non-empty/scalars-only exit 2, JSON, 17 tests) ✓ 2026-08-03
364|357|- [x] line-strip-suffix : retire un suffixe (ou une extension de fichier) de chaque ligne (--suffix, --ext, -i, --report/--count, gates require-match/min/max/require-none/expect exit 2, JSON, 17 tests) ✓ 2026-08-03
365|358|- [x] markdown-bare-url-check : détecte les URLs nues dans un Markdown (fences, inline code, liens, images, autolinks, HTML ignorés, line:col, --unique, gates max-bare/require-none/expect exit 2, JSON, 15 tests) ✓ 2026-08-03
366|359|
367|360|## Vague 623 — CLI Tools (CSV, URL, JSON, Markdown, texte)
368|361|- [x] csv-duplicate-row-find : trouve et rapporte les lignes dupliquées d'un CSV (comparaison exacte ou par clés --key nom/index, --ignore-case/--trim, --dedupe garde la 1re occurrence, delimiter sniffé, gates check/min/max/require-any/require-none exit 2, JSON, 15 tests) ✓ 2026-08-03
369|362|- [x] url-fragment-extract : extrait les fragments #anchor des URLs (bare-text scan via regex inline, --decode percent, empty # distingué, scroll-to-text ':~:' directives, --unique/--count/--with-url, gates check/min/max/require/forbid exit 2, JSON, 14 tests) ✓ 2026-08-03
370|363|- [x] json-array-length-report : rapporte la longueur de chaque tableau JSON avec chemins jq-style (JSONL, --include-empty, --sort path/length/desc, --stats, gates min-len/max-len/max-arrays/require-non-empty/require-path exit 2, JSON, 15 tests) ✓ 2026-08-03
371|364|- [x] markdown-heading-word-count : compte les mots par section d'en-tête Markdown (ATX + Setext, fences/images/inline code exclus, preamble, --min/max-level, gates check/min-words/max-words/require-uniform/expect-sections exit 2, JSON, 14 tests) ✓ 2026-08-03
372|365|- [x] text-long-word-list : liste les mots les plus longs d'un texte (seuil --min-length défaut 10, --top/--count/--position/--alpha/--ascending, accents+diacritics folding, gates check/min-count/max-count/max-length/require/forbid exit 2, JSON, 16 tests) ✓ 2026-08-03
373|366|
374|367|## Vague 622 — CLI Tools (env, Markdown, JSON, URL, texte)
375|368|- [x] env-whitespace-trim : détecte/corrige les espaces autour des valeurs .env (space-after-eq/trailing/around-quoted, quotes préservées, --write/--check exit 2, JSON, stdin, 18 tests) ✓ 2026-08-03
376|369|- [x] markdown-horizontal-rule-report : rapport/normalise les séparateurs horizontaux Markdown (dash/star/underscore, spaced variants, fences skip, mixed=invalid, --normalize CHR --in-place, gates --check/--style exit 2, JSON, 12 tests) ✓ 2026-08-03
377|370|- [x] json-comment-strip : supprime // et /* */ des JSONC (strings protégées, newlines préservées dans blocks, --check/--lint gates exit 2, --stats/--json, 12 tests) ✓ 2026-08-03
378|371|- [x] url-userinfo-extract : extrait user/pass des URLs (password jamais brut par défaut: len+sha256(8), --show opt-in, URL sanitizée, bare-text regex, gates require-none/require-passwordless/min/max exit 2, JSON, 13 tests) ✓ 2026-08-03
379|372|- [x] text-zero-width-chars : détecte/supprime les caractères invisibles Unicode (ZWSP/ZWJ/bidi/BOM/soft-hyphen, 20+ codepoints, line:col+nom, --strip/--in-place, --allow zwsp|zwj|bidi|bom aliases, --check exit 2, JSON, 10 tests) ✓ 2026-08-03
380|373|
381|374|## Vague 621 — CLI Tools (texte, URL, Markdown, JSON, lignes)
382|375|- [x] text-tab-space-mix : detecte/corrige le melange tabs/espaces dans l'indentation (rapport/mixed lines, --to tabs|spaces + --width, --in-place, gates --check exit 2, JSON) ✓ 2026-08-03
383|376|- [x] url-host-extract : extrait et rapporte les hotes d'URLs (domaine/ipv4/ipv6, --unique/--count/--with-port/--family, gates require/forbid/check exit 2, JSON) ✓ 2026-08-03
384|377|- [x] markdown-image-alt-check : verifie les alt des images Markdown (vides/generiques, fences ignorees, gates --check/--max/--min-ratio exit 2, JSON) ✓ 2026-08-03
385|378|- [x] json-numeric-precision-report : rapport de precision des nombres JSON (chemins jq-style, histogramme decimales, gates --max-decimals/--require-nonzero/--check exit 2, JSON) ✓ 2026-08-03
386|379|- [x] line-indent-depth-report : niveaux d'indentation ligne par ligne (histogramme, --level, gates --max-depth/--require-nested exit 2, JSON) ✓ 2026-08-03
387|380|- [x] text-hex-color-extract : extrait/normalise les couleurs hex #rgb/#rrggbb/#rrggbbaa (--unique/--count/--with-position, gates --require/--check/--min exit 2, JSON) ✓ 2026-08-03
388|381|
389|382|## Vague 620 — CLI Tools (texte)
390|383|- [x] text-detect-natural-language : détecte la langue naturelle d'un texte (en/fr/es/de/it/pt/nl, stopwords pondérés par exclusivité + chars/sequences typiques, confidence, --per-line, --languages, gates expect/min-words/min-confidence exit 2, JSON, 17 tests) ✓ 2026-08-03
391|384|- [x] markdown-checklist-progress : calcule le pourcentage d'avancement des task lists Markdown (bullets - * +, nesting, case-insensitive X, barre ASCII/--width, badge shields, gates min-percent/expect exit 2, JSON, 14 tests) ✓ 2026-08-03
392|385|- [x] json-pointer-delete : supprime des noeuds JSON via des pointers RFC 6901 (multi-pointers, ~0/~1 escapes, arrays, reset root avec "", --strict/--require-changed gates exit 2, report JSON stderr, 16 tests) ✓ 2026-08-03
393|386|- [x] env-expand-paths : expande ~ et $VAR dans les valeurs path-like d'un .env (suffixes PATH/DIR/FILE/HOME/ROOT/BASE, --key-pattern custom, quotes/export preserves, --in-place/--output, gates check/require-expanded/require-key/require-no-undefined exit 2, JSON, 17 tests) ✓ 2026-08-03
394|387|
395|388|## Vague 619 — CLI Tools (texte, JSON, Markdown, env, URL, lignes)
396|389|- [x] text-palindrome-detect : détecte les palindromes (mode lignes ou mots, normalisation case/alnum/diacritics, --min-length, gates check/require/min/max-count/expect exit 2, JSON, tests) ✓ 2026-08-03
397|390|- [x] json-value-type-matrix : matrice chemin → types observés (jq-style paths, arrays[], polymorphic detect, --poly-only, gates check/require-type/forbid-type/min/max-paths exit 2, JSON, tests) ✓ 2026-08-03
398|391|- [x] markdown-table-align-check : vérifie/corrige l'alignement des tables Markdown (cell-count, --strict widths, --fix/--in-place, fences ignorées, gates check/max-issues exit 2, JSON, tests) ✓ 2026-08-03
399|392|- [x] env-shell-export-format : convertit .env en exports shell (posix/fish, quoting sûr, merge multi-fichiers, --prefix/--strip-prefix, gates check/strict-keys/require/forbid-key exit 2, JSON, tests) ✓ 2026-08-03
400|393|- [x] url-path-segment-stats : stats des segments de path d'URLs (depth distribution, top segments, numeric IDs, empty/trailing slash, gates max-depth/check/require-numeric/forbid-empty exit 2, JSON, tests) ✓ 2026-08-03
401|394|- [x] line-first-char-stats : distribution du premier caractère de chaque ligne (classes space/tab/alpha/digit/punct/blank, mixed-indent --check, gates require/forbid-class/char/max-classes exit 2, JSON, tests) ✓ 2026-08-03
402|395|
403|396|## Vague 618 — CLI Tools (texte, INI, URL, Markdown, env)
404|397|- [x] text-word-frequency-report : fréquence des mots (counts, ratios, density, gates require/forbid/min/max-count/unique/expect/density exit 2, JSON) ✓ 2026-08-03
405|398|- [x] ini-merge-files : fusionne plusieurs INI (precedence first|last, DEFAULT optionnel, conflict report JSON, --check, gates require/max-conflicts exit 2) ✓ 2026-08-03
406|399|- [x] url-scheme-swap : remplace le scheme d'URLs (--adjust-port mappe vieux→nouveau default, --strip-default-port, --from-scheme filtre, IPv6, gates check/require-changed/require-unchanged exit 2, JSON) ✓ 2026-08-03
407|400|- [x] markdown-link-protocol-stats : distribution des protocoles dans les liens Markdown (inline/ref/autolink/image, fences+front-matter+comments skippés, --bars, --per-kind, gates require/forbid-scheme/min/max-count/check exit 2, JSON) ✓ 2026-08-03
408|401|- [x] text-paragraph-count-report : compte paragraphes et phrases (splitter abréviations/décimales), stats avg/median, histogram, gates min/max-paragraphs/sentences/require-avg-words exit 2, JSON ✓ 2026-08-03
409|402|- [x] env-interpolate-values : expande ${VAR}/$VAR dans les .env (multi-fichiers --from, recursive, cycle detect, quotes/comments preservés, gates check/require-expanded exit 2, JSON) ✓ 2026-08-03
410|403|
411|404|## Vague 617 — CLI Tools (JSON, Markdown, URL, INI, texte)
412|405|- [x] json-key-casing-check : valide le style de casse des clés JSON (camel/pascal/snake/screaming/kebab/lower/upper, chemins jq-style, --ignore, --unique-keys, --report keys|styles, --check --style exit 2, JSON) ✓ 2026-08-03
413|406|- [x] markdown-trailing-space-double : détecte/ajoute/supprime les hard breaks Markdown (double espace en fin de ligne, fences préservées, --strip/--ensure/--in-place, --check present|required|clean exit 2, JSON) ✓ 2026-08-03
414|407|- [x] url-port-default-strip : retire les ports par défaut des URLs (16 schémas built-in, --default-port custom, IPv6/userinfo/query/fragment préservés, --report, --check/require-changed exit 2, JSON) ✓ 2026-08-03
415|408|- [x] ini-section-count-report : rapport de sections et clés INI (parser tolérant doublons/clés globales, --list, gates min/max-sections/keys + no-duplicates/no-empty/no-global exit 2, JSON) ✓ 2026-08-03
416|409|- [x] text-vowel-ratio-report : ratios voyelles/consonnes avec folding accents NFD (--include-y, --per-line, --words N, gates min/max-ratio/expect-vowel/check exit 2, JSON) ✓ 2026-08-03
417|410|
418|411|## Vague 616 — CLI Tools (lignes, INI, Markdown, URL, JSON)
419|412|- [x] line-collapse-multiple-blank : réduit les suites de lignes vides à N max (whitespace-only optionnel, --strip-trailing, --in-place/--output, gates check/require-blank exit 2, JSON) ✓ 2026-08-03
420|413|- [x] ini-comment-char-detect : détecte les caractères de commentaire d'un INI (# / ;, full-line vs inline, mixte signalé, gates check/expect exit 2, JSON) ✓ 2026-08-03
421|414|- [x] markdown-list-normalize : normalise les puces Markdown vers un seul marqueur (-, *, +, fences ignorées, EOL/indent préservés, --in-place/--output, gate check exit 2, JSON) ✓ 2026-08-03
422|415|- [x] url-query-extract-key : extrait les valeurs d'une clé de query-string depuis des URLs (--all, --ignore-case, --with-url, --unique, --empty-ok, gates check/require-all exit 2, JSON) ✓ 2026-08-03
423|416|- [x] json-pretty-indent-width : ré-indente un JSON pretty (width N, --tabs, --compact) et détecte l'indentation (--detect-only, gates expect/require-compact/require-pretty exit 2, --sort-keys, JSON) ✓ 2026-08-03
424|417|
425|418|## Vague 615 — CLI Tools (lignes, env, Markdown, URL, texte)
426|419|- [x] line-most-frequent-show : affiche les N lignes les plus fréquentes (sort|uniq -c|sort -rn en un outil, --exact/--ignore-case/--skip-blank, --least/--alpha, gates check/require-duplicates/min/max-count/expect-line exit 2, JSON) ✓ 2026-08-03
427|420|- [x] env-boolean-values-only : valide les valeurs booléennes d'un .env (true/false/yes/no/on/off/1/0, --key ciblé, quotes/export tolérés, --strict-case, --tokens custom, gates require-key/expect-value exit 2, JSON) ✓ 2026-08-03
428|421|- [x] markdown-code-block-lang-stats : stats par langage des blocs de code fenced (``` et ~~~, alias normalisés, barres ASCII, fences non fermées détectées, gates check/require-lang/forbid-lang/min/max-blocks exit 2, JSON) ✓ 2026-08-03
429|422|- [x] url-host-swap : remplace le host d'URLs (userinfo/port/path/query/fragment préservés, --scheme, port keep/drop, dry-run --check, gates require-changed/require-unchanged exit 2, JSON) ✓ 2026-08-03
430|423|- [x] text-acrostic-extract : extrait le mot acrostiche des premières lettres de lignes (--position N colonne, --strip-prefix, --lower/--strip-diacritics/--letters-only, --show-lines, gates check/expect-word/min/max-length exit 2, JSON) ✓ 2026-08-03
431|424|
432|425|## Vague 614 — CLI Tools (lignes, INI, URL, env, Markdown)
433|426|- [x] line-shortest-show : affiche les N lignes les plus courtes (lineno:length:content, --skip-blank/--blank-only/--first-only, gates check/min-len/max-len exit 2, JSON) ✓ 2026-08-03
434|427|- [x] ini-keys-in-multiple-sections : détecte les clés INI présentes dans 2+ sections (--ignore-case, --sections-only, gates check/require-duplicates/min/max-count/expect-key exit 2, JSON) ✓ 2026-08-03
435|428|- [x] url-path-normalize : normalise les chemins d'URLs (collapse //, resolve /./ /../, --trailing keep/force/strip, query+fragment préservés, gates check/require-changed/require-clean/min/max exit 2, JSON) ✓ 2026-08-03
436|429|- [x] env-integer-values-only : valide les valeurs entières signées d'un .env (--all ou --key ciblé, quotes/export tolérés, --min-value/--max-value, --require-key, --allow-empty, exit 2, JSON) ✓ 2026-08-03
437|430|- [x] markdown-plain-text-extract : extrait le texte brut d'un Markdown (fences/images/liens/formatage/frontmatter strippés, --keep-code, --drop-headings, gates min/max-words + require-non-empty exit 2, JSON) ✓ 2026-08-03
438|431|
439|432|## Vague 613 — CLI Tools (URL, JSON, texte, INI, lignes)
440|433|- [x] url-strip-tracking-params : retire les paramètres de tracking des URLs (utm_*, fbclid, gclid, liste 60+ curée, --add/--remove/--only, gates check/require-changed/require-clean/min/max-removed exit 2, JSON) ✓ 2026-08-03
441|434|- [x] json-min-max-value : min/max des valeurs numériques d'un JSON avec chemins jq-style (booleans exclus, --path subtree, --show-all, gates expect-min/max + min/max-floor/ceiling + require-any/min-count exit 2, JSON) ✓ 2026-08-03
442|435|- [x] text-short-sentence-list : liste les phrases sous N mots (segmenteur à règles, abréviations Mr./e.g. et décimales protégées, --min-words, --numbered, gates check/require-short/min/max-count exit 2, JSON) ✓ 2026-08-03
443|436|- [x] ini-section-rename-prefix : renomme les sections INI par préfixe (modes add/strip/replace, commentaires et ordre préservés, dry-run par défaut, --in-place/-o, --only, gates check/require-renamed/min/max exit 2, JSON) ✓ 2026-08-03
444|437|- [x] line-first-uppercase-note : détecte les lignes ne débutant pas par une majuscule (marqueurs de liste skippés, --allow whitelist, --tally, gates check/require-found/max-count exit 2, JSON) ✓ 2026-08-03
445|438|
446|439|## Vague 606 — CLI Tools (JSON, CSV, texte, env, Markdown)
447|440|- [x] json-path-rewrite : réécrit des valeurs scalaires par chemins dot/bracket (wildcards *, null quand pas de =, transforms upper/lower/trim/int/float/string, gates require-changed/require-path exit 2, JSON) ✓ 2026-08-03
448|441|- [x] csv-quote-balance-check : détecte les guillemets doubles non fermés/stray dans un CSV (position ligne/col/char, délimiteur sniffé, gates min/max/require-clean exit 2, JSON) ✓ 2026-08-03
449|442|- [x] text-word-freq-report : rapport de fréquence de mots (top-N, --min-len, --no-lowercase, stopwords en ligne ou @fichier, gates min/max-unique/total exit 2, JSON) ✓ 2026-08-03
450|443|- [x] env-rename-prefix : renomme le préfixe de clés d'un .env (auto-détect premier segment, --only, dry-run/in-place, gates check/require-renamed exit 2, JSON) ✓ 2026-08-03
451|444|- [x] markdown-heading-promote : décale les titres ATX de N niveaux (clamp 1..6, fences préservés, --in-place, gates check exit 2, JSON) ✓ 2026-08-03
452|445|
453|446|## Vague 605 — CLI Tools (Markdown, CSV, texte, env, lignes)
454|447|- [x] markdown-link-check-list : liste et valide les liens Markdown (inline, référence, autolink, bare URL, fences/code ignorés, gates check/require-links/min/max-count exit 2, JSON) ✓ 2026-08-03
455|448|- [x] csv-column-reorder : réordonne les colonnes d'un CSV par nom ou index (header conservé, '...' pour le reste, délimiteurs sniffer/output, --check/require-columns exit 2, JSON) ✓ 2026-08-03
456|449|- [x] text-unicode-normalize : normalise du texte vers NFC/NFD/NFKC/NFKD, folding ASCII optionnel (--check exit 2, --count, JSON multi-fichiers) ✓ 2026-08-03
457|450|- [x] env-default-inject : injecte les valeurs par défaut manquantes d'un .env (no-overwrite, prefix-stub, comment/dry-run/in-place, check exit 2, JSON) ✓ 2026-08-03
458|451|- [x] line-random-seed : mélange réproductible de lignes (--seed hashé, --sample, --reverse, --block-size, gates check/require-count/min/max exit 2, JSON) ✓ 2026-08-03
459|452|
460|453|## Vague 604 — CLI Tools (Markdown, CSV, texte, JSON, lignes, INI)
461|454|- [x] markdown-table-align : réaligne les tables pipe Markdown (largeurs uniformes, hints :---/:---:/---: préservés, fences ignorés, --in-place, --check exit 2, JSON) ✓ 2026-08-03
462|455|- [x] csv-pad-ragged-rows : normalise les lignes CSV ragged (pad vide/--fill, troncature --truncate, target header/--width/--to-max, délimiteur sniffé, --check/require-ragged exit 2, JSON) ✓ 2026-08-03
463|456|- [x] text-word-shuffle-seed : mélange déterministe des mots par ligne (--seed, --lines, --keep-first/--keep-last, gates check/require-changed/require-unchanged exit 2, JSON) ✓ 2026-08-03
464|457|- [x] json-toggle-null-string : bascule null <-> "null" (modes dans les deux sens, sentinelle --from/--to, JSONL, --compact, gates check/require-changed exit 2, JSON) ✓ 2026-08-03
465|458|- [x] line-count-report : compte les lignes avec breakdowns (total/blank/comment/long, min/max/mean len, --fields, gates min/max-lines/require-non-empty/max-blank exit 2, JSON) ✓ 2026-08-03
466|459|- [x] ini-value-quote-check : audit du quoting des valeurs INI (bare/single/double/unbalanced, --strict-mixed, --style enforce, --to normalize --in-place, exit 2, JSON) ✓ 2026-08-03
467|460|
468|461|## Vague 603 — CLI Tools (CSV, INI, env, chemins)
469|462|- [x] csv-row-number-validate : valide qu'une colonne CSV est une séquence d'entiers (start/step/gaps/dupes, --min/--max, exit 2, --json) ✓ 2026-08-03
470|463|- [x] ini-comment-strip : supprime les commentaires ; et # des INI en préservant valeurs quotées et marqueurs dans strings (--markers, --check exit 2, --in-place, --json) ✓ 2026-08-03
471|464|- [x] env-prefix-validate : valide que chaque clé .env respecte une convention de préfixe (-p multi, --forbid-prefix, --pattern regex, --allow, exit 2, --json) ✓ 2026-08-03
472|465|- [x] csv-delimiter-normalize : convertit un CSV vers tout délimiteur (comma/semicolon/tab/pipe/colon, auto-detect avec fallback fréquence+consistance, quoting minimal/all/nonnumeric/none, --line-ending lf/crlf, --check exit 2) ✓ 2026-08-03
473|466|- [x] path-absolute-resolve : résout les chemins relatifs en absolus (--base, --real symlinks, --must-exist/--must-not-exist/--must-be-inside exit 2, --relative-to, stdin batch -0, JSON) ✓ 2026-08-03
474|467|
475|468|## Vague 602 — CLI Tools (CSV, HTTP, Markdown, texte, lignes)
476|469|- [x] csv-column-mask : masque des colonnes CSV sensibles (modes full/first/last/hash sha256, délimiteur auto, --require-masked exit 2, --json) ✓ 2026-08-03
477|470|- [x] http-header-canonical : normalise la casse des headers HTTP (Title-Case, exceptions ETag/WWW-Authenticate/X-Forwarded-*, --lowercase http2, --sort, --format http/json/dict, --check exit 2) ✓ 2026-08-03
478|471|- [x] markdown-image-extract : extrait toutes les images d'un Markdown (inline, reference-style avec résolution, HTML img, code fences ignorées, --urls-only, lint --missing-alt/--broken-refs/--require-images exit 2, JSON) ✓ 2026-08-03
479|472|- [x] text-byte-count : compte bytes/chars/words/lines UTF-8-aware (multi-fichiers + totals, --fields custom, --max-bytes/--max-chars exit 2, JSON) ✓ 2026-08-03
480|473|- [x] line-padding-strip : supprime le padding leading/trailing par ligne (--chars custom, --keep-blank, --check exit 2, --in-place, JSON) ✓ 2026-08-03
481|474|
482|475|## Vague 601 — CLI Tools (texte, lignes, env, URL)
483|476|- [x] text-strip-ansi-color : supprime les séquences ANSI (CSI couleurs, cursor, OSC, charset) d'un flux (--check exit 2, --count, --in-place, --json) ✓ 2026-08-03
484|477|- [x] line-crop-range : rogne chaque ligne à une plage de colonnes (indices négatifs, --fill pad, --ellipsis, --check-length exit 2, --json) ✓ 2026-08-03
485|478|- [x] env-quote-values : normalise le quoting des valeurs .env (strip/single/double/keep, --force, préservant export/commentaires, --check exit 2, --in-place, --json) ✓ 2026-08-03
486|479|- [x] url-slug-sanitize : convertit en slugs URL-safe (translitération ASCII, --unicode, séparateur custom, --max-length, --check exit 2, --json) ✓ 2026-08-03
487|480|- [x] text-find-repeated-words : liste les mots répétés > N fois (stopwords EN, --min-length, tri count/word, --top, --check exit 2, --json) ✓ 2026-08-03
488|481|
489|482|## Vague 600 — CLI Tools (texte, lignes, fichiers, INI)
490|483|- [x] text-uppercase-words : met en majuscules des mots ciblés (all, --keywords liste/fichier, --nth N, ignore-case, --no-change-check exit 2, JSON) ✓ 2026-08-03
491|484|- [x] line-reverse-order : inverse l'ordre des lignes (tac, trailing newline préservé, assertions --expect-lines/--head-check/--tail-check exit 2, JSON) ✓ 2026-08-03
492|485|- [x] file-trailing-newline : vérifie/corrige la newline finale des fichiers (--fix, -r --glob, --max-size, --include-empty, exit 2, JSON) ✓ 2026-08-03
493|486|- [x] ini-section-merge : fusionne des INI en overlay (--on-conflict last/first/error, --delete-section/--delete-key, --require-key exit 2, formats ini/env/json, --sort) ✓ 2026-08-03
494|487|- [x] line-suffix-add : suffixe chaque ligne ({n} numérotation, --skip-empty, --check-existing, --expect-lines exit 2, JSON) ✓ 2026-08-03
495|488|
496|489|## Vague 599 — CLI Tools (texte, whitespace, Markdown, JSON, CSV)
497|490|- [x] line-prefix-add : préfixe chaque ligne d'un flux ({n} numérotation, --skip-empty, --check-existing, --expect-lines exit 2, JSON) ✓ 2026-08-03
498|491|- [x] text-whitespace-report : rapport whitespace (indentation, tabs, trailing, longueurs) avec lint --no-tabs/--no-trailing/--max-line-length/--max-indent exit 2, JSON ✓ 2026-08-03
499|492|- [x] markdown-heading-anchors : liste les ancres GitHub des titres Markdown, TOC --toc, --check duplicatas/liens cassés exit 2, code fences ignorés, JSON ✓ 2026-08-03
500|493|- [x] json-empty-checks : détecte valeurs vides (null, "", [], {}) avec chemins dot (--kinds, --check, --require-empty, --max-find exit 2, JSON) ✓ 2026-08-03
501|