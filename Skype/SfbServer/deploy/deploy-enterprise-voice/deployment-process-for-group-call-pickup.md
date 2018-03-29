---
title: Procédure de déploiement de la prise d’appel de groupe dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Processus de déploiement et les étapes de collecte d’appeler groupe dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 1e87b475e5628aa9df46d025c95d80dc355c6567
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business-2015"></a>Deployment process for Group Call Pickup in Skype for Business 2015
 
Processus de déploiement et les étapes de collecte d’appeler groupe dans Skype pour Business Server Voix Entreprise.
  
Collecte d’appeler groupe permet aux utilisateurs de répondre aux appels entrants à partir de leurs téléphones à leurs collègues. 
  
 Les composants de collecte d’appeler groupe utilise automatiquement installés et activés sur le serveur frontal ou Standard Edition serveur lors du déploiement de Voix Entreprise. Toutefois, vous devez utiliser les étapes suivantes pour configurer la collecte de groupe appeler avant qu’il soit disponible pour les utilisateurs.
  
**Processus de déploiement de capteur d’appel de groupe**

|**Phase de**|**Étapes**|**Rôles et groupes requis**|**Documentation sur le déploiement**|
|:-----|:-----|:-----|:-----|
|Activer l’outil SEFAUtil dans votre topologie.  <br/> |
Utilisez l’applet de commande New-CsTrustedApplicationPool pour créer un nouveau pool d’applications de confiance. L’applet de commande New-CsTrustedApplication permet de spécifier l’outil SEFAUtil comme application de confiance. Exécutez l’applet de commande Enable-CsTopology pour activer la topologie. Si vous ne l’avez déjà pas, téléchargez la Skype pour la version de serveur d’entreprise de l’outil SEFAUtil à partir de cet emplacement et l’installer sur le pool d’applications de confiance que vous avez créé à l’étape 1. Vérifiez que l’outil SEFAUtil fonctionne correctement en l’exécutant pour afficher les paramètres de transfert d’appel d’un utilisateur dans le déploiement. |RTCUniversalServerAdmins  <br/> |[Déploiement de l’outil SEFAUtil dans Skype pour entreprise 2015](deploy-the-sefautil-tool.md) <br/> [Nouvelle-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) [Nouvelle-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps) [Activer-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Documentation outil du kit de ressources Lync Server 2013](https://technet.microsoft.com/en-us/library/jj945604%28v=ocs.15%29.aspx). (Pour Skype pour Business Server, vous devez utiliser la version actuelle de l’outil, mais s’applique toujours cette documentation à partir de Lync Server 2013.  <br/> |
|Configurer les plages de numéros de prise d’appel dans la table des numéros d’appel parqué  <br/> |L’applet de commande **New-CSCallParkOrbit** permet de créer des plages de numéros de collecte appel dans la table des appels park orbite et affecter les plages de prise d’appel du type **GroupPickup**.  <br/> Pour une intégration transparente aux plans de numérotation existants, les plages de numéros sont en général configurées en tant que bloc d’extensions virtuelles. Il n’est pas possible d’affecter des numéros SDA (sélection directe à l’arrivée, Direct Inward Dialing (DID)) comme numéros de plages dans la table des numéros d’appel parqué.<br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Créer ou modifier une plage de numéros de collecte d’appeler groupe dans Skype pour entreprise 2015](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Attribuer un numéro d’appel de remise en mains propres aux utilisateurs et activer la collecte d’appeler de groupe pour les utilisateurs  <br/> |Utilisez le paramètre /enablegrouppickup dans l’outil SEFAUtil du kit de ressources pour permettre la collecte d’appeler groupe et affecter un numéro de prise d’appel pour les utilisateurs.  <br/> |-  <br/> |[Activer la collecte d’appeler de groupe pour les utilisateurs et affecter un numéro de groupe dans Skype pour entreprise 2015](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Informer les utilisateurs du numéro de prise d’appel qui leur a été affecté et de tout autre numéro digne d’intérêt  <br/> |Après avoir activé la prise d’appel de groupe pour les utilisateurs, envoyez un e-mail ou utilisez une autre méthode pour indiquer aux utilisateurs leur numéro de groupe de prise d’appel. Indiquez aux utilisateurs le numéro de groupe de prise d’appel pour un groupe qu’ils souhaitent surveiller. Dans la mesure où les utilisateurs peuvent récupérer des appels d’autres utilisateurs même s’ils ne se trouvent pas dans le même groupe, les utilisateurs peuvent avoir besoin du numéro de groupe de prise d’appel pour plusieurs groupes.  <br/> |-  <br/> ||
|Vérifiez que votre déploiement de prise d’appel de groupe  <br/> | Testez la réalisation et la récupération des appels pour vérifier que la configuration fonctionne comme prévu. Vérifiez au minimum les éléments suivants : <br/>  Appelez un utilisateur activé pour la prise d’appel de groupe et faites en sorte qu’un autre utilisateur récupère l’appel. Cet autre utilisateur peut appartenir au même groupe, à un groupe différent ou ne pas être activé pour la prise d’appel de groupe. <br/>  Appelez un utilisateur activé pour la prise d’appel de groupe et ne répondez pas à l’appel. <br/> |-  <br/> ||
   

