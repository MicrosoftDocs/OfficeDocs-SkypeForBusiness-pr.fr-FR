---
title: Tester les paramètres de configuration de jonction SIP dans Skype pour Business Server
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
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Résumé : Découvrez comment tester les paramètres de configuration de jonction SIP à l’aide de la Skype pour Business Server Management Shell.'
ms.openlocfilehash: fb782ddefbf3930e5e2122724adf729ef63c05dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892278"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Tester les paramètres de configuration de jonction SIP dans Skype pour Business Server
 
**Résumé :** Découvrez comment tester les paramètres de configuration de jonction SIP à l’aide de la Skype pour Business Server Management Shell.
  
Les paramètres de configuration de jonction SIP (Session Initiation Protocol) définissent la relation et les possibilités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (RTC), un autocommutateur privé IP (PBX) ou le contrôleur SBC (Session Border Controller) du côté fournisseur de services. Ces paramètres spécifient, par exemple :
  
- si la déviation du trafic multimédia doit être activée sur les jonctions ;
    
- les conditions dans lesquelles les paquets RTCP sont envoyés ;
    
- si le chiffrement SRTP (Secure Real-Time Protocol ) est requis ou non sur chaque jonction.
    
Lorsque vous installez Skype pour Business Server, une collection de paramètres de configuration de jonction SIP globale est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement). Les administrateurs peuvent également utiliser l’applet de commande Test-CsTrunkConfiguration pour vérifier qu’une jonction peut convertir un numéro composé par un utilisateur en numéro pouvant être traité par la passerelle.
  
Les paramètres de configuration de jonction peuvent uniquement être testés à l’aide de Windows PowerShell et de l’applet de commande [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps). Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou depuis une session distante de Skype pour Business Server Management Shell.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Pour tester les paramètres de configuration des jonctions SIP

- Cette commande vérifie que les paramètres de configuration de jonction pour le site Redmond peuvent convertir correctement le numéro composé 4255551212.
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


