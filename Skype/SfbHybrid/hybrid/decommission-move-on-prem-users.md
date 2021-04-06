---
title: Déplacer des utilisateurs et des points de terminaison vers le cloud
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
description: Déplacez les utilisateurs et les points de terminaison avant de désaffecter un environnement Skype Entreprise local.
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593887"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a>Déplacer les utilisateurs et points de terminaison requis avant de désaffecter votre environnement local

Cet article explique comment déplacer les utilisateurs et les points de terminaison d’application requis vers le cloud Microsoft avant de désaffecter votre environnement Skype Entreprise local. Il s’agit de l’étape 1 des étapes suivantes pour désaffecter votre environnement local :

- **Étape 1. Déplacez tous les utilisateurs et points de terminaison d’application requis de l’local vers le site en ligne.** (Cet article.)

- Étape 2. [Désactivez votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)

- Étape 3. [Supprimez votre déploiement Skype Entreprise local.](decommission-remove-on-prem.md)


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>Déplacer tous les utilisateurs requis de l’local vers le cloud

Tous les utilisateurs que vous continuerez à utiliser après avoir effectué la migration doivent d’abord être déplacés de l’local vers le cloud. Vous déplacez les utilisateurs à l’aide des outils d’administration locaux. Pour plus d’informations, voir [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).

Bien qu’il soit possible pour les utilisateurs ayant des comptes Skype Entreprise Server locaux d’utiliser Teams, ces utilisateurs n’ont pas toutes les fonctionnalités de Teams. Ces utilisateurs ne peuvent pas interopérer ou fédérer avec d’autres utilisateurs qui utilisent encore Skype Entreprise (en ligne ou en local). Ces utilisateurs ne peuvent pas non plus recevoir d’appels PSTN dans leur client Teams. Par conséquent, vous devez déplacer ces utilisateurs en ligne. Cette étape garantit également que tous les contacts ou réunions créés dans Skype Entreprise Server sont migrés vers Teams.

Pour vérifier s’il reste des utilisateurs dans votre déploiement local, exécutez l’cmdlet suivante dans une fenêtre PowerShell Skype Entreprise Server.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

Si des utilisateurs sont renvoyés, examinez la sortie pour déterminer si des comptes doivent être déplacés vers le cloud et, pour ces utilisateurs, suivez les étapes [ci-après.](move-users-between-on-premises-and-cloud.md) Pour les comptes d’utilisateurs qui ne sont plus nécessaires, exécutez l’cmdlet PowerShell Skype Entreprise Server suivante :

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> L'Disable-CsUser supprimera tous les attributs Skype Entreprise pour tous les utilisateurs qui ont les critères de filtre. Avant de continuer, confirmez que ces comptes ne sont plus nécessaires à l’avenir.

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a>Déplacer des points de terminaison d’application hybride sur site vers Microsoft 365

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
Vous êtes maintenant prêt à [désactiver votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)

## <a name="see-also"></a>Voir aussi

- [Désaffecter votre environnement Skype Entreprise local](decommission-on-prem-overview.md)

- [Désactiver votre configuration hybride](cloud-consolidation-disabling-hybrid.md)

- [Supprimer votre déploiement Skype Entreprise local](decommission-remove-on-prem.md)




