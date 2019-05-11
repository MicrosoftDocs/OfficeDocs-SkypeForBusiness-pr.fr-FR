---
title: Afficher des informations sur les jonctions SIP individuelles dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Résumé : Découvrez comment afficher des informations sur les jonctions SIP dans Skype pour Business Server.'
ms.openlocfilehash: a7cf290bf245092e08babcaa86c642dd0f0a4265
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892236"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Afficher des informations sur les jonctions SIP individuelles dans Skype pour Business Server
 
**Résumé :** Découvrez comment afficher des informations sur les jonctions SIP dans Skype pour Business Server.
  
Jonctions SIP sont utilisées pour se connecter Skype pour Business Server Voice via le réseau de téléphone IP avec le Public téléphone réseau commuté (RTC). Dans la version précédente du produit, jonctions ont été utilisées pour router les appels sortants à partir d’un serveur de médiation à une passerelle PSTN et chaque passerelle a été limitée à une seule jonction. Par conséquent, une passerelle PSTN et une jonction SIP ont été pratiquement identiques. Pour les administrateurs, qui signifie qu’ils peuvent afficher des informations sur une jonction SIP individuelle en simplement l’affichage des informations sur la passerelle PSTN associée.
  
Dans Skype pour Business Server, toutefois, plusieurs jonctions peuvent ensuite être attribuées à une seule passerelle PSTN ; Cela signifie que les passerelles et les jonctions ne sont plus les mêmes. À son tour, cela signifie que les administrateurs doivent utiliser l’applet de commande [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) nouveau afin d’afficher des informations sur une jonction SIP individuelle.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Pour afficher des informations sur toutes vos jonctions SIP

- La commande suivante retourne des informations relatives à toutes les jonctions SIP utilisées dans votre organisation :
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Pour afficher les informations relatives à une jonction SIP spécifique

- La commande suivante retourne uniquement les informations relatives à la jonction SIP ayant l’identité PstnGateway 192.168.0.240 :
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Affichage des informations relatives à toutes les jonctions SIP affectées à un pool

- Dans cet exemple, les informations relatives à toutes les jonctions SIP affectées au pool atl-cs-001.litwareinc.com sont retournées :
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
