<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "2342baa570312086fc19edcf41320250",
  "translation_date": "2025-06-17T16:11:57+00:00",
  "source_file": "03-GettingStarted/02-client/README.md",
  "language_code": "ro"
}
-->
În codul precedent am:

- Importat bibliotecile
- Creat o instanță a unui client și conectat-o folosind stdio pentru transport.
- Listat prompturi, resurse și unelte și le-am invocat pe toate.

Iată-l, un client care poate comunica cu un MCP Server.

Hai să ne luăm timpul în următoarea secțiune de exerciții și să descompunem fiecare fragment de cod pentru a explica ce se întâmplă.

## Exercițiu: Scrierea unui client

Așa cum am spus mai sus, să ne luăm timpul să explicăm codul și, dacă vreți, puteți să scrieți codul alături de noi.

### -1- Importarea bibliotecilor

Să importăm bibliotecile de care avem nevoie, vom avea nevoie de referințe la un client și la protocolul de transport ales, stdio. stdio este un protocol pentru lucruri care sunt menite să ruleze pe mașina ta locală. SSE este un alt protocol de transport pe care îl vom arăta în capitolele viitoare, dar aceasta este cealaltă opțiune. Pentru moment, să continuăm cu stdio.

---

Să trecem la instanțiere.

### -2- Instanțierea clientului și a transportului

Va trebui să creăm o instanță a transportului și una a clientului nostru:

---

### -3- Listarea funcționalităților serverului

Acum avem un client care se poate conecta dacă programul este rulat. Totuși, nu listează efectiv funcționalitățile sale, așa că să facem asta acum:

---

Groza, acum am capturat toate funcționalitățile. Întrebarea este când le folosim? Ei bine, acest client este destul de simplu, simplu în sensul că va trebui să apelăm explicit funcționalitățile atunci când le dorim. În capitolul următor, vom crea un client mai avansat care va avea acces la propriul său model lingvistic mare, LLM. Pentru moment, să vedem cum putem invoca funcționalitățile de pe server:

### -4- Invocarea funcționalităților

Pentru a invoca funcționalitățile trebuie să ne asigurăm că specificăm argumentele corecte și, în unele cazuri, numele a ceea ce încercăm să invocăm.

---

### -5- Rularea clientului

Pentru a rula clientul, tastează următoarea comandă în terminal:

---

## Tema

În această temă, vei folosi ce ai învățat despre crearea unui client, dar vei crea propriul tău client.

Iată un server pe care îl poți folosi și la care trebuie să te conectezi prin codul clientului tău, vezi dacă poți adăuga mai multe funcționalități serverului pentru a-l face mai interesant.

---

## Soluție

[Soluție](./solution/README.md)

## Aspecte importante

Aspectele importante din acest capitol despre clienți sunt următoarele:

- Pot fi folosiți atât pentru a descoperi, cât și pentru a invoca funcționalități pe server.
- Pot porni un server în timp ce se pornesc singuri (ca în acest capitol), dar clienții se pot conecta și la servere deja pornite.
- Sunt o metodă excelentă de a testa capabilitățile serverului, alături de alternative precum Inspector, așa cum s-a descris în capitolul precedent.

## Resurse suplimentare

- [Construirea clienților în MCP](https://modelcontextprotocol.io/quickstart/client)

## Exemple

- [Calculator Java](../samples/java/calculator/README.md)
- [Calculator .Net](../../../../03-GettingStarted/samples/csharp)
- [Calculator JavaScript](../samples/javascript/README.md)
- [Calculator TypeScript](../samples/typescript/README.md)
- [Calculator Python](../../../../03-GettingStarted/samples/python)

## Ce urmează

- Următorul: [Crearea unui client cu un LLM](/03-GettingStarted/03-llm-client/README.md)

**Declinare a responsabilității**:  
Acest document a fost tradus folosind serviciul de traducere AI [Co-op Translator](https://github.com/Azure/co-op-translator). Deși ne străduim pentru acuratețe, vă rugăm să rețineți că traducerile automate pot conține erori sau inexactități. Documentul original în limba sa nativă trebuie considerat sursa autorizată. Pentru informații critice, se recomandă traducerea profesională realizată de un specialist uman. Nu ne asumăm răspunderea pentru eventualele neînțelegeri sau interpretări greșite care pot apărea în urma utilizării acestei traduceri.