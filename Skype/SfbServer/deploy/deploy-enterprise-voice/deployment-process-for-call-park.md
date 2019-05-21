---
title: Processus de déploiement du parc d’appels dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Processus de déploiement et étapes du parc d’appels dans Skype entreprise Server Voice.
ms.openlocfilehash: 972a8cec2794afeebc0f5ab65d89291e78b7211e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289012"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Processus de déploiement du parc d’appels dans Skype entreprise
 
Processus de déploiement et étapes du parc d’appels dans Skype entreprise Server Voice.
  
Le parc d’appels permet à un utilisateur d’entreprise Voice de mettre un appel en attente d’un seul téléphone, puis de récupérer l’appel ultérieurement en composant un numéro interne (connu sous le nom de bobine de parking) depuis n’importe quel téléphone.
  
Les composants utilisés par le parc d’appels sont automatiquement installés et activés sur le serveur frontal ou le serveur Standard Edition lors du déploiement d’Enterprise Voice. Toutefois, vous devez suivre les étapes ci-dessous pour configurer le parc d’appels avant qu’il soit disponible pour les utilisateurs. 
  
**Procédure de déploiement du parcage d’appel**

|**Phase**|**Étapes**|**Groupes et rôles requis**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Configurer les plages d’orbites de parcage d’appel dans la table des orbites  <br/> |Utilisez le panneau de configuration Skype entreprise Server ou l’applet de commande **New-CSCallParkOrbit** pour créer des plages d’orbites dans la table de stationnement d’appel et associez-les au service d’application qui héberge l’application de stationnement d’appels. <br/> **Remarque:** Pour une intégration transparente avec les plans de numérotation existants, les plages d’orbites sont généralement configurées comme un bloc d’extensions virtuelles. Il n’est pas possible d’affecter des numéros SDA (sélection directe à l’arrivée, Direct Inward Dialing [DID]) comme numéros d’orbites dans la table des orbites de parcage d’appel. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Créer ou modifier une gamme de parc d’appels dans Skype entreprise](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Configuration des paramètres de parcage d’appel  <br/> | Utilisez l’applet de cmdlet **Set-CsCpsConfiguration** pour configurer les paramètres du parc d’appels. Nous vous conseillons d’effectuer au moins une configuration de l’option **OnTimeoutURI** pour configurer la destination de secours à utiliser lorsqu’un appel parqué arrive à expiration. Vous pouvez également configurer les paramètres suivants: <br/>  (Facultatif) **EnableMusicOnHold** pour activer ou désactiver l’attente musicale. <br/>  (Facultatif) **MaxCallPickupAttempts** pour déterminer le nombre de fois qu’un appel parqué doit sonner de nouveau sur le téléphone de destination avant d’être transféré à l’URI (Uniform Resource Identifier) de remplacement. <br/>  (Facultatif) **CallPickupTimeoutThreshold** pour déterminer le délai qui s’écoule entre le moment où un appel est parqué et le moment où il sonne de nouveau sur le téléphone auquel il était destiné. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Configurer les paramètres de parc d’appels dans Skype entreprise](configure-call-park-settings.md) <br/> |
|Si vous le souhaitez, personnalisez l’attente musicale  <br/> |Si vous ne voulez pas utiliser l’attente musicale par défaut, personnalisez et téléchargez un fichier audio à l’aide de l’applet de commande **Set-CsCallParkServiceMusicOnHoldFile**. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Personnalisation du parc d’appels en attente dans Skype entreprise](customize-call-park-music-on-hold.md) <br/> |
|Configurer la stratégie vocale pour activer le parc d’appels pour les utilisateurs  <br/> |Utilisez le panneau de configuration Skype entreprise Server ou l’applet de commande **Set-CSVoicePolicy** avec l’option **EnableCallPark** pour activer le parc d’appels pour les utilisateurs dans la stratégie vocale. <br/> Par défaut, le parc d’appels est désactivé pour tous les utilisateurs.  <br/> Si vous disposez de plusieurs stratégies de voix, définissez la propriété EnableCallPark pour toutes les stratégies de voix et pas seulement pour la stratégie par défaut.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Activer le parc d’appels pour les utilisateurs de Skype entreprise](enable-call-park-for-users.md) <br/> |
|Vérification des règles de normalisation pour le parcage d’appel  <br/> |Les orbites de parcage d’appel ne doivent pas être normalisées. Vérifiez que les règles de normalisation ne comportent aucune plage d’orbites. Si nécessaire, créez des règles de normalisation supplémentaires pour empêcher la normalisation des orbites.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Vérifier les règles de normalisation du parc d’appels dans Skype entreprise](verify-normalization-rules-for-call-park.md) <br/> |
|Vérifier le déploiement de votre parc d’appels  <br/> |Testez la réalisation et la récupération des appels pour vérifier que la configuration fonctionne comme prévu.  <br/> |-  <br/> |[Facultatif Vérifier le déploiement du parc d’appels dans Skype entreprise](optional-verify-call-park-deployment.md) <br/> |
   

