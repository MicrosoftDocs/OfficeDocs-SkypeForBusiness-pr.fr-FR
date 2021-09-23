---
title: Configurer la connectivité hybride | Déployer Skype Entreprise Server 2019 connect
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instructions pour l’implémentation de la connectivité hybride entre Skype Entreprise Server et Teams.
ms.openlocfilehash: 272166852ef86da6318aa5fa2908697a93d65e02
ms.sourcegitcommit: b2566e64e02cb51d18836630d3aa9b6f27b924da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59491694"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Configurer la connectivité hybride entre Skype Entreprise Server et Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**Résumé :** Lisez cette rubrique pour découvrir comment configurer la connectivité hybride entre Skype Entreprise Server et Teams.  La connectivité hybride vous permet de déplacer vos utilisateurs locaux vers Teams, et permet à vos utilisateurs de tirer parti des services cloud.
  
Avant d’effectuer les étapes de [cette](plan-hybrid-connectivity.md)rubrique, vous devez avoir lu Planifier la connectivité hybride entre Skype Entreprise Server et Teams .
  
Le tableau suivant répertorie les tâches requises pour configurer Skype Entreprise connectivité hybride et fournit des liens vers les articles associés pour plus d’informations.
  
|Étape|Description|
|:-----|:-----|
|Créer un compte de client pour Microsoft 365.   <br/> |Pour en savoir Microsoft 365, [Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Pour vous assurer que votre environnement est prêt pour la Microsoft 365, consultez la [system requirements](https://products.office.com/office-system-requirements).  <br/> Pour plus d’informations sur la configuration Microsoft 365, voir [Getting Started with Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Ajoutez votre domaine à votre Microsoft 365 organisation et vérifiez la propriété.  <br/> | Vous devez ajouter votre domaine à votre organisation Microsoft 365, puis suivre les étapes pour valider le domaine avec Microsoft 365. Cette validation consiste à confirmer que vous êtes le propriétaire du domaine. <br/> Pour ajouter votre domaine à votre organisation Microsoft 365, suivez les étapes décrites dans Ajouter un domaine [à Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US). N’oubliez pas de consulter les instructions ci-dessous concernant les [implications DNS pour les organisations qui deviennent hybrides.](#dns-implications-for-on-premises-organizations-that-become-hybrid) <br/> |
|Configurer la synchronisation Active Directory.  <br/> |La synchronisation Active Directory garantit que votre annuaire Active Directory local est en permanence synchronisé avec Microsoft 365 afin que vous créez des versions synchronisées de chaque compte d’utilisateur et groupe.  <br/> <br> **Important :** Vous devez synchroniser les comptes Active Directory pour tous les utilisateurs Skype Entreprise de votre organisation entre vos déploiements locaux et en ligne, même si les utilisateurs ne sont pas déplacés vers Teams. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et en ligne de votre organisation risque de ne pas fonctionner comme prévu. Pour plus d’informations, [voir Configurer azure ad Connecter pour les environnements hybrides.](configure-azure-ad-connect.md)         |
| Configurer Skype Entreprise hybride. | Il existe trois étapes de base : <br><br> 1. Configurez votre environnement local pour la fédération avec Microsoft 365. <br> 2. Configurez votre environnement local pour qu’il Microsoft 365 et activez l’espace d’adressare SIP partagé avec Microsoft 365.<br> 3. Activez l’espace d’adressare SIP partagé dans Microsoft 365 organisation. <br><br> En outre, si vous Exchange en local, vous pouvez configurer OAuth entre vos environnements Exchange local et en ligne. <br> <br>Pour plus d’informations, [voir Configurer Skype Entreprise hybride.](configure-federation-with-skype-for-business-online.md)
|Déplacer les utilisateurs pilotes.  <br/> |Une fois que vous avez effectué les étapes de préparation et de configuration de votre environnement pour Teams, vous pouvez commencer à déplacer des utilisateurs pilotes vers votre organisation Microsoft 365 en ligne. Pour plus d’informations, voir [Move users from on premises to Teams](move-users-from-on-premises-to-Teams.md).  <br/> |


## <a name="dns-implications-for-on-premises-organizations-that-become-hybrid"></a>Implications DNS pour les organisations locales qui deviennent hybrides

Par défaut, les locataires sont créés en mode TeamsOnly. Les administrateurs ne peuvent pas modifier cette configuration. Toutefois, les organisations hybrides ne doivent pas être en mode TeamsOnly, car cela rompreait la fédération pour leurs utilisateurs locaux. Teams dispose d’un mécanisme intégré pour s’assurer que la configuration TeamsOnly à l’échelle du client n’est pas appliquée aux nouveaux clients hybrides et qu’elle n’est pas supprimée des clients existants qui deviennent hybrides. Ce mécanisme est basé sur la valeur d’un enregistrement DNS LyncDiscover pour tout domaine Microsoft 365 vérifié (car un déploiement Skype Entreprise Server local aura dans la plupart des cas cet enregistrement), comme décrit ci-dessous.

Lorsqu’un nouvel Microsoft 365 est d’abord traitée, les opérations suivantes se produisent :
- S’il n’existe pas encore de Microsoft 365 vérifiés, le client est créé en mode TeamsOnly. La valeur est définie par le biais de TeamsUpgradeOverridePolicy, qui peut uniquement être définie par Microsoft. Si la valeur de stratégie est UpgradeToTeams, elle est prioritaire sur n’importe quelle valeur de TeamsUpgradePolicy.
- S’il existe des domaines Microsoft 365 vérifiés, mais qu’aucun enregistrement DNS lyncDiscover public n’est détecté, ou si des enregistrements LyncDiscover détectés pointent tous vers Microsoft 365 (sipfed.online.lync.com, sipfed.online.gov.skypeforbusiness.us, etc.), le client est créé en mode TeamsOnly (via TeamsUpgradeOverridePolicy).
- S’il existe au moins un domaine Microsoft 365 vérifié pour lequel un enregistrement LyncDiscover est détecté et que cet enregistrement pointe ailleurs que Microsoft 365, le client est créé en mode îles.

Lorsqu’un client Microsoft 365 existant est réapprovisionnement (généralement en raison d’une modification dans les domaines vérifiés ou dans les détails de l’abonnement), les problèmes suivants se produisent :
- Si un enregistrement LyncDiscover est trouvé pour un ou plusieurs domaines vérifiés Microsoft 365 et que cet enregistrement ne pointe pas vers Microsoft 365, le mode TeamsOnly à l’échelle du client (via TeamsUpgradeOverridePolicy) est supprimé. Le mode client revient à ce qui est spécifié au niveau du client pour TeamsUpgradePolicy, qui, par défaut, est le mode Îles.


Il existe certaines limitations pour ce mécanisme de détection automatique :
- Si votre organisation n’a pas d’enregistrements DNS publics, le mode TeamsOnly ne sera pas supprimé dans la mesure où Microsoft 365 ne sera pas en mesure de détecter les enregistrements. Si votre organisation dispose d’une Skype Entreprise Server sur site sans entrée DNS publique, vous devez contacter le Support Microsoft pour que votre client soit rétrogradé.
- Si vous ajoutez/mettez à jour un enregistrement  DNS public dans un domaine qui est déjà un domaine Microsoft 365 vérifié, cette modification DNS n’est pas détectée et le mode TeamsOnly n’est pas supprimé. Le mode TeamsOnly n’est supprimé que si le client est réapprovisionnement, ce qui se produit généralement en cas de modification de Microsoft 365 domaines vérifiés ou de l’abonnement.  
