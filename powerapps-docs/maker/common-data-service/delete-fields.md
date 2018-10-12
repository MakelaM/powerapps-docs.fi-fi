---
title: Kenttien poistaminen PowerAppsissa | MicrosoftDocs
description: Opi poistamaan kenttiä
ms.custom: ''
ms.date: 06/20/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 578ac950-da16-4ec6-a0a4-25f3aaa3b96e
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: ''
ms.openlocfilehash: 82e560f063f2e46190420b6be5cef4cc55d9ab4f
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39676483"
---
# <a name="delete-fields"></a>Poista kenttiä

<a name="BKMK_DeletingFields"></a>   
 
 Jos sinulla on järjestelmän järjestelmänvalvojan rooli, voit poistaa mukautettuja kenttiä, jotka eivät ole osa hallittua ratkaisua. Kun poistat kentän, kentän tallennetut tiedot menetetään. Ainoa tapa palauttaa poistetun kentän tietoja on palauttaa tietokanta kentän poistamista edeltävästä kohdasta.  
  
 Ennen kuin voit poistaa mukautetun kentän, sinun on poistettava kaikki riippuvuussuhteet muissa ratkaisun osissa. Avaa kenttä ja paina **Näytä riippuvuudet** -painiketta valikkorivillä, niin **Riippuvaiset osat** tulee näkyviin. Jos kenttää käytetään esimerkiksi lomakkeessa tai näkymässä, sinun on ensin poistettava kentän viittauksen kyseisistä ratkaisun osista.  
  
 Jos poistat hakukentän, sen 1:N-entiteettisuhde poistetaan automaattisesti.  

 ## <a name="next-steps"></a>Seuraavat vaiheet

 [Poista mukautettu entiteetti](data-platform-delete-entity.md)
