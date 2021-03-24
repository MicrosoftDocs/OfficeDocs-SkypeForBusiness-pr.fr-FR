---
title: Tester les paramètres de configuration des trunks SIP dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Résumé : Découvrez comment tester les paramètres de configuration des trunks SIP à l’aide de Skype Entreprise Server Management Shell.'
ms.openlocfilehash: 6f569c7e397e7902cb347e13b4077acb5a9b34fb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103370"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Tester les paramètres de configuration des trunks SIP dans Skype Entreprise Server
 
**Résumé :** Découvrez comment tester les paramètres de configuration des trunks SIP à l’aide de Skype Entreprise Server Management Shell.
  
Les paramètres de configuration de la trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un PBX (IP-Public Branch eXchange) ou un contrôleur SBC (Session Border Controller) chez le fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :
  
- L’activation ou non du contournement de média sur les jonctions.
    
- Conditions dans lesquelles les paquets RTCP (Realtime Transport Control Protocol) sont envoyés.
    
- Si le chiffrement SRTP (Secure Realtime Transport Protocol) est requis sur chaque trunk.
    
Lorsque vous installez Skype Entreprise Server, une collection globale de paramètres de configuration de la trunk SIP est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement). Les administrateurs peuvent également utiliser l’applet de commande Test-CsTrunkConfiguration pour vérifier qu’une jonction peut convertir un numéro composé par un utilisateur en numéro pouvant être traité par la passerelle.
  
Les paramètres de configuration de jonction peuvent uniquement être testés à l’aide de Windows PowerShell et de l’applet de commande [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps). Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante de Skype Entreprise Server Management Shell.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Pour tester les paramètres de configuration de la trunk SIP

- Cette commande vérifie que les paramètres de configuration de jonction pour le site Redmond peuvent convertir de façon correcte le numéro composé 4255551212.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```