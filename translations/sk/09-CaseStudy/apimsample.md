<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "36de9fae488d6de554d969fe8e0801a8",
  "translation_date": "2025-06-20T19:24:46+00:00",
  "source_file": "09-CaseStudy/apimsample.md",
  "language_code": "sk"
}
-->
# Prípadová štúdia: Zverejnenie REST API v API Management ako MCP server

Azure API Management je služba, ktorá poskytuje bránu nad vašimi API koncovými bodmi. Funguje tak, že Azure API Management pôsobí ako proxy pred vašimi API a môže rozhodnúť, čo robiť s prichádzajúcimi požiadavkami.

Použitím tejto služby získate množstvo funkcií, ako napríklad:

- **Bezpečnosť**, môžete použiť všetko od API kľúčov, JWT až po spravovanú identitu.
- **Obmedzenie rýchlosti (rate limiting)**, skvelá funkcia, ktorá vám umožní určiť, koľko volaní prejde za určitú časovú jednotku. To pomáha zabezpečiť, že všetci používatelia budú mať dobrý zážitok a zároveň sa služba nepreťaží požiadavkami.
- **Škálovanie a vyvažovanie záťaže**. Môžete nastaviť viacero koncových bodov na vyváženie záťaže a tiež rozhodnúť, ako bude vyvažovanie prebiehať.
- **AI funkcie ako sémantické cachovanie**, limitovanie tokenov, monitorovanie tokenov a ďalšie. Tieto funkcie zlepšujú odozvu a zároveň vám pomáhajú mať prehľad o spotrebe tokenov. [Viac informácií tu](https://learn.microsoft.com/en-us/azure/api-management/genai-gateway-capabilities).

## Prečo MCP + Azure API Management?

Model Context Protocol sa rýchlo stáva štandardom pre agentné AI aplikácie a spôsob, ako konzistentne zverejňovať nástroje a dáta. Azure API Management je prirodzenou voľbou, keď potrebujete "spravovať" API. MCP servery často integrujú iné API na riešenie požiadaviek na nástroje, napríklad. Preto kombinácia Azure API Management a MCP dáva veľký zmysel.

## Prehľad

V tomto konkrétnom prípade sa naučíme, ako zverejniť API koncové body ako MCP server. Týmto spôsobom môžeme jednoducho sprístupniť tieto koncové body ako súčasť agentnej aplikácie a zároveň využiť funkcie Azure API Management.

## Kľúčové vlastnosti

- Vyberiete metódy koncového bodu, ktoré chcete sprístupniť ako nástroje.
- Dodatočné funkcie, ktoré získate, závisia od konfigurácie v sekcii politík pre vaše API. Tu vám však ukážeme, ako pridať obmedzenie rýchlosti.

## Predkrok: import API

Ak už máte API v Azure API Management, skvelé, tento krok môžete preskočiť. Ak nie, pozrite si tento odkaz, [importovanie API do Azure API Management](https://learn.microsoft.com/en-us/azure/api-management/import-and-publish#import-and-publish-a-backend-api).

## Zverejnenie API ako MCP server

Na zverejnenie API koncových bodov postupujte podľa týchto krokov:

1. Prejdite do Azure portálu na adresu <https://portal.azure.com/?Microsoft_Azure_ApiManagement=mcp>  
   Prejdite na vašu inštanciu API Management.

1. V ľavom menu vyberte APIs > MCP Servers > + Create new MCP Server.

1. V sekcii API vyberte REST API, ktoré chcete zverejniť ako MCP server.

1. Vyberte jednu alebo viac API operácií, ktoré chcete zverejniť ako nástroje. Môžete vybrať všetky operácie alebo len konkrétne.

    ![Vyberte metódy na zverejnenie](https://learn.microsoft.com/en-us/azure/api-management/media/export-rest-mcp-server/create-mcp-server-small.png)

1. Kliknite na **Create**.

1. Prejdite do menu **APIs** a **MCP Servers**, mali by ste vidieť nasledovné:

    ![Zobrazenie MCP servera v hlavnom paneli](https://learn.microsoft.com/en-us/azure/api-management/media/export-rest-mcp-server/mcp-server-list.png)

    MCP server je vytvorený a API operácie sú sprístupnené ako nástroje. MCP server je uvedený v paneli MCP Servers. Stĺpec URL zobrazuje koncový bod MCP servera, ktorý môžete volať na testovanie alebo v klientskej aplikácii.

## Voliteľné: Konfigurácia politík

Azure API Management používa koncept politík, kde nastavujete rôzne pravidlá pre svoje koncové body, napríklad obmedzenie rýchlosti alebo sémantické cachovanie. Tieto politiky sa píšu v XML.

Tu je návod, ako nastaviť politiku na obmedzenie rýchlosti pre váš MCP server:

1. V portáli, v sekcii APIs, vyberte **MCP Servers**.

1. Vyberte MCP server, ktorý ste vytvorili.

1. V ľavom menu, pod MCP, vyberte **Policies**.

1. V editore politík pridajte alebo upravte politiky, ktoré chcete aplikovať na nástroje MCP servera. Politiky sú definované v XML formáte. Napríklad môžete pridať politiku na obmedzenie volaní nástrojov MCP servera (v tomto príklade 5 volaní za 30 sekúnd na IP adresu klienta). Tu je XML, ktorý zabezpečí obmedzenie rýchlosti:

    ```xml
     <rate-limit-by-key calls="5" 
       renewal-period="30" 
       counter-key="@(context.Request.IpAddress)" 
       remaining-calls-variable-name="remainingCallsPerIP" 
    />
    ```

    Tu je obrázok editora politík:

    ![Editor politík](https://learn.microsoft.com/en-us/azure/api-management/media/export-rest-mcp-server/mcp-server-policies-small.png)
 
## Vyskúšajte to

Uistime sa, že náš MCP Server funguje podľa očakávaní.

Na to použijeme Visual Studio Code a GitHub Copilot v režime agenta. Pridáme MCP server do súboru *mcp.json*. Týmto spôsobom bude Visual Studio Code fungovať ako klient s agentnými schopnosťami a koncoví používatelia budú môcť zadávať príkazy a komunikovať so serverom.

Ako pridať MCP server vo Visual Studio Code:

1. Použite príkaz MCP: **Add Server z Command Palette**.

1. Keď budete vyzvaní, vyberte typ servera: **HTTP (HTTP alebo Server Sent Events)**.

1. Zadajte URL MCP servera v API Management. Príklad: **https://<apim-service-name>.azure-api.net/<api-name>-mcp/sse** (pre SSE koncový bod) alebo **https://<apim-service-name>.azure-api.net/<api-name>-mcp/mcp** (pre MCP koncový bod), všimnite si rozdiel medzi transportmi `/sse` or `/mcp`.

1. Zadajte ID servera podľa vlastného výberu. Nie je to kritická hodnota, ale pomôže vám to zapamätať si, čo táto inštancia servera predstavuje.

1. Vyberte, či chcete uložiť konfiguráciu do nastavení pracovného priestoru alebo používateľských nastavení.

  - **Nastavenia pracovného priestoru** - Konfigurácia servera sa uloží do súboru .vscode/mcp.json, ktorý je dostupný len v aktuálnom pracovnom priestore.

    *mcp.json*

    ```json
    "servers": {
        "APIM petstore" : {
            "type": "sse",
            "url": "url-to-mcp-server/sse"
        }
    }
    ```

    alebo ak zvolíte streaming HTTP ako transport, bude to mierne odlišné:

    ```json
    "servers": {
        "APIM petstore" : {
            "type": "http",
            "url": "url-to-mcp-server/mcp"
        }
    }
    ```

  - **Používateľské nastavenia** - Konfigurácia servera sa pridá do globálneho súboru *settings.json* a je dostupná vo všetkých pracovných priestoroch. Konfigurácia vyzerá približne takto:

    ![Používateľské nastavenie](https://learn.microsoft.com/en-us/azure/api-management/media/export-rest-mcp-server/mcp-servers-visual-studio-code.png)

1. Tiež musíte pridať konfiguráciu hlavičky, aby sa správne autentifikovalo voči Azure API Management. Používa sa hlavička nazvaná **Ocp-Apim-Subscription-Key**.

    - Tu je návod, ako ju pridať do nastavení:

    ![Pridanie hlavičky na autentifikáciu](https://learn.microsoft.com/en-us/azure/api-management/media/export-rest-mcp-server/mcp-server-with-header-visual-studio-code.png), táto akcia vyvolá výzvu na zadanie hodnoty API kľúča, ktorú nájdete v Azure portáli pre vašu inštanciu Azure API Management.

    - Ak ju chcete pridať priamo do *mcp.json*, môžete ju pridať takto:

    ```json
    "inputs": [
      {
        "type": "promptString",
        "id": "apim_key",
        "description": "API Key for Azure API Management",
        "password": true
      }
    ]
    "servers": {
        "APIM petstore" : {
            "type": "http",
            "url": "url-to-mcp-server/mcp",
            "headers": {
                "Ocp-Apim-Subscription-Key": "Bearer ${input:apim_key}"
            }
        }
    }
    ```

### Použitie režimu agenta

Teraz sme pripravení, či už v nastaveniach alebo v *.vscode/mcp.json*. Poďme to vyskúšať.

Mala by sa zobraziť ikona Nástrojov, kde sú uvedené sprístupnené nástroje z vášho servera:

![Nástroje zo servera](https://learn.microsoft.com/en-us/azure/api-management/media/export-rest-mcp-server/tools-button-visual-studio-code.png)

1. Kliknite na ikonu nástrojov a mali by ste vidieť zoznam nástrojov, napríklad takto:

    ![Nástroje](https://learn.microsoft.com/en-us/azure/api-management/media/export-rest-mcp-server/select-tools-visual-studio-code.png)

1. Zadajte príkaz do chatu na vyvolanie nástroja. Napríklad, ak ste vybrali nástroj na získanie informácií o objednávke, môžete agenta opýtať na objednávku. Tu je príklad príkazu:

    ```text
    get information from order 2
    ```

    Teraz sa zobrazí ikona nástrojov, ktorá vás vyzve na pokračovanie volania nástroja. Vyberte možnosť pokračovať v spustení nástroja, mali by ste vidieť výstup podobný tomuto:

    ![Výsledok z príkazu](https://learn.microsoft.com/en-us/azure/api-management/media/export-rest-mcp-server/chat-results-visual-studio-code.png)

    **To, čo vidíte vyššie, závisí od toho, aké nástroje ste nastavili, ale idea je, že dostanete textovú odpoveď ako vyššie.**


## Referencie

Tu je niekoľko zdrojov, kde sa môžete dozvedieť viac:

- [Návod na Azure API Management a MCP](https://learn.microsoft.com/en-us/azure/api-management/export-rest-mcp-server)
- [Python príklad: Bezpečné vzdialené MCP servery pomocou Azure API Management (experimentálne)](https://github.com/Azure-Samples/remote-mcp-apim-functions-python)

- [Laboratórium autorizácie MCP klienta](https://github.com/Azure-Samples/AI-Gateway/tree/main/labs/mcp-client-authorization)

- [Použitie rozšírenia Azure API Management pre VS Code na import a správu API](https://learn.microsoft.com/en-us/azure/api-management/visual-studio-code-tutorial)

- [Registrácia a objavovanie vzdialených MCP serverov v Azure API Center](https://learn.microsoft.com/en-us/azure/api-center/register-discover-mcp-server)
- [AI Gateway](https://github.com/Azure-Samples/AI-Gateway) Výborné repozitár, ktorý ukazuje mnohé AI schopnosti s Azure API Management
- [AI Gateway workshopy](https://azure-samples.github.io/AI-Gateway/) Obsahuje workshopy využívajúce Azure Portal, čo je skvelý spôsob, ako začať hodnotiť AI možnosti.

**Vyhlásenie o zodpovednosti**:  
Tento dokument bol preložený pomocou AI prekladateľskej služby [Co-op Translator](https://github.com/Azure/co-op-translator). Aj keď sa snažíme o presnosť, vezmite prosím na vedomie, že automatické preklady môžu obsahovať chyby alebo nepresnosti. Pôvodný dokument v jeho rodnom jazyku by mal byť považovaný za autoritatívny zdroj. Pre kritické informácie sa odporúča profesionálny ľudský preklad. Nie sme zodpovední za akékoľvek nedorozumenia alebo nesprávne interpretácie vyplývajúce z použitia tohto prekladu.