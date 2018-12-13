---
title: Mettre à jour le certificat de serveur edge
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Cette annexe inclut des procédures détaillées pour mettre à jour le certificat de serveur edge dans le cadre de la consolidation de cloud pour les équipes et Skype pour les entreprises.
ms.openlocfilehash: bd7707add0962a827373f1d07de9f8f8f9d3ec7c
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247638"
---
# <a name="update-the-edge-certificate"></a>Mettre à jour le certificat de serveur edge

Mise à jour le certificat de serveur edge est l’étape clé pour garantir un environnement sur prem avec SipDomain1 permettre participer à un environnement de cloud avec SipDomain2 et garantir un routage correct dans un environnement d’espace d’adressage partagé entre les deux domaines SIP. Voir l’étape 14 de [consolidation de Cloud pour les équipes et Skype pour les entreprises](cloud-consolidation.md) pour le contexte dans lequel vous pouvez effectuer cette étape. Dans nos exemples, SipDomain1 est AcquiredCompany. <span>com et SipDomain2 est OriginalCompany. <span>com.

L’autre nom du sujet (SAN) du certificat sur tous les serveurs de périphérie dans l’environnement local doit être mis à jour pour inclure tous les domaines SIP qui existent dans le client en ligne pur (à l’exclusion de n’importe quel onmicrosoft.<span> domaines com), sous la forme « sip. \<domaine > ».  Dans notre exemple, il s’agit d’un sip. OriginalCompany. <span>com. Cette étape est essentielle à effectuer avant de migrer des utilisateurs vers le nuage.

**Étapes suivantes :**

1.  Obtenir un nouveau certificat de serveur Edge externe du bord qui possède des entrées supplémentaires ainsi que toutes les entrées SAN pour tous les domaines SIP dans l’environnement cloud (à l’exclusion de *. onmicrosoft.com domaines) sous la forme « sip. <DomainName>».
2.  Installer le certificat localement sur chaque serveur edge et l’assigner au service Skype Edge sur chacun du service edge.  Pour obtenir la procédure détaillée, voir la section « Certificats d’interface externe Edge » dans [Déployer le Service Edge dans Skype pour Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).
3.  Redémarrez le service Edge sur chacun des serveurs de périphérie. Vous pouvez le faire pour une seule boîte avec les commandes PowerShell suivantes :

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Voir aussi

[Consolidation de cloud pour les équipes et Skype pour les entreprises](cloud-consolidation.md)