---
title: Procédure de déploiement du parcage d’appel dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Processus de déploiement et les étapes de parc d’appel dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 9d5df92a95e52612c3b0dee005072b10de5c244c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-process-for-call-park-in-skype-for-business-2015"></a>Procédure de déploiement du parcage d’appel dans Skype Entreprise 2015
 
Processus de déploiement et les étapes de parc d’appel dans Skype pour Business Server Voix Entreprise.
  
Appel de parc permet à un utilisateur de Voix Entreprise mettre un appel en attente à partir d’un téléphone et puis récupérer ultérieurement l’appel en composant un numéro interne (appelé une orbite appel Park) à partir de n’importe quel téléphone.
  
Les composants qui utilise des appels Park sont automatiquement installés et activés sur le serveur frontal ou Standard Edition server lors du déploiement de Voix Entreprise. Toutefois, vous devez utiliser les étapes suivantes pour configurer l’appel de parc avant qu’il soit disponible pour les utilisateurs. 
  
**Processus de déploiement de parc d’appel**

|**Phase de**|**Étapes**|**Rôles et groupes requis**|**Documentation sur le déploiement**|
|:-----|:-----|:-----|:-----|
|Configurer les plages d’orbites de parcage d’appel dans la table des orbites  <br/> |Utiliser Skype pour Business Server du Panneau de configuration ou l’applet de commande **New-CSCallParkOrbit** pour créer les plages d’orbite dans la table des appels park orbite et de les associer avec le service d’Application qui héberge l’application d’appel Park. <br/> **Remarque :** Pour une intégration transparente avec les plans de numérotation existant, les plages d’orbite sont généralement configurés comme un bloc d’extensions virtuels. Il n’est pas possible d’affecter des numéros SDA (sélection directe à l’arrivée, Direct Inward Dialing [DID]) comme numéros d’orbites dans la table des orbites de parcage d’appel. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Créer ou modifier une plage d’orbite appel Park dans Skype pour entreprise 2015](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Configuration des paramètres de parcage d’appel  <br/> | L’applet de commande **Set-CsCpsConfiguration** permet de configurer les paramètres d’appel Park. Au minimum, nous vous conseillons de configurer l’option **OnTimeoutURI** pour configurer la destination de secours à utiliser lors de l’expiration d’un appel en stationnement. Vous pouvez également configurer les paramètres suivants : <br/>  (Facultatif) **EnableMusicOnHold** d’activer ou de désactiver la musique en attente. <br/>  (Facultatif) **MaxCallPickupAttempts** pour déterminer le nombre de fois à un anneaux en stationnement appel vers le téléphone répondant avant de transférer l’appel vers le secours identificateur URI (Uniform Resource). <br/>  (Facultatif) **CallPickupTimeoutThreshold** pour déterminer la quantité de temps qui s’écoule après qu’un appel a été calée avant qu’il sonne au téléphone où l’appel a été reçu. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Configurer les paramètres d’appel Park dans Skype pour entreprise 2015](configure-call-park-settings.md) <br/> |
|Si vous le souhaitez, personnalisez l’attente musicale  <br/> |L’applet de commande **Set-CsCallParkServiceMusicOnHoldFile** permet de personnaliser et télécharger un fichier audio, si vous ne souhaitez pas utiliser la musique par défaut sur le contenir. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Personnaliser des morceaux musicaux d’appel Park sur inSkype de blocage pour Business 2015](customize-call-park-music-on-hold.md) <br/> |
|Configurer la stratégie voice pour activer le parc d’appel pour les utilisateurs  <br/> |Permet de Skype pour Business Server du Panneau de configuration ou l’applet de commande **Set-CSVoicePolicy** avec l’option **EnableCallPark** pour activer le parc d’appel pour les utilisateurs dans une stratégie voice. <br/> Par défaut, le parc d’appel est désactivée pour tous les utilisateurs.  <br/> Si vous disposez de plusieurs stratégies de voix, définissez la propriété EnableCallPark pour toutes les stratégies de voix et pas seulement pour la stratégie par défaut.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Activer le parc d’appel pour les utilisateurs de Skype pour entreprise 2015](enable-call-park-for-users.md) <br/> |
|Vérification des règles de normalisation pour le parcage d’appel  <br/> |Les orbites de parcage d’appel ne doivent pas être normalisées. Vérifiez que les règles de normalisation ne comportent aucune plage d’orbites. Si nécessaire, créez des règles de normalisation supplémentaires pour empêcher la normalisation des orbites.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Vérifiez les règles de normalisation pour le parc d’appel dans Skype pour entreprise 2015](verify-normalization-rules-for-call-park.md) <br/> |
|Vérifier le déploiement de votre parc d’appel  <br/> |Testez la réalisation et la récupération des appels pour vérifier que la configuration fonctionne comme prévu.  <br/> |-  <br/> |[(Facultatif) Vérifier le déploiement d’appel Park dans Skype pour entreprise 2015](optional-verify-call-park-deployment.md) <br/> |
   

