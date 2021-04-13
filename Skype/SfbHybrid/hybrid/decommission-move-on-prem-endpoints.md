---
title: Déplacer des points de terminaison d’application hybride vers le cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Déplacez les points de terminaison d’application hyrid avant de désaffecter un environnement Skype Entreprise local.
ms.openlocfilehash: af8b521eaaf4a1e86027936f3d4d3600ab4bfa7b
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656878"
---
# <a name="move-hyrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>Déplacer des points de terminaison d’application hyrid avant de désaffecter votre environnement local

Cet article explique comment déplacer les points de terminaison d’application hybride requis vers le cloud Microsoft avant de désaffecter votre environnement Skype Entreprise local. Il s’agit de l’étape 3 des étapes suivantes pour désaffecter votre environnement local :

- Étape 1. [Déplacer tous les utilisateurs requis de l’local vers le site en ligne](decommission-move-on-prem-users.md)

- Étape 2. [Désactivez votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)

- **Étape 3. Déplacez les points de terminaison de l’application hybride de l’local vers le mode en ligne.** (Cet article)

- Étape 4. [Supprimez votre déploiement Skype Entreprise local.](decommission-remove-on-prem.md)


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>Déplacer tous les points de terminaison d’application hybride requis de l’local vers le mode en ligne

Avant de pouvoir déplacer ces points de terminaison en ligne, vous devez vous assurer que vous avez mis à jour les enregistrements DNS pour qu’ils pointent vers Microsoft 365 pour tous les domaines sip utilisés par les points de terminaison. Il n’est pas possible de créer des comptes de ressources en ligne si les enregistrements DNS pointent vers l’environnement local. Pour plus d’informations, [voir Désactiver votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)

1. Récupérez et exportez les paramètres du point de terminaison de l’application hybride sur site en exécutant la commande PowerShell Skype Entreprise Server sur site suivante :

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. Créez et licensez [de nouveaux](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) comptes de ressources dans Microsoft 365 pour remplacer les points de terminaison d’application hybride locaux existants.

3. Associez les nouveaux comptes de ressources aux points de terminaison d’application hybride existants.

4. Supprimez les numéros de téléphone définis dans les points de terminaison de l’application hybride sur site en exécutant la commande PowerShell Skype Entreprise Server sur site suivante :

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. Étant donné qu’il est possible que les numéros de téléphone de ces comptes ont été gérés dans Microsoft 365 plutôt que sur site, exécutez la commande suivante dans Skype Entreprise Online PowerShell :

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

6. Affectez des numéros de téléphone aux nouveaux comptes de ressources créés à l’étape 2. Pour plus d’informations sur l’affectation d’un numéro de téléphone à un compte de ressource, voir l’article suivant : [Affecter un numéro de service.](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)

7. Supprimez les points de terminaison locaux en exécutant la commande PowerShell Skype Entreprise Server sur site suivante :

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
Vous êtes maintenant prêt à [supprimer votre déploiement Skype Entreprise local.](decommission-remove-on-prem.md)

## <a name="see-also"></a>Voir aussi

- [Mise hors service de votre environnement Skype pour entreprises sur site](decommission-on-prem-overview.md)

- [Déplacer tous les utilisateurs requis de l’local vers le site en ligne](decommission-move-on-prem-users.md)

- [Désactiver votre configuration hybride](cloud-consolidation-disabling-hybrid.md)

- [Supprimez votre déploiement sur site de Skype pour entreprises.](decommission-remove-on-prem.md)




