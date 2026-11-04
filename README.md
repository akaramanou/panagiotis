# Μαθαίνω Python

Διαδραστικά μαθήματα Python για την Α' Γυμνασίου. Ο κώδικας τρέχει μέσα στον browser με [Pyodide](https://pyodide.org), χωρίς εγκατάσταση και χωρίς λογαριασμό.

Περιέχει 9 βήματα (print, μεταβλητές, input, αριθμοί, χελώνα, for, if, random/while, κυνήγι σφαλμάτων), 16 ασκήσεις με αυτόματο έλεγχο, ένα κουίζ 10 ερωτήσεων και ένα ελεύθερο «εργαστήρι». Η πρόοδος, ο κώδικας και τα αστέρια αποθηκεύονται μόνο στον browser του παιδιού (localStorage).

## Δημοσίευση στο GitHub Pages

1. Ανέβασε το `index.html` σε ένα αποθετήριο (π.χ. `python-paidia`).
2. **Settings → Pages → Build and deployment**: Source «Deploy from a branch», branch `main`, φάκελος `/ (root)`, **Save**.
3. Σε 1-2 λεπτά η σελίδα θα είναι στο `https://<username>.github.io/python-paidia/`.

## Πώς προσθέτω άσκηση

Μέσα σε ένα `<section class="step">` πρόσθεσε:

```html
<div class="ex" data-ex="e17" data-title="Τίτλος">
  <p>Εκφώνηση…</p>
  <script type="text/plain" class="starter">
    # αρχικός κώδικας
  </script>
</div>
```

και στο αντικείμενο `CHECKS` του JavaScript τον έλεγχό της:

```js
e17: { tests: [['απάντηση στο input']], fn: ([r]) => has(r, 'αναμενόμενο') ? OK('Μπράβο!') : NO('Υπόδειξη…') },
```

Κάθε στοιχείο του `tests` είναι μια λίστα με τις απαντήσεις που θα δοθούν στα `input()`. Το `r.out` έχει ό,τι τύπωσε το πρόγραμμα. Για σχέδια με τη χελώνα, το `segs(r)` επιστρέφει τις γραμμές που ζωγραφίστηκαν. Για απλό κουτί «Δοκίμασε» χωρίς έλεγχο, χρησιμοποίησε `<div class="try" data-id="μοναδικό-id">`.
