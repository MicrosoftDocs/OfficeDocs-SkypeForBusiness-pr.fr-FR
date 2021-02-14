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
localization_priority: Normal
description: Cette annexe comprend des étapes détaillées pour la mise à jour du certificat Edge dans le cadre de la consolidation du cloud pour Teams et Skype Entreprise.
ms.openlocfilehash: 3e6b151e340a0942b561edd2233795fad94c3a9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888603"
---
# <a name="update-the-edge-certificate"></a>Mettre à jour le certificat de Microsoft Edge

La mise à jour du certificat edge est l’étape clé pour s’assurer qu’un environnement local avec SipDomain1 peut rejoindre un environnement cloud avec SipDomain2 et garantir un routage correct dans un environnement d’espace d’adressas partagé entre les deux domaines SIP. Consultez l’étape 14 de [la consolidation cloud](cloud-consolidation.md) pour Teams et Skype Entreprise pour le contexte dans lequel vous pouvez effectuer cette étape. Dans nos exemples, SipDomain1 est AcquiredCompany. <span> com et SipDomain2 est OriginalCompany. <span> com.

L’autre nom de sujet (SAN) du certificat sur tous les serveurs Edge dans l’environnement local doit être mis à jour pour inclure tous les domaines SIP existant dans le client en ligne pur (à l’exception de toute onmicrosoft. <span> com domains), sous la forme « sip. \< domaine> ».  Dans notre exemple, il s’agit de sip. OriginalCompany. <span> com. Cette étape est essentielle avant de migrer des utilisateurs vers le cloud.

**Procédure :**

1.  Obtenez un nouveau certificat Edge externe pour le edge qui possède toutes les entrées existantes, ainsi que des entrées supplémentaires dans le SAN pour tous les domaines SIP dans l’environnement cloud (à l’exception des domaines *.onmicrosoft.com) sous la forme « sip. ». <DomainName>
2.  Installez le certificat localement sur chaque serveur Edge et affectez-le au service Skype Edge sur chacun d’eux.  Pour obtenir la procédure détaillée, voir la section « Certificats d’interface Edge externe » dans [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).
3.  Redémarrez le service Edge sur chacun des serveurs Edge. Vous pouvez le faire pour une zone unique avec les commandes PowerShell suivantes :

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Voir aussi

[Consolidation du cloud pour Teams et Skype Entreprise](cloud-consolidation.md)