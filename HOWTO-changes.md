## Οδηγίες παραμετροποίησης weblate ##

Μετά την εγκατάσταση του Weblate σε docker, πηγαίνετε στο directory του docker weblate-docker_weblate-data:

_data/python/customize/static/

Κατά την εκκίνηση του docker, τα αρχεία που από εκεί θα γίνουν cached και θα φαίνονται στο https://WEBLATE_SITE/WEBLATE_DIRECTORY/static/ με την δομή σε directories να είναι ίδια. 

Δημιουργήσαμε τα directories *css* και *js* , και βάλαμε τα αρχεία *custom.css* και *custom.js* αντίστοιχα. Με το custom.css παραμετροποιήται η εμφάνιση, ενώ με το custom.js προστέθηκαν πληροφορίες στο footer του weblate. Επίσης, ανέβηκε το λογότυπο του ελ/λακ (ellak_logo.png) .

Τα static αρχεία διαβάζονται κατά την εκκίνηση του docker, και όποιες αλλαγές σε αυτά θα φανούν μετά την επόμενη εκκίνηση του docker.


Στο αρχικό directory του docker, εκεί που γίνεται το configuration στο αρχείο: docker-compose.override.yml προστέθηκε η παράμετρος WEBLATE_EXTRA_HTML_HEAD με τιμή:

<link type="text/css" rel="stylesheet" href="https://WEBLATE_SITE/WEBLATE_DIRECTORY/static/css/custom.css"><script src="https://WEBLATE_SITE/WEBLATE_DIRECTORY/static/js/custom.js" defer></s
cript>

Το περιεχόμενο της παραμέτρου θα περάσει στον header της html. 