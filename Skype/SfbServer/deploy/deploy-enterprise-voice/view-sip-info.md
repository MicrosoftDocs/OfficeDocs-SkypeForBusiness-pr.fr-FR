---
title: Afficher des informations sur les circuits SIP individuels dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Résumé : Découvrez comment afficher des informations sur les ISL SIP dans Skype entreprise Server.'
ms.openlocfilehash: f67fe998408b9c99311f1a86c35e08200de99431
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766927"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Afficher des informations sur les circuits SIP individuels dans Skype entreprise Server
 
**Résumé :** Découvrez comment afficher des informations sur les ISL SIP dans Skype entreprise Server.
  
Les circuits SIP sont utilisés pour connecter le réseau téléphonique commuté de Skype entreprise Server à l’aide du réseau téléphonique public commuté (RTC). Dans la version précédente du produit, les Trunks permettaient le routage des appels sortants d’un serveur de médiation vers une passerelle RTC et chaque passerelle était limitée à un seul Trunk. Par conséquent, une passerelle RTC et un Trunk SIP étaient essentiellement identiques. Pour les administrateurs, cela signifie qu’ils pouvaient afficher les informations relatives à une ligne SIP individuelle en consultant les informations relatives à la passerelle RTC associée.
  
Dans Skype entreprise Server, il est désormais possible d’attribuer plusieurs Trunks à une seule passerelle PSTN. Cela signifie que les passerelles et les liaisons ne sont plus une seule et même. Cela signifie que les administrateurs doivent utiliser la nouvelle applet de commande [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) pour afficher des informations sur un Trunk SIP individuel.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Pour afficher des informations sur toutes vos jonctions SIP

- La commande suivante retourne des informations relatives à toutes les jonctions SIP utilisées dans votre organisation :
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Pour afficher les informations relatives à une jonction SIP spécifique

- La commande suivante retourne uniquement les informations relatives à la jonction SIP ayant l’identité PstnGateway 192.168.0.240 :
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Affichage des informations relatives à toutes les jonctions SIP affectées à un pool

- Dans cet exemple, les informations relatives à toutes les jonctions SIP affectées au pool atl-cs-001.litwareinc.com sont retournées :
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
