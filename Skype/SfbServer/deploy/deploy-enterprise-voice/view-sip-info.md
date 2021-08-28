---
title: Afficher les informations de la trunk SIP dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Résumé : Découvrez comment afficher des informations sur les trunks SIP dans Skype Entreprise Server.'
ms.openlocfilehash: f4bd3ba4560980243fefe06b49a8f4aaa4a9625e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624406"
---
# <a name="skype-for-business-server-view-information-about-individual-sip-trunks"></a>Skype Entreprise Server : afficher des informations sur des trunks SIP individuelles 
 
**Résumé :** Découvrez comment afficher des informations sur les trunks SIP dans Skype Entreprise Server.
  
Les connexions SIP sont utilisées pour Skype Entreprise Server réseau téléphonique Voix sur IP avec le réseau téléphonique commuté (PSTN). Dans la version précédente du produit, les trunks étaient utilisées pour router les appels sortants d’un serveur de médiation vers une passerelle PSTN et chaque passerelle était limitée à une seule. Par conséquent, une passerelle PSTN et une trunk SIP étaient essentiellement identiques. Pour les administrateurs, cela signifie qu’ils peuvent afficher des informations sur une trunk SIP individuelle simplement en visualisant les informations sur la passerelle PSTN associée.
  
Dans Skype Entreprise Server, toutefois, plusieurs trunks peuvent désormais être affectés à une seule passerelle PSTN ; Cela signifie que les passerelles et les trunks ne sont plus identiques. Cela signifie que les administrateurs doivent utiliser la nouvelle cmdlet [Get-CsTrunk](/powershell/module/skype/get-cstrunk) pour afficher des informations sur une trunk SIP individuelle.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Pour afficher des informations pour toutes vos trunks SIP

- La commande suivante retourne des informations sur toutes les trunks SIP en cours d’utilisation dans votre organisation :
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Pour afficher les informations d’une trunk SIP spécifique

- Cette commande retourne des informations uniquement pour la trunk SIP dont l’identité est PstnGateway:192.168.0.240 :
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Afficher les informations de toutes les trunks SIP affectées à un pool

- Dans cet exemple, les informations sont retournées pour toutes les trunks SIP affectées au pool atl-cs-001.litwareinc.com :
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
