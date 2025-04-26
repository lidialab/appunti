# Personalizza Firefox

## Colore di sfondo della scheda attiva

Nel tuo profilo Firefox crea la cartella ```chrome``` e al suo interno crea il file ```userChrome.css``` con contenuto

```
/* Tab: selected colors */
#tabbrowser-tabs .tabbrowser-tab[selected] .tab-content {
	border-bottom-style: solid !important;
	border-bottom-width: 3px !important;
	border-bottom-color: yellow !important;
}
```

In Firefox da ```about:config``` imposta ```toolkit.legacyUserProfileCustomizations.stylesheets``` a ```true```


