---
title: Configuration de votre déploiement local pour la diffusion de réunion Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Résumé : Découvrez les étapes à suivre pour configurer la diffusion de réunion Skype pour votre déploiement hybride de Skype entreprise Server sur site.'
ms.openlocfilehash: 8bdbb163f5ef867711ce109bc923ba0ec8401ffa
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790942"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configure your on-premises deployment for Skype Meeting Broadcast
 
**Résumé :** Découvrez les étapes à suivre pour configurer la diffusion de réunion Skype pour votre déploiement hybride de Skype entreprise Server sur site.
  
La diffusion de réunion Skype est un service en ligne intégré à Office 365. Si vous utilisez Skype entreprise Server en local et souhaitez utiliser la diffusion de réunion Skype dans votre environnement, vous devez suivre les étapes de configuration de cette rubrique. Avant de commencer, votre environnement doit être configuré pour une connexion hybride avec Skype entreprise online. Pour plus d’informations, reportez-vous aux rubriques [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) et [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurer votre environnement hybride pour la diffusion de réunion Skype

Pour préparer votre environnement pour la diffusion de réunion Skype, vous devez procéder comme suit :
  
- Configurer la Fédération avec des ressources Skype entreprise Online
    
- Configuration de domaines fédérés SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurer la Fédération avec des ressources Skype entreprise Online

Pour activer la Fédération avec des ressources Skype entreprise Online, vous devez configurer l’accès externe pour un fournisseur fédéré SIP. Pour cela, utilisez le panneau de configuration Skype entreprise Server en procédant comme suit :
  
1. Démarrez le panneau de configuration Skype entreprise Server et sélectionnez **accès externe** à gauche.
    
2. Sélectionnez **Fournisseurs fédérés SIP** et cliquez sur **Nouveau**.
    
3. Configurez le nouveau fournisseur avec les paramètres suivants :
    
|||
|:-----|:-----|
|**Activer les communications avec ce fournisseur :** <br/> |Sélectionné  <br/> |
|**Nom du fournisseur :** <br/> |LyncOnlineResources  <br/> |
|**Service Edge d’accès (nom de domaine complet [FQDN]) :** <br/> |sipfed.resources.lync.com  <br/> |
|**Niveau de vérification par défaut :** <br/> |Autorisez les utilisateurs à communiquer avec tout le monde à l’aide de ce fournisseur.  <br/> |
   
Vous pouvez également activer la Fédération avec des ressources Skype entreprise Online en exécutant l’applet de commande suivante dans Skype entreprise Server Management Shell :
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configuration de domaines fédérés SIP

Ensuite, vous devez ajouter des domaines fédérés SIP à la liste des domaines autorisés. Répétez cette procédure pour chacun des domaines répertoriés, en créant quatre domaines fédérés SIP. Ces domaines incluent les centres de données régionaux utilisés dans Skype entreprise online.
  
1. Démarrez le panneau de configuration Skype entreprise Server et sélectionnez **accès externe** à gauche.
    
2. Sélectionnez **Domaines fédérés SIP** et cliquez sur **Nouveau**.
    
3. Dans le champ **Nom de domaine (ou nom de domaine complet) :**, entrez le domaine, en répétant cette procédure pour chacun des domaines suivants :
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Vous pouvez également configurer l’accès externe pour les domaines fédérés SIP en exécutant les applets de commande suivantes dans Skype entreprise Server Management Shell :
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Une fois ces étapes de configuration terminées, vous pouvez commencer à utiliser la diffusion de réunion Skype dans votre déploiement. Pour plus d’informations sur la diffusion de réunion Skype, voir [qu’est-ce qu’une diffusion de réunion Skype ?](https://go.microsoft.com/fwlink/?LinkId=617071) et guide d’administration de la [diffusion de réunion Skype](https://go.microsoft.com/fwlink/?LinkId=617075).
  

