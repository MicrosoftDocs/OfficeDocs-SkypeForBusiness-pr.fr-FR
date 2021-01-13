---
title: Configurer votre déploiement local pour la diffusion de réunion Skype
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Résumé : Découvrez les étapes à suivre pour configurer la diffusion de réunion Skype pour votre déploiement hybride Skype Entreprise Server local.'
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820704"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configurer votre déploiement local pour la diffusion de réunion Skype
 
**Résumé :** Découvrez les étapes à suivre pour configurer la diffusion de réunion Skype pour votre déploiement hybride Skype Entreprise Server local.
  
Diffusion de réunion Skype est un service en ligne qui fait partie d’Office 365. Si vous exécutez Skype Entreprise Server en local et que vous souhaitez utiliser diffusion de réunion Skype dans votre environnement, vous devez suivre les étapes de configuration de cette rubrique. Avant de commencer, votre environnement doit être configuré pour un environnement hybride avec Skype Entreprise Online. Pour plus d’informations, voir [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and Deploy hybrid [connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurer votre environnement hybride pour diffusion de réunion Skype

Pour préparer votre environnement pour la diffusion de réunion Skype, vous devez :
  
- Configurer la fédération avec les ressources Skype Entreprise Online
    
- Configurer des domaines fédérés SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurer la fédération avec les ressources Skype Entreprise Online

Pour activer la fédération avec les ressources Skype Entreprise Online, vous devez configurer l’accès externe pour un fournisseur fédéré SIP. Pour ce faire, à l’aide du Panneau de contrôle Skype Entreprise Server, suivez les étapes suivantes :
  
1. Démarrez le Panneau de contrôle Skype Entreprise Server et sélectionnez **Accès** externe sur la gauche.
    
2. Sélectionnez **Fournisseurs fédérés SIP,** puis cliquez sur **Nouveau.**
    
3. Configurez le nouveau fournisseur avec les paramètres suivants :
    
|||
|:-----|:-----|
|**Activez les communications avec ce fournisseur :** <br/> |Sélectionné  <br/> |
|**Nom du fournisseur :** propriété requise. <br/> |LyncOnlineResources  <br/> |
|**Service Edge d’accès (FQDN) :** propriété requise. <br/> |sipfed.resources.lync.com  <br/> |
|**Niveau de vérification par défaut :** <br/> |Autoriser les utilisateurs à communiquer avec tout le monde à l’aide de ce fournisseur.  <br/> |
   
Vous pouvez également activer la fédération avec les ressources Skype Entreprise Online en exécutant l’cmdlet suivante dans Skype Entreprise Server Management Shell :
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurer des domaines fédérés SIP

Ensuite, vous devez ajouter des domaines fédérés SIP à la liste des domaines autorisés. Répétez ces étapes pour chacun des domaines répertoriés, en créant 4 domaines fédérés SIP. Ces domaines sont inclus pour les centres de données régionaux utilisés dans Skype Entreprise Online.
  
1. Démarrez le Panneau de contrôle Skype Entreprise Server et sélectionnez **Accès** externe sur la gauche.
    
2. Sélectionnez **Domaines fédérés SIP** et cliquez sur **Nouveau.**
    
3. Pour le **nom de domaine (ou nom de** domaine complet) : entrez le domaine, en répétant cette procédure pour chacun des domaines suivants :
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Vous pouvez également configurer l’accès externe pour les domaines fédérés SIP en exécutant les cmdlets suivantes dans Skype Entreprise Server Management Shell :
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Une fois ces étapes de configuration terminées, vous pouvez commencer à utiliser diffusion de réunion Skype dans votre déploiement. Pour plus d’informations sur diffusion de réunion Skype, voir [Qu’est-ce](https://go.microsoft.com/fwlink/?LinkId=617071) qu’une diffusion de réunion Skype ? et le Guide d’administration de diffusion de réunion [Skype.](https://go.microsoft.com/fwlink/?LinkId=617075)
  

