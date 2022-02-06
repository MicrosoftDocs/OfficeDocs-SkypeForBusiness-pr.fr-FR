---
title: Processus de déploiement de la prise d’appel de groupe dans Skype Entreprise
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Processus de déploiement et étapes de prise d’appel de groupe dans Skype Entreprise Server Voix Entreprise.
---

# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Processus de déploiement de la prise d’appel de groupe dans Skype Entreprise
 
Processus de déploiement et étapes de prise d’appel de groupe dans Skype Entreprise Server Voix Entreprise.
  
La prise d’appel de groupe permet aux utilisateurs de répondre aux appels entrants à leurs collègues à partir de leurs propres téléphones. 
  
 Les composants que la prise d’appel de groupe utilise sont automatiquement installés et activés sur le serveur frontal ou le serveur Édition Standard lorsque vous déployez Voix Entreprise. Toutefois, vous devez suivre les étapes suivantes pour configurer la prise d’appel de groupe avant qu’elle ne soit disponible pour les utilisateurs.
  
**Processus de déploiement de la prise d’appel de groupe**

|**Étape**|**Étapes**|**Groupes et rôles requis**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Activer l’outil SEFAUtil dans votre topologie|Utilisez lNew-CsTrustedApplicationPool cmdlet pour créer un pool d’applications fiables. Utilisez la cmdlet New-CsTrustedApplication pour spécifier l’outil SEFAUtil en tant qu’application fiable. Exécutez lEnable-CsTopology cmdlet pour activer la topologie. Si vous ne l’avez pas encore, téléchargez la version Skype Entreprise Server de l’outil SEFAUtil à partir de cet emplacement et installez-la sur le pool d’applications approuvé que vous avez créé à l’étape 1. Vérifiez que SEFAUtil s’exécute correctement en l’exécutant pour afficher les paramètres de forwarding d’appel d’un utilisateur dans le déploiement. |RTCUniversalServerAdmins  <br/> |[Déployer l’outil SEFAUtil dans Skype Entreprise](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Skype Entreprise Server documentation des outils du Kit de ressources 2015](../../management-tools/resource-kit-tools.md). (Par Skype Entreprise Server vous devez utiliser la version actuelle de l’outil, mais cette documentation de Lync Server 2013 s’applique toujours.)  <br/> |
|Configurer des plages de numéro de prise d’appel dans la table des orbites de parcage d’appel  <br/> |Utilisez l’cmdlet **New-CSCallParkOrbit** pour créer des plages de numéro de prise d’appel dans la table des orbites de parcage d’appel et attribuez aux plages de prise d’appel le type **GroupPickup**.  <br/> Pour une intégration transparente aux plans de numérotation existants, les plages de numéros sont généralement configurées en tant que bloc d’extensions virtuelles. L’affectation de numéros DID (Direct Inward Dialing) en tant que numéros de plage dans la table des numéros d’appels par parcage n’est pas prise en charge.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Créer ou modifier une plage de numéro de prise d’appel de groupe dans Skype Entreprise](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Affecter un numéro de prise d’appel aux utilisateurs et activer la prise d’appel de groupe pour les utilisateurs  <br/> |Utilisez le paramètre /enablegrouppickup dans l’outil du kit de ressources SEFAUtil pour activer la prise d’appel de groupe et affecter un numéro de prise d’appel pour les utilisateurs.  <br/> |-  <br/> |[Activer la prise d’appel de groupe pour les utilisateurs et affecter un numéro de groupe dans Skype Entreprise](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Informer les utilisateurs de leur numéro de prise d’appel affecté et de tout autre numéro d’intérêt  <br/> |Après avoir activé la prise d’appel de groupe pour les utilisateurs, utilisez le courrier électronique ou un autre mécanisme pour informer les utilisateurs de leur numéro de groupe de prise d’appel. Informez les utilisateurs du numéro du groupe de prise d’appel pour n’importe quel groupe qu’ils souhaitent surveiller. Étant donné que les utilisateurs peuvent récupérer des appels pour d’autres utilisateurs même s’ils ne font pas le même groupe, les utilisateurs peuvent avoir besoin du numéro de groupe de prise d’appel pour plusieurs groupes.  <br/> |-  <br/> ||
|Vérifier le déploiement de la prise d’appel de groupe  <br/> | Testez le placement et la récupération des appels pour vous assurer que votre configuration fonctionne comme prévu. Vérifiez au minimum les informations suivantes : <br/>  Appelez un utilisateur activé pour la prise d’appel de groupe et demander à un autre utilisateur de récupérer l’appel. L’autre utilisateur peut se trouver dans le même groupe, dans un autre groupe ou ne pas activer la prise d’appel de groupe. <br/>  Appelez un utilisateur activé pour la prise d’appel de groupe et ne répondez pas à l’appel. <br/> |-  <br/> ||
