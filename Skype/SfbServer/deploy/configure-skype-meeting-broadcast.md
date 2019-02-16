---
title: Configuration de votre déploiement local pour la diffusion de réunion Skype
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Résumé : Découvrez les différentes étapes à effectuer pour configurer la diffusion de réunion Skype pour votre Skype sur site pour le déploiement hybride Business Server.'
ms.openlocfilehash: 09b99cab45b8832be34a3219a222324d199c5195
ms.sourcegitcommit: 4967c9b1010a444475dcfbdb6dd3c058494449d9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2019
ms.locfileid: "30069468"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configure your on-premises deployment for Skype Meeting Broadcast
 
**Résumé :** Découvrez les différentes étapes à effectuer pour configurer la diffusion de réunion Skype pour votre Skype sur site pour le déploiement hybride Business Server.
  
Diffusion de réunion Skype est un service en ligne qui fait partie d’Office 365. Si vous exécutez Skype pour Business Server local et que vous souhaitez utiliser Skype réunion diffusion dans votre environnement, vous devez suivre les étapes de configuration dans cette rubrique. Avant de commencer, votre environnement doit être configuré pour l’environnement hybride avec Skype pour Business Online. Pour plus d’informations, reportez-vous aux rubriques [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) et [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurer votre environnement hybride pour la diffusion de réunion Skype

Vous devez effectuer les opérations suivantes pour préparer votre environnement pour la diffusion de réunion Skype :
  
- Configurer la fédération avec Skype pour les ressources d’entreprise en ligne
    
- Configuration de domaines fédérés SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurer la fédération avec Skype pour les ressources d’entreprise en ligne

Pour activer la fédération avec Skype pour les ressources d’entreprise en ligne, vous devez configurer l’accès externe pour un fournisseur fédéré SIP. Pour cela à l’aide de la Skype pour le panneau de configuration serveur Business, suivez ces étapes :
  
1. Démarrez le Skype pour le panneau de configuration serveur Business et sélectionnez **Accès externe** à gauche.
    
2. Sélectionnez **Fournisseurs fédérés SIP** et cliquez sur **Nouveau**.
    
3. Configurez le nouveau fournisseur avec les paramètres suivants :
    
|||
|:-----|:-----|
|**Activer les communications avec ce fournisseur :** <br/> |Sélectionné  <br/> |
|**Nom du fournisseur :** <br/> |LyncOnlineResources  <br/> |
|**Service Edge d’accès (nom de domaine complet [FQDN]) :** <br/> |sipfed.resources.lync.com  <br/> |
|**Niveau de vérification par défaut :** <br/> |Autorisez les utilisateurs à communiquer avec tout le monde à l’aide de ce fournisseur.  <br/> |
   
Vous pouvez également activer la fédération avec Skype pour les ressources d’entreprise en ligne en exécutant la cmdlet suivante dans le Skype pour Business Server Management Shell :
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configuration de domaines fédérés SIP

Ensuite, vous devez ajouter des domaines fédérés SIP à la liste des domaines autorisés. Répétez cette procédure pour chacun des domaines répertoriés, en créant quatre domaines fédérés SIP. Incluent ces domaines sont pour les données régionales centres utilisé dans Skype pour Business en ligne.
  
1. Démarrez le Skype pour le panneau de configuration serveur Business et sélectionnez **Accès externe** à gauche.
    
2. Sélectionnez **Domaines fédérés SIP** et cliquez sur **Nouveau**.
    
3. Dans le champ **Nom de domaine (ou nom de domaine complet) :**, entrez le domaine, en répétant cette procédure pour chacun des domaines suivants :
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Vous pouvez également configurer l’accès externe pour les domaines fédérés SIP en exécutant les cmdlets suivantes dans le Skype pour Business Server Management Shell :
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Une fois que vous avez terminé ces étapes de configuration, vous pouvez démarrer à l’aide de diffusion de réunion Skype dans votre déploiement. Pour plus d’informations sur la diffusion de réunion Skype, voir [What ' s une diffusion de réunion Skype ?](https://go.microsoft.com/fwlink/?LinkId=617071) et [Guide d’administration de diffusion Skype réunion](https://go.microsoft.com/fwlink/?LinkId=617075).
  

