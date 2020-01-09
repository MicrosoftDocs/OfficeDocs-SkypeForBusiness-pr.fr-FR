---
title: Planification de l’intégration de Skype Entreprise et d’Exchange
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Résumé : reportez-vous à cette rubrique pour plus d’informations sur l’intégration de Skype entreprise Server à Exchange Server 2016 ou Exchange Server 2013.'
ms.openlocfilehash: 54a079a550b1c915d9ffc124b1608a3fd3f2a5ef
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991479"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Planifier l’intégration de Skype Entreprise et d’Exchange
 
**Résumé :** Consultez cette rubrique pour plus d’informations sur l’intégration de Skype entreprise Server à Exchange Server 2016 ou Exchange Server 2013.
  
Pour pouvoir intégrer Skype entreprise Server et Exchange Server, vous devez vous assurer que Exchange Server et Skype entreprise Server sont entièrement installés et opérationnels. 
  
Pour plus d’informations sur l’installation d’Exchange Server, voir la documentation relative à la planification et au déploiement d’Exchange Server pour votre version d’Exchange. 
   
Une fois les serveurs opérationnels, vous devez attribuer des certificats d’authentification de serveur à serveur à Skype entreprise Server et Exchange Server. ces certificats permettent à Skype entreprise Server et Exchange Server d’échanger des informations et de communiquer entre eux. Lorsque vous installez Exchange Server, un certificat auto-signé avec le nom Microsoft Exchange Server auth est créé pour vous. Ce certificat, qui se trouve dans le magasin de certificats de l’ordinateur local, doit être utilisé pour l’authentification serveur à serveur sur Exchange Server. Pour plus d’informations sur l’attribution de certificats dans Exchange Server, voir [configurer le flux de messagerie et l’accès client](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Pour Skype entreprise Server, vous pouvez utiliser un certificat Skype entreprise Server existant comme certificat d’authentification de serveur à serveur. par exemple, vous pouvez également utiliser votre certificat par défaut comme certificat OAuthTokenIssuer. Skype entreprise Server vous permet d’utiliser n’importe quel certificat de serveur Web comme certificat d’authentification de serveur à serveur, à condition que :
  
- le certificat inclue le nom de votre domaine SIP dans le champ Objet ;
    
- le même certificat soit configuré comme certificat OAuthTokenIssuer sur tous vos serveurs frontaux ;
    
- la longueur du certificat soit d’au moins 2 048 bits.
    
Pour plus d’informations sur les certificats d’authentification de serveur à serveur pour Skype entreprise Server, voir [affecter un certificat d’authentification de serveur à serveur à Skype entreprise Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Une fois les certificats attribués, vous devez configurer le service de découverte automatique sur Exchange Server. Dans Exchange Server, le service de découverte automatique configure les profils utilisateur et donne accès aux services Exchange lorsque les utilisateurs ouvrent une session sur le système. Les utilisateurs indiquent leur adresse de messagerie et leur mot de passe au service de découverte automatique ; le service fournit en retour à l’utilisateur des informations telles que :
  
- Informations de connexion pour la connectivité interne et externe à Exchange Server.
    
- Emplacement du serveur de boîtes aux lettres de l’utilisateur.
    
- les URL pour les fonctionnalités Outlook telles que les informations sur la disponibilité, la messagerie unifiée et le carnet d’adresses en mode hors connexion ;
    
- les paramètres de serveur d’Outlook Anywhere.
    
Le service de découverte automatique doit être configuré avant de pouvoir intégrer Skype entreprise Server et Exchange Server. Vous pouvez vérifier si le service de découverte automatique a ou non été configuré en exécutant la commande suivante à partir d’Exchange Server Management Shell et en vérifiant la valeur de la propriété AutoDiscoverServiceInternalUri :
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Si cette valeur est vide, vous devez attribuer un URI au service de découverte automatique. En règle générale, cet URI ressemble à ceci :https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Vous pouvez attribuer l’URI de découverte automatique en exécutant une commande semblable à celle-ci :
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Pour plus d’informations sur le service de découverte automatique, voir [service de découverte automatique](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Une fois le service de découverte automatique configuré, vous devez modifier les paramètres de configuration OAuth de Skype entreprise Server. ainsi, Skype entreprise Server sait où trouver le service de découverte automatique. Pour modifier les paramètres de configuration OAuth dans Skype entreprise Server, exécutez la commande suivante à partir de Skype entreprise Server Management Shell. Lorsque vous exécutez cette commande, veillez à spécifier l’URI pour le service de découverte automatique qui s’exécute sur votre serveur Exchange, et que vous utilisez la **découverte automatique. svc** pour pointer sur l’emplacement du service au lieu de la **découverte automatique. xml** (qui pointe vers le fichier XML utilisé par le service).
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Le paramètre Identity de la commande précédente est facultatif ; en effet, Skype entreprise Server vous permet uniquement d’avoir une collection globale unique de paramètres de configuration OAuth. Entre autres choses, cela signifie que vous pouvez configurer l’URL de découverte automatique à l’aide de cette commande légèrement plus simple : 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "<https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc>" 
> 
> [!NOTE]
> Si vous ne connaissez pas cette technologie, OAuth est un protocole d’autorisation standard utilisé par nombre des plus importants sites web. Grâce à OAuth, les informations d’identification et les mots de passe d’utilisateur ne sont pas transmis d’un ordinateur à un autre. L’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité. Ces jetons octroient l’accès à un ensemble de ressources spécifique pour une durée spécifique. 
  
En plus de configurer le service de découverte automatique, vous devez également créer un enregistrement DNS pour le service qui pointe vers votre serveur Exchange. Par exemple, si votre service de découverte automatique se trouve dans autodiscover.litwareinc.com, vous devez créer un enregistrement DNS pour autodiscover.litwareinc.com résolu sur le nom de domaine complet de votre serveur Exchange (par exemple, atl-exchange-001.litwareinc.com).
  
Si vous intégrez Skype entreprise Server à Exchange Online, les étapes suivantes sont décrites dans la rubrique [configurer l’intégration entre Skype entreprise Server et Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), sinon, voir [intégrer Skype entreprise Server à Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Fonctionnalités prises en charge
<a name="feature_support"> </a>

Le tableau suivant répertorie les fonctionnalités prises en charge dans les diverses combinaisons de en ligne ou en local pour Exchange et Skype entreprise.
  
||**Exchange 2016/2013/2010 (en local) + Skype entreprise Server (en local)**|**Exchange Online + Skype entreprise Server (en local)**|**Exchange 2010 (en local) + Skype entreprise Online**|**Exchange 2016/2013 (local) + Skype entreprise Online**|**Exchange Online + Skype entreprise Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Présence dans Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Répondre par messagerie instantanée, appel RTC, appel Skype ou appel vidéo dans un e-mail Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Planification de réunions en ligne et participation à l’aide d’Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Présence dans Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Répondre par messagerie instantanée, appel RTC, appel Skype ou appel vidéo dans un e-mail OWA  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Planification de réunions en ligne et participation via Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Messagerie instantanée/présence dans les clients mobiles  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Participation à des réunions en ligne dans les clients mobiles  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Publication du statut en fonction des informations de disponibilité du calendrier Outlook  <br/> |O  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |O  <br/> |
|Liste de contacts (par le biais du magasin de contacts unifié)  <br/> |O (Exchange 2016/2013 requis)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Photo de contact haute résolution (nécessite Lync 2013 ou Skype entreprise clients au minimum). Non pris en charge pour LWA, applications mobiles, Lync 2010, Lync pour Mac et autres clients plus anciens.)  <br/> |O (Exchange 2016/2013 requis)  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |
|Délégation de réunion  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|L’historique des conversations manquées et les journaux d’appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Archivage de contenu (messagerie instantanée et réunion) dans Exchange  <br/> |O (Exchange 2016/2013 requis)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Recherche de contenu archivé  <br/> |O (Exchange 2016/2013 requis)  <br/> |Y  <br/> |N  <br/> |N  <br/> |O  <br/> |
|Messagerie vocale unifiée Exchange  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Historique des conversations côté serveur  <br/> |O  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |

> [!NOTE]
> Un service de boîte vocale Cloud est pris en charge pour Skype entreprise Online, Skype entreprise Server 2019, Skype entreprise Server 2015 et Lync Server 2013.
> 

## <a name="see-also"></a>Voir aussi
<a name="feature_support"> </a>

[Configurer l’intégration entre Skype entreprise Server et Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurer le protocole OAuth entre Skype entreprise Online et Exchange en local](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Intégration de Skype entreprise Server à Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Intégration d’Exchange Server 2013 à Lync Server 2013, Skype entreprise Online ou déploiement hybride Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Configurer les applications partenaires dans Skype entreprise Server et Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
