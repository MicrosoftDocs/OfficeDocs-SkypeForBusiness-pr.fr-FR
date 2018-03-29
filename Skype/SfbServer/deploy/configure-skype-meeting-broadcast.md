---
title: Configuration de votre déploiement local pour la diffusion de réunion Skype
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
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
description: 'Résumé : Découvrez les étapes que vous devez effectuer pour configurer la diffusion de réunion Skype pour votre Skype sur site pour le déploiement hybride de serveur d’entreprise.'
ms.openlocfilehash: e788a263223ea3fa0f4ce9ed844fb5b4eb0ae898
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configuration de votre déploiement local pour la diffusion de réunion Skype
 
**Résumé :** Obtenir des informations sur les étapes que vous devez effectuer pour configurer la diffusion de réunion Skype pour votre Skype sur site pour le déploiement hybride de serveur d’entreprise.
  
Diffusion de réunion Skype est un service en ligne qui fait partie d’Office 365. Si vous exécutez Skype pour Business Server en local et que vous souhaitez utiliser Skype réunion de diffusion dans votre environnement, vous devez suivre les étapes de configuration dans cette rubrique. Avant de commencer, votre environnement doit être configuré pour hybride avec Skype pour l’activité en ligne. Pour plus d’informations, consultez [planification de la connectivité d’hybride entre Skype pour Business Server et Skype pour Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et de [déployer une connectivité hybride entre Skype pour Business Server et Skype pour l’activité en ligne](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurer votre environnement hybride pour la diffusion de réunion Skype

Vous devez effectuer les tâches suivantes pour préparer votre environnement pour diffusion de réunion de Skype :
  
- Configurer la fédération avec Skype pour les ressources d’entreprise en ligne
    
- Configuration de domaines fédérés SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurer la fédération avec Skype pour les ressources d’entreprise en ligne

Pour activer la fédération avec Skype pour les ressources d’entreprise en ligne, vous devez configurer l’accès externe pour un fournisseur SIP de fédéré. Pour faire cela à l’aide de la Skype pour le panneau de configuration de Business Server comme suit :
  
1. Démarrer le Skype pour le panneau de configuration de Business Server et sélectionnez **l’Accès externe** à gauche.
    
2. Sélectionnez **Fournisseurs fédérés SIP** et cliquez sur **Nouveau**.
    
3. Configurez le nouveau fournisseur avec les paramètres suivants :
    
|||
|:-----|:-----|
|**Permettre la communication avec ce fournisseur :** <br/> |Sélectionné  <br/> |
|**Nom du fournisseur :** <br/> |LyncOnlineResources  <br/> |
|**Service Edge d’accès (nom de domaine complet [FQDN]) :** <br/> |sipfed.Resources.Lync.com  <br/> |
|**Niveau de vérification par défaut :** <br/> |Autorisez les utilisateurs à communiquer avec tout le monde à l’aide de ce fournisseur.  <br/> |
   
Vous pouvez également activer la fédération avec Skype pour les ressources d’entreprise en ligne en exécutant la cmdlet suivante dans le Skype pour Business Server Management Shell :
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configuration de domaines fédérés SIP

Ensuite, vous devez ajouter des domaines de SIP fédéré à la liste de domaines autorisés. Répétez cette procédure pour chacun des domaines répertoriés, en créant quatre domaines fédérés SIP. Ces domaines sont notamment pour les données régionales centres utilisés dans Skype pour l’activité en ligne.
  
1. Démarrer le Skype pour le panneau de configuration de Business Server et sélectionnez **l’Accès externe** à gauche.
    
2. Sélectionnez **Domaines fédérés SIP** et cliquez sur **Nouveau**.
    
3. Dans le champ **Nom de domaine (ou nom de domaine complet) :**, entrez le domaine, en répétant cette procédure pour chacun des domaines suivants :
    
  - noammeetings.Lync.com
    
  - emeameetings.Lync.com
    
  - apacmeetings.Lync.com
    
  - Resources.Lync.com
    
Vous pouvez également configurer l’accès externe pour les domaines SIP fédéré en exécutant les applets de commande suivantes dans le Skype pour Business Server Management Shell :
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "emeameetings.lync.com"
```

```
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "resources.lync.com"
```

Une fois que vous avez terminé ces étapes de configuration, vous pouvez démarrer à l’aide de Skype réunion de diffusion dans votre déploiement. Pour plus d’informations sur la diffusion de réunion Skype, consultez [ce qu’est une diffusion de réunion Skype ?](https://go.microsoft.com/fwlink/?LinkId=617071) et [Guide de l’administrateur de diffusion Skype réunion](https://go.microsoft.com/fwlink/?LinkId=617075).
  

