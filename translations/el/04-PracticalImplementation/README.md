<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "7919ce2e537f0c435c7c23fa6775b613",
  "translation_date": "2025-06-11T18:15:04+00:00",
  "source_file": "04-PracticalImplementation/README.md",
  "language_code": "el"
}
-->
# Πρακτική Εφαρμογή

Η πρακτική εφαρμογή είναι το σημείο όπου η δύναμη του Model Context Protocol (MCP) γίνεται χειροπιαστή. Ενώ η κατανόηση της θεωρίας και της αρχιτεκτονικής πίσω από το MCP είναι σημαντική, η πραγματική αξία αναδεικνύεται όταν εφαρμόζετε αυτές τις έννοιες για να δημιουργήσετε, να δοκιμάσετε και να αναπτύξετε λύσεις που επιλύουν πραγματικά προβλήματα. Αυτό το κεφάλαιο γεφυρώνει το χάσμα μεταξύ της εννοιολογικής γνώσης και της πρακτικής ανάπτυξης, καθοδηγώντας σας στη διαδικασία υλοποίησης εφαρμογών βασισμένων στο MCP.

Είτε αναπτύσσετε έξυπνους βοηθούς, ενσωματώνετε AI σε επιχειρησιακές ροές εργασίας, είτε δημιουργείτε προσαρμοσμένα εργαλεία για επεξεργασία δεδομένων, το MCP προσφέρει μια ευέλικτη βάση. Ο σχεδιασμός του που δεν εξαρτάται από γλώσσα προγραμματισμού και τα επίσημα SDK για δημοφιλείς γλώσσες το καθιστούν προσιτό σε ένα ευρύ φάσμα προγραμματιστών. Αξιοποιώντας αυτά τα SDK, μπορείτε γρήγορα να δημιουργήσετε πρωτότυπα, να επαναλάβετε και να κλιμακώσετε τις λύσεις σας σε διαφορετικές πλατφόρμες και περιβάλλοντα.

Στις επόμενες ενότητες, θα βρείτε πρακτικά παραδείγματα, δείγματα κώδικα και στρατηγικές ανάπτυξης που δείχνουν πώς να υλοποιήσετε MCP σε C#, Java, TypeScript, JavaScript και Python. Επίσης, θα μάθετε πώς να εντοπίζετε σφάλματα και να δοκιμάζετε τους MCP servers σας, να διαχειρίζεστε APIs και να αναπτύσσετε λύσεις στο cloud χρησιμοποιώντας το Azure. Αυτοί οι πρακτικοί πόροι έχουν σχεδιαστεί για να επιταχύνουν τη μάθησή σας και να σας βοηθήσουν να δημιουργήσετε με αυτοπεποίθηση στιβαρές, έτοιμες για παραγωγή εφαρμογές MCP.

## Επισκόπηση

Αυτό το μάθημα εστιάζει σε πρακτικές πτυχές της υλοποίησης MCP σε πολλές γλώσσες προγραμματισμού. Θα εξερευνήσουμε πώς να χρησιμοποιήσουμε τα MCP SDK σε C#, Java, TypeScript, JavaScript και Python για να δημιουργήσουμε στιβαρές εφαρμογές, να εντοπίσουμε και να δοκιμάσουμε MCP servers, και να δημιουργήσουμε επαναχρησιμοποιήσιμους πόρους, prompts και εργαλεία.

## Στόχοι Μάθησης

Στο τέλος αυτού του μαθήματος, θα μπορείτε να:
- Υλοποιείτε λύσεις MCP χρησιμοποιώντας τα επίσημα SDK σε διάφορες γλώσσες προγραμματισμού
- Εντοπίζετε και να δοκιμάζετε συστηματικά MCP servers
- Δημιουργείτε και να χρησιμοποιείτε λειτουργίες server (Resources, Prompts, και Tools)
- Σχεδιάζετε αποτελεσματικές ροές εργασίας MCP για σύνθετες εργασίες
- Βελτιστοποιείτε τις υλοποιήσεις MCP για απόδοση και αξιοπιστία

## Επίσημοι Πόροι SDK

Το Model Context Protocol προσφέρει επίσημα SDK για πολλές γλώσσες:

- [C# SDK](https://github.com/modelcontextprotocol/csharp-sdk)
- [Java SDK](https://github.com/modelcontextprotocol/java-sdk) 
- [TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk)
- [Python SDK](https://github.com/modelcontextprotocol/python-sdk)
- [Kotlin SDK](https://github.com/modelcontextprotocol/kotlin-sdk)

## Εργασία με τα MCP SDKs

Αυτή η ενότητα παρέχει πρακτικά παραδείγματα υλοποίησης MCP σε πολλές γλώσσες προγραμματισμού. Μπορείτε να βρείτε δείγματα κώδικα στον `samples` φάκελο οργανωμένο ανά γλώσσα.

### Διαθέσιμα Παραδείγματα

Το αποθετήριο περιλαμβάνει δείγματα υλοποίησης στις παρακάτω γλώσσες:

- C#
- Java
- TypeScript
- JavaScript
- Python

Κάθε δείγμα παρουσιάζει βασικές έννοιες MCP και μοτίβα υλοποίησης για τη συγκεκριμένη γλώσσα και οικοσύστημα.

## Βασικές Λειτουργίες Server

Οι MCP servers μπορούν να υλοποιήσουν οποιονδήποτε συνδυασμό από αυτές τις λειτουργίες:

### Resources
Οι Resources παρέχουν πλαίσιο και δεδομένα για χρήση από τον χρήστη ή το μοντέλο AI:
- Αποθετήρια εγγράφων
- Βάσεις γνώσης
- Δομημένες πηγές δεδομένων
- Αρχειακά συστήματα

### Prompts
Τα Prompts είναι προτύπα μηνυμάτων και ροών εργασίας για τους χρήστες:
- Προκαθορισμένα πρότυπα συνομιλίας
- Καθοδηγούμενα μοτίβα αλληλεπίδρασης
- Εξειδικευμένες δομές διαλόγου

### Tools
Τα Tools είναι λειτουργίες που εκτελεί το μοντέλο AI:
- Βοηθητικά εργαλεία επεξεργασίας δεδομένων
- Ενσωματώσεις με εξωτερικά APIs
- Υπολογιστικές δυνατότητες
- Λειτουργίες αναζήτησης

## Παραδείγματα Υλοποίησης: C#

Το επίσημο αποθετήριο C# SDK περιέχει αρκετά δείγματα που παρουσιάζουν διαφορετικές πτυχές του MCP:

- **Basic MCP Client**: Απλό παράδειγμα που δείχνει πώς να δημιουργήσετε έναν MCP client και να καλέσετε εργαλεία
- **Basic MCP Server**: Ελάχιστη υλοποίηση server με βασική καταχώρηση εργαλείων
- **Advanced MCP Server**: Πλήρης server με καταχώρηση εργαλείων, αυθεντικοποίηση και διαχείριση σφαλμάτων
- **ASP.NET Integration**: Παραδείγματα ενσωμάτωσης με ASP.NET Core
- **Tool Implementation Patterns**: Διάφορα μοτίβα για την υλοποίηση εργαλείων με διαφορετικά επίπεδα πολυπλοκότητας

Το MCP C# SDK βρίσκεται σε προεπισκόπηση και τα APIs μπορεί να αλλάξουν. Θα ενημερώνουμε συνεχώς αυτό το blog καθώς το SDK εξελίσσεται.

### Κύρια Χαρακτηριστικά 
- [C# MCP Nuget ModelContextProtocol](https://www.nuget.org/packages/ModelContextProtocol)

- Δημιουργία του [πρώτου MCP Server](https://devblogs.microsoft.com/dotnet/build-a-model-context-protocol-mcp-server-in-csharp/).

Για ολοκληρωμένα δείγματα υλοποίησης σε C#, επισκεφθείτε το [επίσημο αποθετήριο δειγμάτων C# SDK](https://github.com/modelcontextprotocol/csharp-sdk)

## Παράδειγμα υλοποίησης: Java

Το Java SDK προσφέρει στιβαρές επιλογές υλοποίησης MCP με χαρακτηριστικά κατάλληλα για επιχειρήσεις.

### Κύρια Χαρακτηριστικά

- Ενσωμάτωση με Spring Framework
- Ισχυρή ασφάλεια τύπων
- Υποστήριξη reactive προγραμματισμού
- Ολοκληρωμένη διαχείριση σφαλμάτων

Για ολοκληρωμένο παράδειγμα υλοποίησης Java, δείτε το [MCPSample.java](../../../04-PracticalImplementation/samples/java/MCPSample.java) στον φάκελο samples.

## Παράδειγμα υλοποίησης: JavaScript

Το JavaScript SDK παρέχει μια ελαφριά και ευέλικτη προσέγγιση στην υλοποίηση MCP.

### Κύρια Χαρακτηριστικά

- Υποστήριξη Node.js και browser
- Promise-based API
- Εύκολη ενσωμάτωση με Express και άλλα frameworks
- Υποστήριξη WebSocket για streaming

Για ολοκληρωμένο παράδειγμα υλοποίησης JavaScript, δείτε το [mcp_sample.js](../../../04-PracticalImplementation/samples/javascript/mcp_sample.js) στον φάκελο samples.

## Παράδειγμα υλοποίησης: Python

Το Python SDK προσφέρει μια Pythonic προσέγγιση στην υλοποίηση MCP με εξαιρετικές ενσωματώσεις σε ML frameworks.

### Κύρια Χαρακτηριστικά

- Υποστήριξη async/await με asyncio
- Ενσωμάτωση με Flask και FastAPI
- Απλή καταχώρηση εργαλείων
- Φυσική ενσωμάτωση με δημοφιλείς βιβλιοθήκες ML

Για ολοκληρωμένο παράδειγμα υλοποίησης Python, δείτε το [mcp_sample.py](../../../04-PracticalImplementation/samples/python/mcp_sample.py) στον φάκελο samples.

## Διαχείριση API

Το Azure API Management είναι μια εξαιρετική λύση για το πώς μπορούμε να ασφαλίσουμε MCP Servers. Η ιδέα είναι να τοποθετήσετε μια υπηρεσία Azure API Management μπροστά από τον MCP Server σας και να αφήσετε αυτή να διαχειριστεί λειτουργίες που πιθανόν να χρειάζεστε όπως:

- περιορισμός ρυθμού αιτήσεων
- διαχείριση tokens
- παρακολούθηση
- ισορροπία φορτίου
- ασφάλεια

### Παράδειγμα Azure

Εδώ είναι ένα παράδειγμα Azure που κάνει ακριβώς αυτό, δηλαδή [δημιουργία MCP Server και ασφάλισή του με Azure API Management](https://github.com/Azure-Samples/remote-mcp-apim-functions-python).

Δείτε πώς γίνεται η ροή εξουσιοδότησης στην παρακάτω εικόνα:

![APIM-MCP](https://github.com/Azure-Samples/remote-mcp-apim-functions-python/blob/main/mcp-client-authorization.gif?raw=true) 

Στην παραπάνω εικόνα, συμβαίνει το εξής:

- Η αυθεντικοποίηση/εξουσιοδότηση γίνεται μέσω Microsoft Entra.
- Το Azure API Management λειτουργεί ως πύλη και χρησιμοποιεί πολιτικές για να κατευθύνει και να διαχειρίζεται την κίνηση.
- Το Azure Monitor καταγράφει όλα τα αιτήματα για περαιτέρω ανάλυση.

#### Ροή εξουσιοδότησης

Ας δούμε πιο αναλυτικά τη ροή εξουσιοδότησης:

![Sequence Diagram](https://github.com/Azure-Samples/remote-mcp-apim-functions-python/blob/main/infra/app/apim-oauth/diagrams/images/mcp-client-auth.png?raw=true)

#### Προδιαγραφή εξουσιοδότησης MCP

Μάθετε περισσότερα για την [Προδιαγραφή Εξουσιοδότησης MCP](https://modelcontextprotocol.io/specification/2025-03-26/basic/authorization#2-10-third-party-authorization-flow)

## Ανάπτυξη Remote MCP Server στο Azure

Ας δούμε αν μπορούμε να αναπτύξουμε το παράδειγμα που αναφέραμε προηγουμένως:

1. Κλωνοποιήστε το αποθετήριο

    ```bash
    git clone https://github.com/Azure-Samples/remote-mcp-apim-functions-python.git
    cd remote-mcp-apim-functions-python
    ```

2. Εγγραφείτε `Microsoft.App` resource provider.
    * If you are using Azure CLI, run `az provider register --namespace Microsoft.App --wait`.
    * If you are using Azure PowerShell, run `Register-AzResourceProvider -ProviderNamespace Microsoft.App`. Then run `(Get-AzResourceProvider -ProviderNamespace Microsoft.App).RegistrationState` και περιμένετε λίγο για να ελέγξετε αν η εγγραφή ολοκληρώθηκε.

3. Εκτελέστε αυτή την εντολή [azd](https://aka.ms/azd) για να προμηθεύσετε την υπηρεσία API management, την function app (με κώδικα) και όλους τους υπόλοιπους απαραίτητους πόρους Azure

    ```shell
    azd up
    ```

    Αυτή η εντολή θα αναπτύξει όλους τους πόρους στο cloud στο Azure

### Δοκιμή του server σας με MCP Inspector

1. Σε ένα **νέο παράθυρο τερματικού**, εγκαταστήστε και τρέξτε το MCP Inspector

    ```shell
    npx @modelcontextprotocol/inspector
    ```

    Θα δείτε μια διεπαφή παρόμοια με:

    ![Connect to Node inspector](../../../translated_images/connect.141db0b2bd05f096fb1dd91273771fd8b2469d6507656c3b0c9df4b3c5473929.el.png) 

2. Κάντε CTRL κλικ για να φορτώσετε την web εφαρμογή MCP Inspector από το URL που εμφανίζει η εφαρμογή (π.χ. http://127.0.0.1:6274/#resources)
3. Ορίστε τον τύπο μεταφοράς σε `SSE`
1. Set the URL to your running API Management SSE endpoint displayed after `azd up` και **Connect**:

    ```shell
    https://<apim-servicename-from-azd-output>.azure-api.net/mcp/sse
    ```

5. **Λίστα Εργαλείων**. Κάντε κλικ σε ένα εργαλείο και επιλέξτε **Run Tool**.  

Αν όλα τα βήματα έγιναν σωστά, τώρα θα είστε συνδεδεμένοι με τον MCP server και θα έχετε καλέσει ένα εργαλείο.

## MCP servers για Azure

[Remote-mcp-functions](https://github.com/Azure-Samples/remote-mcp-functions-dotnet): Αυτό το σύνολο αποθετηρίων είναι πρότυπο εκκίνησης για την κατασκευή και ανάπτυξη προσαρμοσμένων απομακρυσμένων MCP (Model Context Protocol) servers χρησιμοποιώντας Azure Functions με Python, C# .NET ή Node/TypeScript.

Τα δείγματα παρέχουν μια ολοκληρωμένη λύση που επιτρέπει στους προγραμματιστές να:

- Δημιουργούν και να τρέχουν τοπικά: Αναπτύσσουν και εντοπίζουν σφάλματα σε MCP server σε τοπικό μηχάνημα
- Αναπτύσσουν στο Azure: Αναπτύσσουν εύκολα στο cloud με μια απλή εντολή azd up
- Συνδέονται από clients: Συνδέονται στον MCP server από διάφορους clients συμπεριλαμβανομένου του VS Code Copilot agent mode και του εργαλείου MCP Inspector

### Κύρια Χαρακτηριστικά:

- Ασφάλεια εκ κατασκευής: Ο MCP server προστατεύεται με κλειδιά και HTTPS
- Επιλογές αυθεντικοποίησης: Υποστηρίζει OAuth με ενσωματωμένη αυθεντικοποίηση και/ή API Management
- Δικτυακή απομόνωση: Επιτρέπει δικτυακή απομόνωση μέσω Azure Virtual Networks (VNET)
- Serverless αρχιτεκτονική: Χρησιμοποιεί Azure Functions για κλιμακούμενη, event-driven εκτέλεση
- Τοπική ανάπτυξη: Ολοκληρωμένη υποστήριξη τοπικής ανάπτυξης και εντοπισμού σφαλμάτων
- Απλή ανάπτυξη: Απλοποιημένη διαδικασία ανάπτυξης στο Azure

Το αποθετήριο περιλαμβάνει όλα τα απαραίτητα αρχεία ρυθμίσεων, πηγαίο κώδικα και ορισμούς υποδομής για να ξεκινήσετε γρήγορα με μια παραγωγική υλοποίηση MCP server.

- [Azure Remote MCP Functions Python](https://github.com/Azure-Samples/remote-mcp-functions-python) - Δείγμα υλοποίησης MCP χρησιμοποιώντας Azure Functions με Python

- [Azure Remote MCP Functions .NET](https://github.com/Azure-Samples/remote-mcp-functions-dotnet) - Δείγμα υλοποίησης MCP χρησιμοποιώντας Azure Functions με C# .NET

- [Azure Remote MCP Functions Node/Typescript](https://github.com/Azure-Samples/remote-mcp-functions-typescript) - Δείγμα υλοποίησης MCP χρησιμοποιώντας Azure Functions με Node/TypeScript.

## Κύρια Συμπεράσματα

- Τα MCP SDK παρέχουν γλωσσικά εργαλεία για την υλοποίηση στιβαρών λύσεων MCP
- Η διαδικασία εντοπισμού σφαλμάτων και δοκιμών είναι κρίσιμη για αξιόπιστες εφαρμογές MCP
- Τα επαναχρησιμοποιήσιμα πρότυπα prompt επιτρέπουν συνεπή αλληλεπίδραση με το AI
- Οι καλά σχεδιασμένες ροές εργασίας μπορούν να συντονίζουν σύνθετες εργασίες χρησιμοποιώντας πολλαπλά εργαλεία
- Η υλοποίηση λύσεων MCP απαιτεί προσοχή στην ασφάλεια, την απόδοση και τη διαχείριση σφαλμάτων

## Άσκηση

Σχεδιάστε μια πρακτική ροή εργασίας MCP που να αντιμετωπίζει ένα πραγματικό πρόβλημα στον τομέα σας:

1. Εντοπίστε 3-4 εργαλεία που θα ήταν χρήσιμα για την επίλυση αυτού του προβλήματος
2. Δημιουργήστε ένα διάγραμμα ροής που να δείχνει πώς αυτά τα εργαλεία αλληλεπιδρούν
3. Υλοποιήστε μια βασική έκδοση ενός από τα εργαλεία χρησιμοποιώντας την προτιμώμενη γλώσσα σας
4. Δημιουργήστε ένα πρότυπο prompt που θα βοηθήσει το μοντέλο να χρησιμοποιήσει αποτελεσματικά το εργαλείο σας

## Επιπλέον Πόροι


---

Επόμενο: [Advanced Topics](../05-AdvancedTopics/README.md)

**Αποποίηση ευθυνών**:  
Αυτό το έγγραφο έχει μεταφραστεί χρησιμοποιώντας την υπηρεσία μετάφρασης AI [Co-op Translator](https://github.com/Azure/co-op-translator). Παρόλο που προσπαθούμε για ακρίβεια, παρακαλούμε να γνωρίζετε ότι οι αυτοματοποιημένες μεταφράσεις ενδέχεται να περιέχουν λάθη ή ανακρίβειες. Το πρωτότυπο έγγραφο στη μητρική του γλώσσα πρέπει να θεωρείται η αυθεντική πηγή. Για κρίσιμες πληροφορίες, συνιστάται επαγγελματική ανθρώπινη μετάφραση. Δεν φέρουμε ευθύνη για τυχόν παρεξηγήσεις ή λανθασμένες ερμηνείες που προκύπτουν από τη χρήση αυτής της μετάφρασης.