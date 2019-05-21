---
title: Processus de déploiement pour le prélèvement d’appels de groupe dans Skype entreprise
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
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Processus de déploiement et étapes de la cueillette d’appels de groupe dans Skype entreprise Server Voice.
ms.openlocfilehash: f493c3c83f3fa703dd5f62989f4f2e444e83ed5d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289923"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Processus de déploiement pour le prélèvement d’appels de groupe dans Skype entreprise
 
Processus de déploiement et étapes de la cueillette d’appels de groupe dans Skype entreprise Server Voice.
  
La fonction de cueillette des appels de groupe permet aux utilisateurs de répondre aux appels entrants de leurs collègues à partir de leur propre téléphone. 
  
 Les composants utilisés par le biais du groupe de collecte d’appels sont automatiquement installés et activés sur le serveur frontal ou le serveur Standard Edition lors du déploiement d’Enterprise Voice. Toutefois, vous devez suivre les étapes ci-dessous pour configurer la collecte d’appels de groupe avant qu’elle ne soit disponible pour les utilisateurs.
  
**Processus de déploiement de la prise d’appel de groupe**

|**Phase**|**Étapes**|**Groupes et rôles requis**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Activer l’outil SEFAUtil dans votre topologie|Utilisez l’applet de nouvelle applet de nouveau-CsTrustedApplicationPool pour créer un pool d’applications approuvé. Utilisez l’applet de nouvelle applet de CsTrustedApplication pour spécifier l’outil SEFAUtil en tant qu’application approuvée. Exécutez l’applet de passe Enable-CsTopology pour activer la topologie. Si vous ne l’avez pas encore, téléchargez la version de Skype entreprise Server de l’outil SEFAUtil à partir de cet emplacement et installez-la sur le pool d’applications approuvé que vous avez créé à l’étape 1. Vérifiez que l’outil SEFAUtil fonctionne correctement en l’exécutant pour afficher les paramètres de transfert d’appel d’un utilisateur dans le déploiement. |RTCUniversalServerAdmins  <br/> |[Déploiement de l’outil SEFAUtil dans Skype entreprise](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Documentation des outils du kit de ressources Skype entreprise Server 2015](../../management-tools/resource-kit-tools.md). (Pour Skype entreprise Server, vous devez utiliser la version actuelle de l’outil, mais cette documentation de Lync Server 2013 s’applique toujours.)  <br/> |
|Configurer les plages de numéros de prise d’appel dans la table des numéros d’appel parqué  <br/> |Utilisez l’applet de commande **New-CSCallParkOrbit** pour créer des plages de numéros de prise d’appel dans la table des numéros d’appel parqué et affecter aux plages de prise d’appel le type **GroupPickup**.  <br/> Pour une intégration transparente aux plans de numérotation existants, les plages de numéros sont en général configurées en tant que bloc d’extensions virtuelles. Il n’est pas possible d’affecter des numéros SDA (sélection directe à l’arrivée, Direct Inward Dialing (DID)) comme numéros de plages dans la table des numéros d’appel parqué.<br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Création ou modification d’une plage de numéros de téléphone dans Skype entreprise](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Affectation d’un numéro de capture d’appel aux utilisateurs et activation de la cueillette d’appel de groupe pour les utilisateurs  <br/> |Utilisez le paramètre/enablegrouppickup dans l’outil de gestion des ressources SEFAUtil pour activer le prélèvement d’appels de groupe et affecter un numéro de téléphone pour les utilisateurs.  <br/> |-  <br/> |[Activez le prélèvement d’appel de groupe pour les utilisateurs et attribuez un numéro de groupe dans Skype entreprise.](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Informer les utilisateurs du numéro de prise d’appel qui leur a été affecté et de tout autre numéro digne d’intérêt  <br/> |Après avoir activé la prise d’appel de groupe pour les utilisateurs, envoyez un e-mail ou utilisez une autre méthode pour indiquer aux utilisateurs leur numéro de groupe de prise d’appel. Indiquez aux utilisateurs le numéro de groupe de prise d’appel pour un groupe qu’ils souhaitent surveiller. Dans la mesure où les utilisateurs peuvent récupérer des appels d’autres utilisateurs même s’ils ne se trouvent pas dans le même groupe, les utilisateurs peuvent avoir besoin du numéro de groupe de prise d’appel pour plusieurs groupes.  <br/> |-  <br/> ||
|Vérifier le déploiement d’un appel de groupe  <br/> | Testez la réalisation et la récupération des appels pour vérifier que la configuration fonctionne comme prévu. Vérifiez au minimum les éléments suivants : <br/>  Appelez un utilisateur activé pour la prise d’appel de groupe et faites en sorte qu’un autre utilisateur récupère l’appel. Cet autre utilisateur peut appartenir au même groupe, à un groupe différent ou ne pas être activé pour la prise d’appel de groupe. <br/>  Appelez un utilisateur activé pour la prise d’appel de groupe et ne répondez pas à l’appel. <br/> |-  <br/> ||
   

