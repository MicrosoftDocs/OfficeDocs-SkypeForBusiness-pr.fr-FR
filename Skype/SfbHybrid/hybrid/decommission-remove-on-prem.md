---
title: Désaffecter Skype Entreprise Server
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
description: Instructions de désaffectation des Skype Entreprise Server.
ms.openlocfilehash: fd2ba8543745760e900e52c2c1f9b3c3f65b0e70
ms.sourcegitcommit: b17e5acadcca0261eaccc64e1b4ee457348f975c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2021
ms.locfileid: "58365621"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>Supprimez votre déploiement sur site de Skype pour entreprises.

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Cet article explique comment supprimer votre déploiement Skype Entreprise local. Il s’agit de l’étape 4 des étapes suivantes pour désaffecter votre environnement local :

- Étape 1. [Déplacez tous les utilisateurs requis de l’local vers le site en ligne.](decommission-move-on-prem-users.md) 

- Étape 2. [Désactivez votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)

- Étape 3. [Migrer les points de terminaison de l’application hybride de l’local vers le mode en ligne](decommission-move-on-prem-endpoints.md)

- **Étape 4. Supprimez votre déploiement Skype Entreprise local.** (Cet article)


> [!IMPORTANT] 
> Les étapes décrites dans cet article s’appliquent uniquement si vous utilisez la méthode 2 pour gérer les attributs utilisateur, comme décrit [ici.](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory) Si vous utilisez la méthode 1, n’utilisez pas les étapes décrites dans cet article pour supprimer Skype Entreprise serveurs. Au lieu de cela, vous pouvez ré-imager les serveurs.

Pour effectuer les étapes de cet article, vous avez besoin de privilèges pour le groupe Administrateurs du schéma et le groupe Administrateurs Enterprise schéma. Vous aurez besoin de ces privilèges pour annuler le schéma Skype Entreprise Server et les modifications au niveau de la forêt apportées aux services de domaine Active Directory. Vous devez également être membre du groupe RTCUniversalServerAdmins.


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>Préparer la suppression du déploiement Skype Entreprise déploiement

Après avoir passé tous les comptes d’utilisateur requis vers le cloud, il se peut qu’il reste des objets locaux, tels que des contacts et des applications, que vous devrez nettoyer.

Utilisez les étapes ci-dessous pour nettoyer ces objets et assurez-vous que vous êtes membre du groupe Administrateur local et du groupe RTCUniversalServerAdmins. Notez que ExUmContacts et PersistantChatEndPoints ne sont pas disponibles Skype Entreprise Server 2019. Si vous avez Skype Entreprise Server 2019, les cmdlets correspondantes dans les étapes ci-dessous doivent être omises.

1. Pour vérifier si des contacts ou des applications sont associés au déploiement Skype Entreprise Server local, exécutez les cmdlets PowerShell Skype Entreprise Server suivantes.

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   Get-CsUnassignedNumber
   ```
2. Examinez les listes de sortie des cmdlets à l’étape 1. Ensuite, si des objets peuvent être supprimés, exécutez les Skype Entreprise Server cmdlets PowerShell suivantes :

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   Get-CsUnassignedNumber | Remove-CsUnassignedNumber -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a>Supprimez votre déploiement sur site de Skype pour entreprises.

Après avoir effectué toutes les étapes préliminaires, vous pouvez supprimer le déploiement Skype Entreprise en suivant les étapes suivantes :

1. Supprimez logiquement le Skype Entreprise Server déploiement, à l’exception d’un seul frontal, comme suit :

   1. Mettez à jour Skype Entreprise Server topologie principale pour qu’elle ne compte qu’un seul pool frontal :

      1. Dans le Générateur de topologie, téléchargez une nouvelle copie et accédez au pool frontal.
      1. Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.
      1. Dans **Associations,** **décochez Associer un pool edge** (pour les composants multimédias) et cliquez sur **OK.**
      1. S’il existe plusieurs pools frontux, supprimez associations pour tous les pools restants.
      1. Sélectionnez **Action > supprimer le déploiement.**
      1. Sélectionnez **Action > publier la topologie.**

    1. Après avoir publié la topologie, terminez les étapes supplémentaires décrites dans l’Assistant.

2. Supprimez Skype Entreprise Server des conférences en exécutant l’Skype Entreprise Server cmdlet PowerShell suivante :

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. Finalisez la désinstallation de votre déploiement Skype Entreprise Server en exécutant l’Skype Entreprise Server cmdlet PowerShell suivante :

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > Si cette étape renvoie une erreur, ouvrez un ticket de support Microsoft pour obtenir de l’aide pour supprimer les objets obsolètes restants.

4. Supprimez le point de contrôle du service Banque d’administration central en exécutant l’Skype Entreprise Server cmdlet PowerShell suivante :

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. Pour annuler Skype Entreprise Server modifications au niveau du domaine Active Directory, exécutez l’Skype Entreprise Server cmdlet PowerShell suivante :

   ```PowerShell
   Disable-CsAdDomain
   ```
6. Pour annuler Skype Entreprise Server modifications au niveau de la forêt Active Directory, exécutez l’Skype Entreprise Server cmdlet PowerShell suivante :

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>Voir aussi

- [Mise hors service de votre environnement Skype pour entreprises sur site](decommission-on-prem-overview.md)

- [Déplacer tous les utilisateurs requis de l’local vers le site en ligne](decommission-move-on-prem-users.md)

- [Désactiver votre configuration hybride](cloud-consolidation-disabling-hybrid.md)

- [Déplacer des points de terminaison d’application hybride de l’local vers le mode en ligne](decommission-move-on-prem-endpoints.md)

