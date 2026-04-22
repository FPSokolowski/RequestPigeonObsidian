---
dbType: nvarchar(16)
---

| Text      | Num | DisplayName            | Description                                                                     |
| --------- | :-: | ---------------------- | ------------------------------------------------------------------------------- |
| Draft     |  0  | Wersja robocza         | Dokument jest w trakcie tworzenia                                               |
| Sending   |  1  | Wysyłanie              | Dokument jest w trakcie przetwarzania i niedługo trafi do osób zatwierdzających |
| Waiting   |  2  | Oczekiwanie na decyzję | Dokument dotarł do osób decyzyjnych i oczekuje na zatwierdzenie                 |
| Cancelled |  3  | Anulowano              | Wniosek został anulowany                                                        |
| Approved  |  4  | Zatwierdzono           | Dokument został rozpatrzony pozytywnie                                          |
| Declined  |  5  | Odrzucono              | Wniosek został rozpatrzony negatywnie                                           |
| Error     |  6  | Błąd                   | Wystąpił błąd podczas przetwarzania wniosku                                     |
