# Μαθαίνω Python

Διαδραστικά μαθήματα Python για την Α' Γυμνασίου. Ο κώδικας τρέχει μέσα στον browser με [Pyodide](https://pyodide.org), χωρίς εγκατάσταση και χωρίς λογαριασμό.

Περιέχει 14 μικρά μαθήματα των ~30 λεπτών, με ένα καινούργιο πράγμα το καθένα: print, λάθη, χελώνα, χρώματα, for, range, μεταβλητές, input, int, if, random, λίστες, while και ένα τελικό project («Μάντεψε τον αριθμό») σε τρία κομμάτια. Έχει 33 ασκήσεις με αυτόματο έλεγχο (Άλλαξε / Γράψε / Διόρθωσε), 13 ερωτήσεις «Πρόβλεψε», ένα κουίζ 10 ερωτήσεων και ένα ελεύθερο «εργαστήρι». Η πρόοδος, ο κώδικας και τα αστέρια αποθηκεύονται μόνο στον browser του παιδιού (localStorage).

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

Για ερώτηση «Πρόβλεψε» (το `data-answer` μετράει από το 0):

```html
<div class="predict" data-p="p14" data-answer="1">
  <p class="pq">Τι θα εμφανίσει;</p>
  <script type="text/plain">print(2 * 3)</script>
  <ol class="opts"><li>23</li><li>6</li><li>2 * 3</li></ol>
  <p class="why">Εξήγηση που φαίνεται μετά τη σωστή απάντηση.</p>
</div>
```
