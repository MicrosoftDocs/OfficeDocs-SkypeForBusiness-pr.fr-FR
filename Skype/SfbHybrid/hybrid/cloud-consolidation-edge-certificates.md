---
title: Mettre à jour le certificat de Microsoft Edge
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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
description: Cette annexe comprend des étapes détaillées pour la mise à jour du certificat Edge dans le cadre de la consolidation du cloud pour Teams et Skype Entreprise.
ms.openlocfilehash: bb8d2eabf17d83546737d3d94fb4add5dc0a892e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857111"
---
# <a name="update-the-edge-certificate"></a>Mettre à jour le certificat de Microsoft Edge

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


La mise à jour du certificat edge est l’étape clé pour s’assurer qu’un environnement local avec SipDomain1 peut rejoindre un environnement cloud avec SipDomain2 et garantir un routage correct dans un environnement d’espace d’adressas partagé entre les deux domaines SIP. Consultez l’étape 14 de la consolidation cloud [pour Teams et Skype Entreprise](cloud-consolidation.md) pour le contexte dans lequel vous pouvez effectuer cette étape. Dans nos exemples, SipDomain1 est AcquiredCompany. <span> com et SipDomain2 est OriginalCompany. <span> com.

L’autre nom de sujet (SAN) du certificat sur tous les serveurs Edge de l’environnement local doit être mis à jour pour inclure tous les domaines SIP existant dans le client en ligne pur (à l’exception de toute onmicrosoft. <span> com domains), sous la forme « sip. \<domain> ».  Dans notre exemple, il s’agit de sip. OriginalCompany. <span> com. Cette étape est essentielle avant de migrer des utilisateurs vers le cloud.

**Étapes :**

1.  Obtenez un nouveau certificat Edge externe pour le edge qui possède toutes les entrées existantes, ainsi que des entrées supplémentaires dans le SAN pour tous les domaines SIP dans l’environnement cloud (à l’exception des domaines *.onmicrosoft.com) sous la forme `sip.<DomainName>` .
2.  Installez le certificat localement sur chaque serveur Edge et affectez-le au service Edge Skype sur chacun d’eux.  Pour obtenir la procédure détaillée, consultez la section « Certificats d’interface Edge externe » dans [Deploy Edge Service in Skype Entreprise Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).
3.  Redémarrez le service Edge sur chacun des serveurs Edge. Vous pouvez le faire pour une zone unique avec les commandes PowerShell suivantes :

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Voir aussi

[Consolidation du cloud pour Teams et Skype Entreprise](cloud-consolidation.md)