---
title: Configurer votre déploiement local pour la diffusion Réunion Skype local
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Résumé : Découvrez les étapes à suivre pour configurer Réunion Skype diffusion pour votre déploiement hybride Skype Entreprise Server local.'
ms.openlocfilehash: 99ba1733dc8c353dc17f9a4c9a51a9ed00410d27
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013708"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configurer votre déploiement local pour la diffusion Réunion Skype local
 
**Résumé :** Découvrez les étapes à suivre pour configurer Réunion Skype diffusion pour votre déploiement local Skype Entreprise Server hybride.
  
Réunion Skype La diffusion est un service en ligne qui fait partie de Office 365. Si vous exécutez Skype Entreprise Server sur site et que vous souhaitez utiliser Réunion Skype Broadcast dans votre environnement, vous devez suivre les étapes de configuration de cette rubrique. Avant de commencer, votre environnement doit être configuré pour un environnement hybride avec Skype Entreprise Online. Pour plus d’informations, voir Planifier la connectivité hybride entre Skype Entreprise Server et [Skype Entreprise Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) et déployer la connectivité hybride entre Skype Entreprise Server et Skype Entreprise [Online.](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurer votre environnement hybride pour la diffusion Réunion Skype hybride

Pour préparer votre environnement à la diffusion Réunion Skype, vous devez :
  
- Configurer la fédération avec les ressources Skype Entreprise Online
    
- Configurer des domaines fédérés SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurer la fédération avec les ressources Skype Entreprise Online

Pour activer la fédération avec Skype Entreprise Online, vous devez configurer l’accès externe pour un fournisseur fédéré SIP. Pour ce faire, utilisez Skype Entreprise Server panneau de Skype Entreprise Server les étapes suivantes :
  
1. Démarrez le panneau Skype Entreprise Server de contrôle d’accès externe et sélectionnez **Accès** externe sur la gauche.
    
2. Sélectionnez **Fournisseurs fédérés SIP,** puis cliquez sur **Nouveau.**
    
3. Configurez le nouveau fournisseur avec les paramètres suivants :
    
   - **Activez les communications avec ce fournisseur :** Sélectionné
   - **Nom du fournisseur :** LyncOnlineResources
   - **Service Edge d’accès (FQDN)** : sipfed.resources.lync.com
   - **Niveau de vérification par défaut :** Autoriser les utilisateurs à communiquer avec tout le monde à l’aide de ce fournisseur. 
   
Vous pouvez également activer la fédération avec Skype Entreprise Online en exécutant l’cmdlet suivante dans Skype Entreprise Server Management Shell :
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurer des domaines fédérés SIP

Ensuite, vous devez ajouter des domaines fédérés SIP à la liste des domaines autorisés. Répétez ces étapes pour chacun des domaines répertoriés, en créant 4 domaines fédérés SIP. Ces domaines sont inclus pour les centres de données régionaux utilisés dans Skype Entreprise Online.
  
1. Démarrez le panneau Skype Entreprise Server de contrôle d’accès externe et sélectionnez **Accès** externe sur la gauche.
    
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

Une fois ces étapes de configuration terminées, vous pouvez commencer à utiliser Réunion Skype diffusion dans votre déploiement. Pour plus d’informations sur Réunion Skype [](https://go.microsoft.com/fwlink/?LinkId=617071) diffusion, voir Qu’est-ce qu’une diffusion Réunion Skype diffusion ? et Réunion Skype [guide d’administration de la diffusion.](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)
