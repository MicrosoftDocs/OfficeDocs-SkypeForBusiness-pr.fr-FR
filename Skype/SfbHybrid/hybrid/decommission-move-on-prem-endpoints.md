---
title: Migrer des points de terminaison d’application hybride vers le cloud
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
description: Migrez les points de terminaison d’application hyrid avant de désaffecter Skype Entreprise environnement local.
ms.openlocfilehash: 74e0ef935c993f6e39b08759d3beb69e0c5c7673
ms.sourcegitcommit: d8dba15c520de3894d1781e17acb2c75fb38ed49
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2022
ms.locfileid: "62921852"
---
# <a name="migrate-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>Migrer des points de terminaison d’application hybride avant de désaffecter votre environnement local

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Cet article explique comment déplacer les points de terminaison d’application hybride requis vers le cloud Microsoft avant de désaffecter votre environnement Skype Entreprise local. Il s’agit de l’étape 3 des étapes suivantes pour désaffecter votre environnement local :

- Étape 1. [Déplacer tous les utilisateurs requis de l’local vers le réseau en ligne](decommission-move-on-prem-users.md)

- Étape 2. [Désactivez votre configuration hybride](cloud-consolidation-disabling-hybrid.md).

- **Étape 3. Migrez les points de terminaison de l’application hybride de l’local vers le mode en ligne.** (Cet article)

- Étape 4. [Supprimez votre déploiement de Skype Entreprise local](decommission-remove-on-prem.md).


## <a name="migrate-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>Migrer tous les points de terminaison d’application hybride requis de l’local vers le mode en ligne

Avant de pouvoir déplacer ces points de terminaison en ligne, vous devez vous assurer que vous avez mis à jour les enregistrements DNS pour qu’ils pointent vers Microsoft 365 pour tous les domaines sip utilisés par les points de terminaison. N’ignorez pas qu’une fois que vous mettez à jour le DNS pour qu’il pointe vers Microsoft 365, tous les points de terminaison d’application hybride existants ne seront plus découvrables tant que vous n’aurez pas terminé cette étape. Étant donné que cette étape (création de comptes de ressources en ligne) n’est pas possible si les enregistrements DNS pointent vers l’environnement local, vous devez planifier les deux étapes 2 et 3 dans la même fenêtre de maintenance. Pour plus d’informations, voir [Désactiver votre configuration hybride](cloud-consolidation-disabling-hybrid.md).

1. Récupérez et exportez les paramètres du point de terminaison de l’application hybride sur site en exécutant la commande PowerShell Skype Entreprise Server suivante :

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. Créez et licensez [de](/microsoftteams/manage-resource-accounts) nouveaux comptes de Microsoft 365 pour remplacer les points de terminaison d’application hybride locaux existants.

3. Associez les nouveaux comptes de ressources aux points de terminaison d’application hybride existants.

4. Supprimez les numéros de téléphone définis dans les points de terminaison de l’application hybride sur site en exécutant la commande PowerShell Skype Entreprise Server suivante :

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. Étant donné qu’il est possible que les numéros de téléphone de ces comptes ont été gérés en Microsoft 365 plutôt qu’en local, exécutez la commande suivante dans Teams PowerShell :

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. Affectez des numéros de téléphone aux nouveaux comptes de ressources créés à l’étape 2. Pour plus d’informations sur l’affectation d’un numéro de téléphone à un compte de ressource, voir l’article suivant : [Affecter un numéro de service](/microsoftteams/manage-resource-accounts).

7. Supprimez les points de terminaison locaux en exécutant la commande PowerShell Skype Entreprise Server suivante :

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
Vous êtes maintenant prêt à [supprimer votre déploiement local Skype Entreprise déploiement](decommission-remove-on-prem.md).

## <a name="see-also"></a>Voir aussi

- [Mise hors service de votre environnement Skype pour entreprises sur site](decommission-on-prem-overview.md)

- [Déplacer tous les utilisateurs requis de l’local vers le réseau en ligne](decommission-move-on-prem-users.md)

- [Désactiver votre configuration hybride](cloud-consolidation-disabling-hybrid.md)

- [Supprimez votre déploiement sur site de Skype pour entreprises.](decommission-remove-on-prem.md)

- [Créer un attendant automatique via des cmdlets](/microsoftteams/create-a-phone-system-auto-attendant-via-cmdlets)




