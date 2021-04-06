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
description: Instructions de désaffectation de Skype Entreprise Server.
ms.openlocfilehash: 668e3d5ebf5dfa03fcfb883adcc3e08fc5924bae
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593886"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>Supprimer votre déploiement Skype Entreprise local

Cet article explique comment supprimer votre déploiement Skype Entreprise local. Il s’agit de l’étape 3 des étapes suivantes pour désaffecter votre environnement local :

- Étape 1. [Déplacez tous les utilisateurs et points de terminaison d’application](decommission-move-on-prem-users.md)requis de l’local vers le site en ligne. 

- Étape 2. [Désactivez votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)

- **Étape 3. Supprimez votre déploiement Skype Entreprise local.** (Cet article)


> [!IMPORTANT] 
> Les étapes décrites dans cet article s’appliquent uniquement si vous utilisez la méthode 2 pour gérer les attributs utilisateur, comme décrit [ici.](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory) Si vous utilisez la méthode 1, n’utilisez pas les étapes décrites dans cet article pour supprimer vos serveurs Skype Entreprise. Au lieu de cela, vous pouvez ré-imager les serveurs.

Pour effectuer les étapes de cet article, vous avez besoin de privilèges pour le groupe Administrateurs du schéma et le groupe Administrateurs de l’entreprise. Vous aurez besoin de ces privilèges pour annuler le schéma Skype Entreprise Server et les modifications au niveau de la forêt apportées aux services de domaine Active Directory. Vous devez également être membre du groupe RTCUniversalServerAdmins.


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>Préparer la suppression du déploiement de Skype Entreprise

Après avoir passé tous les comptes d’utilisateur requis vers le cloud, il se peut qu’il reste des objets locaux, tels que des contacts et des applications, que vous devrez nettoyer.

Utilisez les étapes ci-dessous pour nettoyer ces objets et assurez-vous que vous êtes membre du groupe Administrateur local et du groupe RTCUniversalServerAdmins. Notez que ExUmContacts et PersistantChatEndPoints ne sont pas disponibles dans Skype Entreprise Server 2019. Si vous avez Skype Entreprise Server 2019, les cmdlets correspondantes dans les étapes ci-dessous doivent être omises.

1. Pour vérifier si des contacts ou des applications sont associés au déploiement local de Skype Entreprise Server, exécutez les cmdlets PowerShell Skype Entreprise Server suivantes.

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
   ```
2. Examinez les listes de sortie des cmdlets à l’étape 1. Ensuite, si des objets peuvent être supprimés, exécutez les cmdlets PowerShell Skype Entreprise Server suivantes :

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
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a>Supprimer votre déploiement Skype Entreprise local

Après avoir effectué toutes les étapes préliminaires, vous pouvez supprimer le déploiement de Skype Entreprise en suivant les étapes suivantes :

1. Supprimez logiquement le déploiement de Skype Entreprise Server, à l’exception d’un seul serveur frontal, comme suit :

   a. Mettez à jour votre topologie Skype Entreprise Server pour qu’elle ne compte qu’un seul pool frontal :

     - Dans le Générateur de topologie, téléchargez une nouvelle copie et accédez au pool frontal.
     - Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.
     - Dans **Associations,** **décochez Associer un pool edge** (pour les composants multimédias) et cliquez sur **OK.**
     - S’il existe plusieurs pools frontux, supprimez associations pour tous les pools restants.
     - Sélectionnez **Action > supprimer le déploiement.**
     - Sélectionnez **Action > publier la topologie.**

    b. Après avoir publié la topologie, terminez les étapes supplémentaires décrites dans l’Assistant.

2. Supprimez les annuaires des conférences Skype Entreprise Server en exécutant l’cmdlet PowerShell Skype Entreprise Server suivante :

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. Finalisez la désinstallation de votre déploiement Skype Entreprise Server en exécutant l’cmdlet PowerShell Skype Entreprise Server suivante :

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > Si cette étape renvoie une erreur, ouvrez un ticket de support Microsoft pour obtenir de l’aide pour supprimer les objets obsolètes restants.

4. Supprimez le point de contrôle du service Banque d’administration central en exécutant l’cmdlet PowerShell Skype Entreprise Server suivante :

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. Annuler les modifications au niveau de la forêt du domaine Active Directory de Skype Entreprise Server en exécutant l’cmdlet PowerShell Skype Entreprise Server suivante :

   ```PowerShell
   Disable-CsAdDomain
   ```
6. Annuler les modifications apportées au schéma de domaine Active Directory de Skype Entreprise Server en exécutant l’cmdlet PowerShell Skype Entreprise Server suivante :

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>Voir aussi

- [Désaffecter votre environnement Skype Entreprise local](decommission-on-prem-overview.md)

- [Déplacer les utilisateurs et les points de terminaison vers le cloud](decommission-move-on-prem-users.md)

- [Désactiver votre configuration hybride](cloud-consolidation-disabling-hybrid.md)














