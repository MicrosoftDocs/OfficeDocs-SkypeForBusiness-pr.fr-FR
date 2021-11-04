---
title: Processus de déploiement du parcage d’appel Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Processus de déploiement et étapes de parcage d’appel Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 60de591138046f3ccfa1e5c9ca84bed86c32587d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758076"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Processus de déploiement du parcage d’appel Skype Entreprise
 
Processus de déploiement et étapes de parcage d’appel Skype Entreprise Server Voix Entreprise.
  
Le parcage d’appel permet à un utilisateur Voix Entreprise de mettre un appel en attente à partir d’un téléphone, puis de le récupérer ultérieurement en composant un numéro interne (appelé numéro d’appel par parcage) à partir de n’importe quel téléphone.
  
Les composants que le parcier d’appel utilise sont automatiquement installés et activés sur le serveur frontal ou le serveur Édition Standard lorsque vous déployez Voix Entreprise. Toutefois, vous devez suivre les étapes suivantes pour configurer le parcier d’appel avant qu’il ne soit disponible pour les utilisateurs. 
  
**Processus de déploiement du parcage d’appel**

|**Étape**|**Étapes**|**Groupes et rôles requis**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Configurer les plages d’orbites de parcage d’appel dans la table des orbites  <br/> |Utilisez Skype Entreprise Server Control Panel ou l’cmdlet **New-CSCallParkOrbit** pour créer les plages d’orbites dans la table des orbites de parcage d’appel et les associer au service d’application qui héberge l’application de parcage d’appel. <br/> **Remarque :** Pour une intégration transparente aux plans de numérotation existants, les plages d’orbites sont généralement configurées en tant que bloc d’extensions virtuelles. Il n’est pas possible d’affecter des numéros SDA (sélection directe à l’arrivée, Direct Inward Dialing (DID)) comme numéros d’orbites dans la table des orbites de parcage d’appel. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Créer ou modifier une plage d’orbites de parcur d’appel dans Skype Entreprise](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Configuration des paramètres de parcage d’appel  <br/> | Utilisez **l’cmdlet Set-CsCpsConfiguration** pour configurer les paramètres de parcage d’appel. Au minimum, nous vous recommandons de configurer l’option **OnTimeoutURI** pour configurer la destination de retour à utiliser lorsqu’un appel par parcage n’est plus disponible. Vous pouvez également configurer les paramètres suivants : <br/>  (Facultatif) **EnableMusicOnHold** pour activer ou désactiver l’attente musicale. <br/>  (Facultatif) **MaxCallPickupAttempts** pour déterminer le nombre de fois qu’un appel parqué doit sonner de nouveau sur le téléphone de destination avant d’être transféré à l’URI (Uniform Resource Identifier) de remplacement. <br/>  (Facultatif) **CallPickupTimeoutThreshold** pour déterminer le délai qui s’écoule entre le moment où un appel est parqué et le moment où il sonne de nouveau sur le téléphone auquel il était destiné. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Configurer les paramètres de parcier d’appel dans Skype Entreprise](configure-call-park-settings.md) <br/> |
|Si vous le souhaitez, personnalisez l’attente musicale  <br/> |Si vous ne voulez pas utiliser l’attente musicale par défaut, personnalisez et téléchargez un fichier audio à l’aide de l’applet de commande **Set-CsCallParkServiceMusicOnHoldFile**. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Personnalisation de l’attente musicale du parc d’appel dansSkype pour les entreprises](customize-call-park-music-on-hold.md) <br/> |
|Configurer la stratégie de voix pour activer le parcier d’appel pour les utilisateurs  <br/> |Utilisez Skype Entreprise Server panneau de commande ou l’cmdlet **Set-CSVoicePolicy** avec l’option **EnableCallPark** pour activer le parcage d’appel pour les utilisateurs dans la stratégie de voix. <br/> Par défaut, le parc d’appel est désactivé pour tous les utilisateurs.  <br/> Si vous disposez de plusieurs stratégies de voix, définissez la propriété EnableCallPark pour chaque stratégie de voix, et pas seulement pour la stratégie par défaut.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Activer le parc d’appel pour les utilisateurs Skype Entreprise](enable-call-park-for-users.md) <br/> |
|Vérification des règles de normalisation pour le parcage d’appel  <br/> |Les orbites de parcage d’appel ne doivent pas être normalisées. Vérifiez que les règles de normalisation ne comportent aucune plage d’orbites. Si nécessaire, créez des règles de normalisation supplémentaires pour empêcher la normalisation des orbites.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Vérifier les règles de normalisation pour le parc Skype Entreprise](verify-normalization-rules-for-call-park.md) <br/> |
|Vérifier le déploiement de votre parcement d’appel  <br/> |Testez le parcage et la récupération des appels pour vous assurer que votre configuration fonctionne comme prévu.  <br/> |-  <br/> |[(Facultatif) Vérifier le déploiement du parcement d’appel dans Skype Entreprise](optional-verify-call-park-deployment.md) <br/> |
   

