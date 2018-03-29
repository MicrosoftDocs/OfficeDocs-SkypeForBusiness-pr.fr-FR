---
title: Affichage des informations sur les différentes jonctions SIP (Session Initiation Protocol) dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Résumé : Découvrez comment afficher des informations sur les trunks SIP dans Skype pour Business Server 2015.'
ms.openlocfilehash: c307d4e9b18b7ff5fda8d8d0deaa4eb88ba5b6b0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server-2015"></a>Affichage des informations sur les différentes jonctions SIP (Session Initiation Protocol) dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment afficher des informations sur les trunks SIP dans Skype pour Business Server 2015.
  
PUITS SIP permettent de connecter Skype pour Business Server voix sur un réseau de téléphone IP avec la commutation de téléphone RTPC (réseau Public). Dans la version précédente du produit, malles ont été utilisés pour router les appels sortants à partir d’un serveur de médiation à une passerelle PSTN et chaque passerelle a été limitée à une seule ligne. Par conséquent, une passerelle PSTN et un SIP trunk étaient essentiellement identiques. Pour les administrateurs, cela signifiait qu’ils peuvent afficher des informations sur un SIP trunk individuel simplement par l’affichage d’informations sur la passerelle RTC associée.
  
Dans Skype pour Business Server, toutefois, plusieurs troncs peuvent ensuite être attribués à une passerelle PSTN unique ; Cela signifie que les passerelles et les puits y n’est plus les mêmes. À son tour, cela signifie que les administrateurs doivent utiliser l’applet de commande [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) nouveau afin d’afficher des informations sur un SIP trunk individuel.
  
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


