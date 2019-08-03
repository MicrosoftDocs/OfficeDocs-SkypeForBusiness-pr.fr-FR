---
title: Mettre à jour le certificat de serveur Edge
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Cette annexe inclut des étapes détaillées pour mettre à jour le certificat de serveur Edge dans le cadre de la consolidation du Cloud pour teams et Skype entreprise.
ms.openlocfilehash: 1c3aaa8859db530ceccbebc68ae76f21e8d4a77f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160519"
---
# <a name="update-the-edge-certificate"></a>Mettre à jour le certificat de serveur Edge

La mise à jour du certificat de serveur Edge est l’étape essentielle pour s’assurer qu’un environnement local avec SipDomain1 peut rejoindre un environnement Cloud avec SipDomain2 et garantir le routage approprié dans un environnement d’espace d’adressage partagé dans les deux domaines SIP. Reportez-vous à l’étape 14 dans [consolidation du Cloud pour teams et Skype entreprise](cloud-consolidation.md) pour le contexte dans lequel vous pouvez effectuer cette étape. Dans nos exemples, SipDomain1 est AcquiredCompany. <span>com et SipDomain2 sont OriginalCompany. <span>com.

L’autre nom de l’objet (SAN) du certificat sur tous les serveurs Edge de l’environnement local doit être mis à jour pour inclure tous les domaines SIP existant dans le client pur en ligne (à<span> l’exclusion des onmicrosoft. domaines com), au format «SIP. \<> de domaine».  Dans notre exemple, il s’agit de SIP. OriginalCompany. <span>com. Cette étape est essentielle avant de migrer des utilisateurs vers le Cloud.

**Étapes :**

1.  Obtenir un nouveau certificat de serveur Edge externe pour le serveur Edge qui dispose de toutes les entrées existantes, ainsi que des entrées supplémentaires dans le SAN pour tous les domaines SIP dans l’environnement Cloud (à l’exception des domaines *. onmicrosoft.com) au format «SIP. <DomainName>».
2.  Installez le certificat localement sur chaque serveur Edge et affectez-le au service Edge Skype sur chaque service Edge.  Pour obtenir la procédure détaillée, voir la section «certificats d’interface Edge externe» dans [Deploy Edge service dans Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).
3.  Redémarrez le service Edge sur chaque serveur Edge. Vous pouvez effectuer cette opération pour une zone unique avec les commandes PowerShell suivantes:

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Voir aussi

[Consolidation du Cloud pour teams et Skype entreprise](cloud-consolidation.md)