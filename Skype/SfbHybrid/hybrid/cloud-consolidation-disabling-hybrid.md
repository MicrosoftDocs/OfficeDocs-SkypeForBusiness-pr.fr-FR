---
title: Désactiver l'hybride pour achever la migration vers Teams uniquement
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
description: Cet article comprend des étapes détaillées pour la désactivation de l’hybride dans le cadre de la consolidation du cloud pour Teams et Skype Entreprise.
ms.openlocfilehash: 06d8980a14944004b22fbacc0aecef453d49123e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619310"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a>Désactiver votre configuration hybride pour terminer la migration vers Teams uniquement 

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Cet article explique comment désactiver votre configuration hybride avant de désaffecter votre environnement Skype Entreprise local. Il s’agit de l’étape 2 des étapes suivantes pour désaffecter votre environnement local :

- Étape 1. [Déplacez tous les utilisateurs requis de l’local vers le site en ligne.](decommission-move-on-prem-users.md)

- **Étape 2. Désactivez votre configuration hybride.** (Cet article)

- Étape 3. [Migrez les points de terminaison de l’application hybride de l’local vers le mode en ligne.](decommission-move-on-prem-endpoints.md)

- Étape 4. [Supprimez votre déploiement Skype Entreprise local.](decommission-remove-on-prem.md)

> [!NOTE]
> Les étapes 2 et 3 doivent être réalisées dans la même fenêtre de maintenance, car les points de terminaison d’application hybride existants ne seront pas découvrables entre les étapes 2 et la fin de l’étape 3.


## <a name="summary"></a>Résumé

Une fois que vous avez mis à niveau tous les utilisateurs de Skype Entreprise en local vers Teams Uniquement en Microsoft 365, vous pouvez désaffecter le déploiement Skype Entreprise local.

Avant de désaffecter le déploiement Skype Entreprise local et de supprimer du matériel, vous devez séparer logiquement le déploiement local de Microsoft 365 en désactivant l’hybride. La désactivation hybride se compose des quatre étapes suivantes :

1. [Mettez à jour les enregistrements DNS pour qu’ils pointent vers Microsoft 365](#update-dns-to-point-to-microsoft-365).

2. [Modifiez le mode de coexistence de votre](#change-the-coexistence-mode-for-your-organization-to-teams-only)organisation en Teams uniquement.

3. [Désactivez l’espace d’adressa ment sip partagé (également](#disable-shared-sip-address-space-in-microsoft-365-organization)appelé « domaine fractioné ») dans l’Microsoft 365.

4. [Désactiver la communication entre les locaux et les Microsoft 365](#disable-communication-between-on-premises-and-microsoft-365)

Ces étapes séparent logiquement votre déploiement local de Skype Entreprise Server de Microsoft 365 et assurez-vous que votre organisation est entièrement Teams uniquement. Une fois ces étapes terminées, vous pouvez désaffecter votre déploiement Skype Entreprise local à l’aide de l’une des deux méthodes référencés dans [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).

> [!Important] 
> Une fois cette séparation logique terminée, les attributs msRTCSIP de votre active Directory local ont toujours des valeurs et continueront à se synchroniser via Azure AD Connecter dans Azure AD. La façon dont vous désaffectez l’environnement local varie selon que vous avez l’intention de laisser ces attributs en place ou de les effacer d’abord de votre environnement Active Directory local. Sachez que l’effacement des attributs msRTCSIP locaux une fois que vous avez migré à partir de l’local peut entraîner une perte de service pour les utilisateurs ! Les détails et les compromis des deux approches de désaffectation sont décrits dans [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).

## <a name="update-dns-to-point-to-microsoft-365"></a>Mettre à jour le DNS pour qu’il pointe vers Microsoft 365

Le DNS externe de l’organisation pour l’organisation sur site doit être mis à jour afin que les enregistrements Skype Entreprise pointent vers Microsoft 365 au lieu du déploiement local. 

En outre, les enregistrements CNAME pour la meet ou dialin (le cas présent) peuvent être supprimés. Enfin, tous les enregistrements DNS Skype Entreprise votre réseau interne doivent être supprimés.

Pour plus d’informations sur la mise à jour des enregistrements DNS, voir Mettre à jour les entrées [DNS](decommission-manage-dns-entries.md)pour permettre à votre organisation d’être Teams uniquement.

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a>Modifier le mode de coexistence de votre organisation en mode Teams uniquement

Cette étape garantit que tout nouvel utilisateur de votre organisation est toujours créé en tant qu’Teams utilisateur uniquement. 

Si vous tentez de modifier le mode client en mode Teams Seul vérifie automatiquement l’existence d’enregistrements DNS locaux qui ont pu être manqués à l’étape 1 et identifie ces enregistrements dans la sortie. Si vous modifiez le mode client Teams seul ne réussira pas tant que tous les enregistrements DNS de votre organisation n’auront pas été mis à jour. 

Pour modifier le mode client en mode Teams exécutez uniquement la commande suivante à partir d’Teams fenêtre PowerShell.

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

Vous pouvez également utiliser le Centre d’administration Teams pour modifier le mode de coexistence client en TeamsOnly, sous « Paramètres à l’échelle de l’organisation » -> « Mise à niveau Teams client ».    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a>Désactiver l’espace d’adressaie sip partagé dans Microsoft 365 organisation
    
Pour désactiver l’espace d’adressale sip partagé, exécutez la commande suivante à partir d’Teams fenêtre PowerShell.

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a>Désactiver la communication entre les locaux et les Microsoft 365

Pour désactiver la communication entre l’environnement local et Microsoft 365, exécutez la commande suivante à partir d’une fenêtre PowerShell sur site :

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a>Voir aussi

- [Consolidation du cloud pour Teams et Skype Entreprise](cloud-consolidation.md)

- [Mise hors service de votre environnement Skype pour entreprises sur site](decommission-on-prem-overview.md)

