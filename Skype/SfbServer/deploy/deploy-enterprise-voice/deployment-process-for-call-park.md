---
title: Procédure de déploiement du parcage d’appel dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Processus de déploiement et les étapes de mise en garde d’appels dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: d7bc57664b7f6880cde7481c3ba5aff97c2d4392
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="deployment-process-for-call-park-in-skype-for-business-2015"></a>Procédure de déploiement du parcage d’appel dans Skype Entreprise 2015
 
Processus de déploiement et les étapes de mise en garde d’appels dans Skype pour Business Server Enterprise Voice.
  
Mise en garde d’appels permet à un utilisateur Enterprise Voice mettre un appel en attente à partir d’un téléphone et ensuite le récupérer ultérieurement en composant un numéro interne (appelé une orbite de parcage d’appel) à partir de n’importe quel téléphone.
  
Les composants de mise en garde d’appels automatiquement installés et activés sur le serveur frontal ou Standard Edition server lors du déploiement d’Enterprise Voice. Toutefois, vous devez utiliser les étapes suivantes pour configurer la mise en garde d’appels avant qu’il soit accessible aux utilisateurs. 
  
**Processus de déploiement du parcage d’appel**

|**Phase**|**Étapes**|**Groupes et rôles requis**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Configurer les plages d’orbites de parcage d’appel dans la table des orbites  <br/> |Utilisez Skype pour le panneau de configuration serveur Business ou l’applet de commande **New-CSCallParkOrbit** pour créer les plages d’orbites dans la table d’orbite de parcage d’appel et de les associer avec le service d’Application qui héberge l’application de parcage d’appel. <br/> **Remarque :** Pour une intégration transparente avec des plans de numérotation, les plages d’orbites sont généralement configurées comme un bloc de postes virtuels. Il n’est pas possible d’affecter des numéros SDA (sélection directe à l’arrivée, Direct Inward Dialing [DID]) comme numéros d’orbites dans la table des orbites de parcage d’appel. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Créer ou modifier une plage d’orbites de parcage d’appel dans Skype pour Business 2015](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Configuration des paramètres de parcage d’appel  <br/> | Utilisez l’applet de commande **Set-CsCpsConfiguration** pour configurer les paramètres de parcage d’appel. Au minimum, nous vous conseillons de configurer l’option **OnTimeoutURI** pour configurer la destination de remplacement à utiliser lorsqu’un appel mis en garde arrive à expiration. Vous pouvez également configurer les paramètres suivants : <br/>  (Facultatif) **Propriété EnableMusicOnHold** pour activer ou désactiver une musique d’attente. <br/>  (Facultatif) **MaxCallPickupAttempts** pour déterminer le nombre de fois qu’un appel parqué doit sonner retour vers le téléphone avant de transférer l’appel à la secours ressource identificateur URI (Uniform). <br/>  (Facultatif) **CallPickupTimeoutThreshold** pour déterminer la quantité de temps qui s’écoule après qu’un appel a été mis en garde il sonne de nouveau sur le téléphone où l’appel a été reçu. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Configurer les paramètres de parcage d’appel dans Skype pour Business 2015](configure-call-park-settings.md) <br/> |
|Si vous le souhaitez, personnalisez l’attente musicale  <br/> |Utilisez l’applet de commande **Set-CsCallParkServiceMusicOnHoldFile** pour personnaliser et télécharger un fichier audio, si vous ne souhaitez pas utiliser la musique par défaut sur le blocage. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Personnaliser une musique de parcage d’appel d’attente inSkype pour Business 2015](customize-call-park-music-on-hold.md) <br/> |
|Configurer la stratégie de voix pour activer la mise en garde d’appels pour les utilisateurs  <br/> |Utilisez Skype pour le panneau de configuration serveur Business ou l’applet de commande **Set-CSVoicePolicy** avec l’option **EnableCallPark** pour activer la mise en garde d’appels pour les utilisateurs de la stratégie de voix. <br/> Par défaut, la mise en garde d’appels est désactivé pour tous les utilisateurs.  <br/> Si vous disposez de plusieurs stratégies de voix, définissez la propriété EnableCallPark pour toutes les stratégies de voix et pas seulement pour la stratégie par défaut.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Activer le parcage d’appel pour les utilisateurs de Skype pour Business 2015](enable-call-park-for-users.md) <br/> |
|Vérification des règles de normalisation pour le parcage d’appel  <br/> |Les orbites de parcage d’appel ne doivent pas être normalisées. Vérifiez que les règles de normalisation ne comportent aucune plage d’orbites. Si nécessaire, créez des règles de normalisation supplémentaires pour empêcher la normalisation des orbites.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Vérifier les règles de normalisation pour le parcage d’appel dans Skype pour Business 2015](verify-normalization-rules-for-call-park.md) <br/> |
|Vérifiez que votre déploiement de parcage d’appel  <br/> |Testez la réalisation et la récupération des appels pour vérifier que la configuration fonctionne comme prévu.  <br/> |-  <br/> |[(Facultatif) Vérifier le déploiement de parcage d’appel dans Skype pour Business 2015](optional-verify-call-park-deployment.md) <br/> |
   

