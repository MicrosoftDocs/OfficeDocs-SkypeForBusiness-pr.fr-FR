---
title: Planification de l’intégration de Skype Entreprise et d’Exchange
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Résumé : Passez en revue cette rubrique pour plus d’informations sur la façon d’intégrer Skype pour 2015 de serveur d’entreprise avec 2016 d’Exchange Server ou Exchange Server 2013.'
ms.openlocfilehash: 6d3d88183cfb99597829f01aae70b1c5cdd6f09a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Planifier l’intégration de Skype Entreprise et d’Exchange
 
**Résumé :** Consultez cette rubrique pour plus d’informations sur la façon d’intégrer Skype pour 2015 de serveur d’entreprise avec 2016 d’Exchange Server ou Exchange Server 2013.
  
Avant de pouvoir intégrer Skype pour Business Server 2015 et Exchange Server, vous devez vous assurer qu’Exchange Server et Skype pour Business Server 2015 sont entièrement installés et mis en service. 
  
Pour plus d’informations sur l’installation d’Exchange Server, consultez la documentation Exchange Server de planification et de déploiement pour votre version de Exchange. 
  
Pour plus d’informations sur l’installation de Skype pour Business Server 2015, consultez [Déploiement de Skype pour Business Server 2015](../../deploy/deploy.md).
  
Une fois que les serveurs sont en cours d’exécution, vous devez affecter des certificats d’authentification de serveur à serveur pour les deux Skype pour Business Server 2015 et d’Exchange Server ; Ces certificats permettent à Skype pour Business Server 2015 et d’Exchange Server pour échanger des informations et communiquer avec eux. Lorsque vous installez Exchange Server, un certificat signé automatiquement avec le nom de certificat d’authentification de Microsoft Exchange Server est créé pour vous. Ce certificat, qui se trouve dans le magasin de certificats ordinateur local, doit être utilisé pour l’authentification de serveur à serveur sur Exchange Server. Pour plus d’informations sur l’attribution des certificats dans Exchange Server, reportez-vous à la section [configuration du flux des messages et l’accès Client](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Pour Skype pour Business Server 2015, vous pouvez utiliser un Skype existant pour le certificat de serveur d’entreprise en tant que votre certificat d’authentification de serveur à serveur ; par exemple, votre certificat par défaut peut également être utilisé comme le certificat OAuthTokenIssuer. Skype pour Business Server 2015 vous permet d’utiliser un certificat de serveur Web comme le certificat pour l’authentification de serveur à serveur à condition que :
  
- le certificat inclue le nom de votre domaine SIP dans le champ Objet ;
    
- le même certificat soit configuré comme certificat OAuthTokenIssuer sur tous vos serveurs frontaux ;
    
- la longueur du certificat soit d’au moins 2 048 bits.
    
Pour plus d’informations sur les certificats d’authentification de serveur à serveur pour Skype pour Business Server 2015, voir [Attribution d’un certificat d’authentification de serveur à serveur Skype pour Business Server 2015](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Une fois que les certificats ont été affectées, vous devez ensuite configurer le service de découverte automatique sur Exchange Server. Dans Exchange Server, le service de découverte automatique configure les profils utilisateur et fournit un accès aux services Exchange lorsque les utilisateurs se connectent au système. Les utilisateurs indiquent leur adresse de messagerie et leur mot de passe au service de découverte automatique ; le service fournit en retour à l’utilisateur des informations telles que :
  
- Informations de connexion pour la connectivité interne et externe à Exchange Server.
    
- L’emplacement du serveur de boîte aux lettres de l’utilisateur.
    
- les URL pour les fonctionnalités Outlook telles que les informations sur la disponibilité, la messagerie unifiée et le carnet d’adresses en mode hors connexion ;
    
- les paramètres de serveur d’Outlook Anywhere.
    
Le service de découverte automatique doit être configuré avant de pouvoir intégrer Skype pour Business Server 2015 et Exchange Server. Vous pouvez vérifier si le service de découverte automatique a été configuré en exécutant la commande suivante à partir du Shell de gestion d’Exchange Server et en vérifiant la valeur de la propriété AutoDiscoverServiceInternalUri :
  
```
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Si cette valeur est vide, vous devez attribuer un URI au service de découverte automatique. En règle générale cet URI ressemblera à ceci :https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Vous pouvez attribuer l’URI de découverte automatique en exécutant une commande semblable à celle-ci :
  
```
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Pour plus d’informations sur le service de découverte automatique, consultez [Présentation du Service de découverte automatique](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Une fois que le service de découverte automatique a été configuré, vous devez ensuite modifier le Skype pour les paramètres de configuration de Business Server OAuth ; Cela garantit que ce Skype pour Business Server sait où trouver le service de découverte automatique. Pour modifier les paramètres de configuration OAuth dans Skype pour Business Server 2015, exécutez la commande suivante dans la Skype pour Business Server Management Shell. Lorsque vous exécutez cette commande, assurez-vous que vous spécifiez l’URI du service de découverte automatique en cours d’exécution sur votre Exchange Server et que vous utilisez **autodiscover.svc** pour pointer vers l’emplacement du service au lieu **autodiscover.xml** (qui pointe vers le fichier XML utilisé par le service) :
  
```
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Le paramètre Identity dans la commande précédente est facultatif ; C’est parce que Skype pour Business Server uniquement vous permet d’avoir une collection globale unique, OAuth de paramètres de configuration. Entre autres choses, ce qui signifie que vous pouvez configurer l’URL du service de découverte automatique à l’aide de cette commande légèrement plus simple : 
  
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
  
> [!NOTE]
> Si vous ne connaissez pas cette technologie, OAuth est un protocole d’autorisation standard utilisé par nombre des plus importants sites web. Grâce à OAuth, les informations d’identification et les mots de passe d’utilisateur ne sont pas transmis d’un ordinateur à un autre. L’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité. Ces jetons octroient l’accès à un ensemble de ressources spécifique pour une durée spécifique. 
  
En plus de la configuration du service de découverte automatique, vous devez également créer un enregistrement DNS pour le service qui pointe vers votre Exchange Server. Par exemple, si votre service de découverte automatique se trouve dans autodiscover.litwareinc.com vous devez créer un enregistrement DNS pour les autodiscover.litwareinc.com qui résout le nom de domaine pleinement qualifié de votre Exchange Server (par exemple, ATL-exchange-001.litwareinc.com).
  
Si vous intégrez Skype pour Business Server avec Exchange Online, les prochaines étapes seront de [configurer une intégration entre Skype sur site pour Business Server 2015 et Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), sinon, consultez [Skype intégrer pour Business Server 2015 avec Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Fonctionnalités prises en charge
<a name="feature_support"> </a>

Le tableau suivant détaille les fonctionnalités prises en charge sous diverses combinaisons d’en ligne ou sur site pour Exchange et Skype pour les entreprises.
  
||**2013/Exchange 2016/2010 (sur site) + Skype pour 2015 de serveur d’entreprise (sur site)**|**Exchange Online + Skype pour 2015 de serveur d’entreprise (sur site)**|**Exchange 2010 (sur site) + Skype pour professionnels en ligne**|**Exchange 2016/2013(on premises) + Skype pour professionnels en ligne**|**Exchange en ligne + Skype pour l’activité en ligne**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Présence dans Outlook  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |
|Répondre par messagerie instantanée, appel RTC, appel Skype ou appel vidéo dans un e-mail Outlook  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |
|Planification de réunions en ligne et participation à l’aide d’Outlook  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |
|Présence dans Outlook Web App  <br/> |O  <br/> |O  <br/> |N  <br/> |N  <br/> |O  <br/> |
|Répondre par messagerie instantanée, appel RTC, appel Skype ou appel vidéo dans un e-mail OWA  <br/> |O  <br/> |O  <br/> |N  <br/> |N  <br/> |O  <br/> |
|Planification de réunions en ligne et participation via Outlook Web App  <br/> |O  <br/> |O  <br/> |N  <br/> |N  <br/> |O  <br/> |
|Messagerie instantanée/présence dans les clients mobiles  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |
|Participation à des réunions en ligne dans les clients mobiles  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |
|Publication du statut en fonction des informations de disponibilité du calendrier Outlook  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |
|Liste de contacts (par le biais du magasin de contacts unifié)  <br/> |O (Exchange 2016/2013 requis)  <br/> |O  <br/> |N  <br/> |N  <br/> |O  <br/> |
|Photo de Contact haute résolution (nécessite Lync 2013 ou Skype pour les clients professionnels au minimum. Non pris en charge pour LWA, applications mobiles, Lync 2010, Lync pour Mac et autres clients plus anciens.)  <br/> |O (Exchange 2016/2013 requis)  <br/> |O  <br/> |N  <br/> |O  <br/> |O  <br/> |
|Délégation de réunion  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |
|Manqué l’historique des Conversations et appeler les journaux sont écrits dans la boîte aux lettres exchange de l’utilisateur  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |
|Archivage de contenu (messagerie instantanée et réunion) dans Exchange  <br/> |O (Exchange 2016/2013 requis)  <br/> |O  <br/> |N  <br/> |N  <br/> |O  <br/> |
|Recherche de contenu archivé  <br/> |O (Exchange 2016/2013 requis)  <br/> |O  <br/> |N  <br/> |N  <br/> |O  <br/> |
|Messagerie vocale unifiée Exchange  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |O  <br/> |
|Historique des conversations côté serveur  <br/> |O  <br/> |O  <br/> |N  <br/> |O  <br/> |O  <br/> |
   
## <a name="see-also"></a>Voir aussi
<a name="feature_support"> </a>

#### 

[Configurer l’intégration entre Skype sur site pour Business Server 2015 et Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurer OAuth entre Skype pour Business Online et Exchange sur site](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)
#### 

[Intégrer Skype pour Business Server 2015 avec Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Comment intégrer Exchange Server 2013 et Lync Server 2013, Skype pour professionnels en ligne, un déploiement hybride de Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Configurer des applications partenaires dans Skype pour Business Server 2015 et Microsoft Exchange Server](https://go.microsoft.com/fwlink/p/?LinkId=746495)

