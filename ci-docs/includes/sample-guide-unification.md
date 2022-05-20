---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755538"
---
Nadat u de gegevens hebt opgenomen, begint u met het gegevensharmonisatieproces om een geharmoniseerd klantprofiel te maken. Zie [Gegevensharmonisatie](../data-unification.md) voor meer informatie.

### <a name="select-source-fields"></a>Bronvelden selecteren

1. Na het opnemen van de gegevens, wijst u contacten uit eCommerce en Loyaliteitsgegevens toe aan veelgebruikte gegevenstypen. Ga naar **Gegevens** > **Harmoniseren**.

1. Selecteer de entiteiten die het klantprofiel vertegenwoordigen: **eCommerceContacts** en **loyCustomers**.

   ![harmoniseer eCommerce- en loyaliteitsgegevensbronnen.](../media/unify-ecommerce-loyalty.png)

1. Selecteer **ContactId** als de primaire sleutel voor **eCommerceContacts** en **LoyaltyID** als de primaire sleutel voor **loyCustomers**.

1. Selecteer **Volgende**. Sla dubbele records over en selecteer **Volgende**.

### <a name="match-conditions"></a>Overeenkomstvoorwaarden

1. Kies **eCommerce: eCommerceContacts** als de primaire entiteit en neem alle records erin op.

1. Kies **loyCustomers: LoyaltyScheme** en neem alle records erin op.

1. Een regel toevoegen:
   - Selecteer **FullName** voor zowel eCommerceContacts als loyCustomers.
   - Selecteer **Type (telefoon, naam, adres, ...)** voor **Normaliseren**.
   - Stel **Precisieniveau**: **Basic** en **Waarde**: **Hoog** in.
   - Voer **FullName, Email** in voor de naam.

1. Voeg een tweede voorwaarde toe voor het e-mailadres:
   - Selecteer **Email** voor zowel eCommerceContacts als loyCustomers.
   - Laat Normaliseren leeg.
   - Stel **Precisieniveau**: **Basic** en **Waarde**: **Hoog** in.

   ![Harmoniseer de matchregel voor naam en e-mailadres.](../media/unify-match-rule.png)

1. Selecteer **Gereed**.

1. Selecteer **Volgende**.

### <a name="unify-fields"></a>Velden harmoniseren

1. Wijzig de naam van de **ContactId** voor de **loyCustomers**-entiteit in **ContactIdLOYALTY** om deze te onderscheiden van de andere opgenomen id's.

1. Selecteer **Volgende** om het te bekijken en selecteer vervolgens **Klantprofielen maken**.
